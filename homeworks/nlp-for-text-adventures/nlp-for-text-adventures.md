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

In this homework you will using advancements in NLP to improve your game. Using two different NLP methods, you will 

1. Make an improvement to your parser. 
2. Add a new game-play experience.

We have put together sample code for a number of methods in NLP that you might find useful or interesting. These include:

* Wordnet 
* Dependency parsing
* Coreference Resolution
* Parse-of-Speech Tasgging
* Semantic role labeling
* Named entity recognition
* Sentiment classification
* Word concreteness classification
* Style classification
* Word embeddings

You are of course welcome to explore other concepts from NLP beyond this list. 


### Task 1: Improve your Parser

Make one improvement to your parser that allows it to handle some form of user input that is not simply hard-coded rule. A few suggestions are:

1. Use sentence segmentation and coreference resolution to allow the player to chain together commands. For example: "Pick the rose. Smell it."
2. Allow the player to use nearby words to the ones you intend. For example: "Toss/throw/chuck the stick" all resolve to the same command.
3. Instead of hardocoding "verb object," use dependecncy parsing to detect the direct object in the player's command.

More suggestions can be found in the demo Colab.

In your homework submission, include a discussion of how you implemented this improvement. Copy and paste several example interactions with your game that showcase the new parser feature.


### Task 2. Add a Gameplay Experience
Add a novel gameplay experience that would only be possible with NLP.
This can be a new character, puzzle, or obstacle. A few suggestions are: 

* A guardswoman NPC who will only let you pass if you complement her.
* An ogre who will only marry you if speak like Shakespeare.
* Build a speech-to-text module that allows the player to speak voice commands into the computer's microphone.

More suggestions can be found in the demo Colab.

In your homework submission, include a discussion of how you implemented your new gameplay feature and why you think it makes your game more fun. Copy and paste several example interactions with your game that showcase the new feature.


## What to submit

1. An IPython notebook called `my_game_improved.ipynb` that runs the new version of your game with the two improvements.
3. A text file called `playthrough.txt` with all of the commands that we need to issue to complete your game. It should be a plain text file with one command per line. (This may or may not be identical to HW1)
4. A text file called `README.md` containing discussion of your two new methods. 

{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  _{{ reading.note }}_
{% endfor %}
{% endif %}

