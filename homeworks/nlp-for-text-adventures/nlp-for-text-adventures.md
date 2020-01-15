---
layout: default
img: ELIZA.jpg
img_link: https://en.wikipedia.org/wiki/ELIZA
caption: ELIZA was an early natural language processing program created in the 1960s.
title: NLP for Text-Adventure Games
type: Homework
number: 2
active_tab: homework
release_date: 2020-01-23 
due_date: 2020-01-30 13:30:00EST
attribution: This homework is based in part on the "Commanding Robots with Natural Language" R2D2 assignment from UPenn's Artificial Intelligence class (CIS 521), which was developed by John Zhang, Calvin Zhenghua Chen, and Chris Callison-Burch with help from Yrvine Thelusma.
materials:
    - 
        name: Text Adventure Game (Python Notebook viewable on Google Colab)
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb
submission_link: https://www.gradescope.com/courses/78405
readings:
-
   title: Vector Semantics and Embeddings 
   authors: Dan Jurafsky and James H. Martin
   venue: Speech and Language Processing (3rd edition draft)
   type: textbook
   url: https://web.stanford.edu/~jurafsky/slp3/6.pdf
-
   title: Magnitude&colon; A Fast, Efficient Universal Vector Embedding Utility Package
   authors: Ajay Patel, Alexander Sands, Chris Callison-Burch, Marianna Apidianaki
   venue: ACL 2018
   type: conference
   url: https://www.aclweb.org/anthology/D18-2021/
-
   title: Dialogue Systems and Chatbots 
   authors: Dan Jurafsky and James H. Martin
   venue: Speech and Language Processing (3rd edition draft)
   type: textbook
   url: https://web.stanford.edu/~jurafsky/slp3/26.pdf
---

<!-- Check whether the assignment is ready to release -->
{% capture today %}{{'now' | date: '%s'}}{% endcapture %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% if release_date > today %} 
<div class="alert alert-danger">
Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<!-- Check whether the assignment is up to date -->
{% capture this_year %}{{'now' | date: '%Y'}}{% endcapture %}
{% capture due_year %}{{page.due_date | date: '%Y'}}{% endcapture %}
{% if this_year != due_year %} 
<div class="alert alert-danger">
Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% if page.materials %}
<div class="alert alert-info">
You can download the materials for this assignment here:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}


{{page.type}} {{page.number}}: {{page.title}}
=============================================================

## Instructions

In the earliest text adventure games, parsers used exact string matching. If a command wasn't in either the form `verb` or `verb object`, the parser would not recognize it. However, parsers and natural language processing (NLP) in general have evolved tremendously since the 1970s. NLP is a vibrant subfield of artificial intelligence.  One of the goals of NLP is to allow computers to understand commands spoken in human language.  This enables technologies like Amazon Alexa, Apple’s Siri or Google’s Assistant.


Early interactive fiction games, as well as the games you implemented for Homework 1, force players to enter commands following a strict syntax, often using the `verb object` form. Players can only say things like `pick rose` or `smell rose` if those commands have been specifically programmed into the parser. 

In this homework you will be using NLP to allow players to say something more elaborate like

```
"Pluck a fresh bloom from the rosebush, and inhale its scent."
```

In this homework, you will implement two NLP components in your game.
The first, an __intent detection module__ that uses word embeddings to improve the parser, is defined for you.
For the second component, you may draw from the the last three decades of NLP research to come up with a creative way to improve your game.
We'll give you several suggestions of interesting possible directions, but we encourage you to come up with your own ideas.



### Task 1: Intent Detection

An intent detection module takes as input a natural language command and determines what action the player is attempting to take.
In the  In the [Parser class of the text adventure starter code](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb) that we gave you in HW1, this module is implemented in the ``get_player_intent`` function.
In the version of the code we gave you, the function takes in a command from the player and returns one of eight possible actions: 
* __direction__ - the player wants to move somewhere
* __examine__ - the player wants to look at something 
* __redescribe__ - the player wants to redescribe the current location
* __inventory__ - the player wants to get a list of things in their inventory
* __take__ - the player wants to get something and put it in their inventory
* __drop__ - the player wants to drop something from their inventory
* __sequence__ - the player issued multiple commands and wants them to be executed as a sequence 
* __special__ - handles special commands that were added (like picking a rose, or hitting a troll with the branch)

