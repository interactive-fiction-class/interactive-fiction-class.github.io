---
layout: default
img: zork.jpg
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Zork, an early intractive fiction game released in 1977.
title: Build a Text-Adventure Game
type: Homework
number: 1
active_tab: homework
release_date: 2020-01-16 
due_date: 2020-01-30 13:30:00EST
materials:
    - 
        name: Text Adventure Game (Python Notebook viewable on Google Colab)
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb
submission_link: https://www.gradescope.com/courses/78405
readings:
    -
      title: Adventuron Classroom
      authors: Chris Ainsley / Adventuron Software Limited
      url: https://adventuron.io/classroom/
      note: This is a tutorial aimed at teaching elementary school kids how to program by writing a text adventure game.  I modeled our text adventure game after this Adventuron system.
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

In this homework assignment, you will write your own classic text adventure game.  This homework can be completed in groups of up to 2 people.  You will implement two text adventure games.  One will be a re-implementation of the __Action Castle__ game, and one will be a game that you design yourself. The game that you design can be on any topic, or can tell any story of your choice.  We will play the games that you design during class, and part of your grade will be awarded based on how creative/exciting your classmates think your game is.

### Starter code

We have provided [starter code for a basic text adventure game](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb).  You should save a copy this Python Notebook to your own Google drive, and modify it however you want.  Since this is a graduate-level class, we leave the implementation details open-ended.

### Game 1: Action Castle

Action Castle is a game by Jared A. Sorensen.  It is included in his book [Parsley](http://www.memento-mori.com/parsely-products/parsely-pdf), which is a collection of games inspired by the text-adventures of the 1980s.  Parsley is a party game where you take on the role of the parser, and the players shout out commands like GO NORTH, LIGHT LAMP or GET SWORD.  You obtusely follow player's commands, simulating a computer's limited vocabulary.  The effect is suprisingly hilarious and fun. 

We got Jared's permission to distribute the Action Castle module in class, and you can also [buy the Parsley book for $20](http://www.memento-mori.com/parsely-products/parsely-pdf) if you'd like to support an awesome indy game developer.

You should modify the provided code to:
1. Create 13 locations for Action Castle (Cottage, Garden Path, Fishing Pond, Winding Path, 
Top of the Tall Tree, Drawbridge, Courtyard, Tower Stairs, Tower, 
Dungeon Stairs, Dungeon, Great Feasting Hall, Throne Room).
2. Create items for the game (fishing poll, rosebush, club, fish, the troll etc.).
3. Update the code so that it can handle the actions/commands/preconditions that are described by the Action Castle module.


### Game 2: Your Own Creation 

Your game should include all of the following:

* At least 3 "rooms"
* At least 3 objects that can be interacted with. These can be doors, keys, tools, octupi, etc.
* At least one "win" state and at least one "lose" state.

### NLP Requirements
In the earliest text adventure games, parsers used exact string matching. If a command wasn't in either the form `verb` or `verb object`, the parser would not recognize it. However, parsers and naural language processing (NL) in general have evolved tremendously from the 1970s.

We would like you to use NLP and machine learning to update the keyword-based parser in our sample code to be able to more robustly handle any input from the user.  In other words, the user should be able to type commands like _"pluck the rose"_ or _"pick a flower from the rosebush"_ instead of the single one command that it currently recognizes _"pick rose"_.  Similarly, the player should be able to say _"leave the cottage"_ intead of _"out"_.  To do so, we recommend that you start by updating the ```get_player_intent``` function in the ```Parser```, to be a multi-class text classifier.

We ask that you take advantage of at least **two** advancements from the last four decades of NLP research to either make your parser more intelligent than simple string matching or to otherwise improve the game-playing experience.

Some possible ideas are:

* Using word2vec similarity to allow the parser to do "fuzzy" matching of similar words.
* Using a modern dependency parser to extract the verb and object from a user input.
* A guardswoman NPC who will only let you pass if you [complement her](https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis).
* An ogre who will only marry you if [you tell him a joke](https://ccc.inaoep.mx/~villasen/bib/LEARNING%20TO%20LAUGH%20(AUTOMATICALLY).pdf).

You will likely find (Spacy)[https://spacy.io/usage/facts-figures], (NLTK)[https://www.nltk.org/], or (AllenNLP)[https://github.com/allenai/allennlp] useful for completing this task.

## What to submit

1. You should save your game as a Python notebook in Github.  You can use [Google Colab to view Python Notebooks on Github](https://colab.research.google.com/github/googlecolab/colabtools/blob/master/notebooks/colab-github-demo.ipynb).  We recommend that you use Colab to test and debug your notebook, since that's how we are going to play your game.

2. Implement a method called `visualize(game)` that uses [Graphviz](https://colab.research.google.com/github/xflr6/graphviz/blob/master/examples/notebook.ipynb) to plot a directed graph representation of your game.  __Hint: It might be worth implementing a breadth-first search that recrsively expands all locations of your graph, beginning at the start_location of the game.__

2. A text file called `playthrough.txt` with all of the commands that we need to issue to complete your game. 

3. A report that describes how you used **two** advancements in NLP to improve the quality of your game. You should cite relevent papers, and explain how you are using the methods introduced in them.

If you are submitting a Google Colab or IPython notebook, you can include your report as part of the notebook itself, and all you need to submit is a single notebook link. Likewise, if you are using a Github repository, you can put your report into the README, and all you need to submit is the Github link.



{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  _{{ reading.note }}_
{% endfor %}
{% endif %}