In the sample code, the  ``get_player_intent`` function is enterly keyword-based.  This has the limitation failing to recognize even simple synonyms.  
For instance, in the keyword algorithm the game knows what to do for the ``pick rose`` command, but it will fail to recognize ``pick flower`` or ``pluck rose``, even though those are preferctly reasonable synonyms that a person can easily understand mean the same as ``pick rose``.

We would like you to use NLP and machine learning to update the keyword-based parser in our sample code to be able to more robustly handle any input from the user.  In other words, the user should be able to type commands like _"pluck the rose"_ or _"pick a flower from the rosebush"_ instead of the single one command that it currently recognizes _"pick rose"_.  Similarly, the player should be able to say _"leave the cottage"_ instead of just _"out"_.  You will update the ```get_player_intent``` function in the ```Parser``` to be a multi-class text classifier.



#### 1. Natural Language Commands for Action Castle [15 points]

We're going to begin this assignment by brainstorming different ways that a player could say each command.  We will do a play through of Action Castle, and write out different ways of saying each command. 

```
You are standing in a small cottage.
Exits: Out
You see: 
a fishing pole

>pick up the fishing pole
I'm not sure what you want to do.
>take the fishing pole
You take the pole.
>look at the fishing pole
I'm not sure what you want to do.
>examine the fishing rod
You don't see anything special.
>what does the fishing pole look like?
I'm not sure what you want to do.
>examine the fishing pole
A SIMPLE FISHING POLE.
>put the fishing pole down
I'm not sure what you want to do.
>drop the fishing pole
You drop the pole.
>put the pole back into my inventory
You have: a lamp (unlit)

```


<!--
We ask that you take advantage of at least **two** advancements from the last four decades of NLP research to either make your parser more intelligent than simple string matching or to otherwise improve the game-playing experience.
-->

### Task 2: Free Choice

1. Co-reference resolution. Type this into a text adventure game ``Pick the rose. Smell it.`` and it will probably reply something dumb like ``I don't know what it is.``. Co-reference resolution is an NLP technology for taking pronouns (like she, he, it, they, them, those, etc.) and figuring out what preceeding noun phrase they (see what I did there?) refer to.  You could try using the [Allen NLP Co-reference Resolution Module].  You should give a detailed analysis of how well it works.


2. Add voice.  A speech-to-text module will allow you to speak into your computer’s microphone and have your voice command converted to text.   Use the Google speech-to-text API to allow a player to talk to the game, and then use the Google's text-to-speech to have the game speak its response aloud.  

3. Arguments to the verb.  Verbs have argments like _the subject_ (__I__ jumped), _the direct object_ (I kicked __the ball__), and the _indirect object_ (I gave the book to __Daphne__).  You can use an NLP system like Spacy or Allen NLP to create a dependency parse to extract the verb its arguments from a user input.  You can then convert them into 


Some possible ideas are:


* A guardswoman NPC who will only let you pass if you [complement her](https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis).
* An ogre who will only marry you if [you tell him a joke](https://ccc.inaoep.mx/~villasen/bib/LEARNING%20TO%20LAUGH%20(AUTOMATICALLY).pdf).

There are serveral good NLP toolkits that you can use for this part of the homeowrk:  [Spacy](https://spacy.io/usage/facts-figures), [NLTK](https://www.nltk.org/), or [AllenNLP](https://github.com/allenai/allennlp).




## What to submit

1. A colab to run the version of your games from HW1 that includes your improvements.
1. A report called either `report.pdf` or `report.md` that describes how you used **two** advancements in NLP to improve the quality of your game. You should cite relevent papers, and explain how you are using the methods introduced in them.

{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  _{{ reading.note }}_
{% endfor %}
{% endif %}

