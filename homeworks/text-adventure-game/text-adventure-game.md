---
layout: default
img: zork.jpg
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Zork, an early intractive fiction game released in 1977.
title: Build a Text-Adventure Game
type: Homework
number: 1
active_tab: homework
release_date: 2024-01-16
due_date: 2022-01-17 23:59:00EST
materials:
    - 
        name: Text Adventure Game starter code
        url: XXX
    - 
        name: Parsely&colon; Preview n' Play Edition (this contains the Action Castle game).  
        url: http://www.memento-mori.com/pdf/parsely-preview-n-play-edition
    - 
        name: Text from Action Castle  
        url: https://raw.githubusercontent.com/interactive-fiction-class/interactive-fiction-class.github.io/master/homeworks/text-adventure-game/action_castle_text.txt
submission_link: 
readings:
    -
      title: Adventuron Classroom
      authors: Chris Ainsley / Adventuron Software Limited
      url: https://adventuron.io/classroom/
      note: This is a tutorial aimed at teaching elementary school kids how to program by writing a text adventure game.  I modeled our text adventure game after this Adventuron system.
    -
      title: How to Make a Text-Based Adventure - Commands and Parser
      authors: The Hitchhiker's Guide to the Galaxy (H2G2)
      url: https://h2g2.com/edited_entry/A20600641
---

<!-- Check whether the assignment is ready to release -->
{% capture today %}{{site.time | date: '%Y%m%d'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%Y%m%d'}}{% endcapture %}
{% if due_date < today %} 
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
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} at {{ page.due_date | date: "%I:%M%p" }} EST. 
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

We have provided [starter code for a basic text adventure game](XXX).  You are free modify it however you want, and bring in any dependencies you feel will be useful.

### Task 1: Implement Action Castle

Action Castle is a game by Jared A. Sorensen.  It is included in his book [Parsley](http://www.memento-mori.com/pdf/parsely-pdf), which is a collection of games inspired by the text-adventures of the 1980s.  Parsley is a party game where you take on the role of the parser, and the players shout out commands like GO NORTH, LIGHT LAMP or GET SWORD.  You obtusely follow player's commands, simulating a computer's limited vocabulary.  The effect is suprisingly hilarious and fun. 

You should download ["Parsely: Preview n' Play Edition"](http://www.memento-mori.com/pdf/parsely-preview-n-play-edition) which is free on Jared's website.  It contains the Action Castle game that you'll be implementing.  You can also [buy the full Parsley book for $20](http://www.memento-mori.com/pdf/parsely-pdf) if you'd like to support an awesome indy game developer.  The Preview n' Play Edition also explains how these kinds of games work.

We have implemented most of Action Castle for you. 
1. We created the 13 locations from Action Castle (Cottage, Garden Path, Fishing Pond, Winding Path, Top of the Tall Tree, Drawbridge, Courtyard, Tower Stairs, Tower, 
Dungeon Stairs, Dungeon, Great Feasting Hall, Throne Room).
2. We created most of the items for the game (fishing poll, rosebush, club, fish, the troll etc.).
You will need to update the code so that it can:
3. Add blocks to the game (these are puzzles that the player needs to solve in order to make progress).  You should add blocks in
* The courtyard - the guard prevents you from going east
* The dungeon stairs - the darkness prevents you from going down
* The tower stairs - the locked door prevents you from going up
4. Add special actions for the Action Castle game.  You should add Actions for:
* Unlocking the door
* Reading the runes to banish the ghost from the dungeon
* Proposing marriage
* Sitting on the throne


<div class="alert alert-warning" markdown="1">
__Need a hint on how to get started?__ Check out the `Troll_Block` class to see an example of how to implement a Block, and the `Eat` class as an example of how to implement an Action.   
</div>


<div class="alert alert-warning" markdown="1">
__Want to know how to win the game?__ Here's a sequence of actions that should result in a winning state, if you've implemented the game correctly. You can play through the full Action Castle game with the following commands:
`take pole, go out, go south, catch fish with pole, go north, pick rose, smell rose, go north, go up, get branch, go down, go east, give the troll the fish, go east, hit guard with branch, get key, go east, get candle, go west, go down, light lamp, go down, light candle, read runes, get crown, go up, go up, go up, unlock door, go up, give rose to the princess, propose to the princess, wear crown, down, down, east, east, sit on throne`
</div>



### Task 2: Implement Your Own Creation

Your game should include all of the following:

* At least 3 Locations
* At least 3 Items that can be interacted with. These can be doors, keys, tools, ogres, etc.
* At least one "puzzle" where there are certain preconditions that must be met before the player can make forward progress.  This could be an Action or a Block.
* At least one "win" state and at least one "lose" state.

A fun example of a tiny game with very 3 locations and 3 items is the "Flaming Goat" game in Jared A. Sorensen's [Parsley book](http://www.memento-mori.com/pdf/parsely-pdf).  I played it with my son when he was 6 year old, and it cracked him up.

Optionally, you can think about adding other elements to your game, like:
* Scoring
* Changes over time
* Interesting non-player characters

Feel free to modify the starter code in any way you see fit in order to enable your game ideas. However, the "Play the game" and "Visualize your game" code blocks should remain functional.

What kind of game should you make?  It's up to you! Be creative!  For inspiration, we recommend searching Pinterest for cross-section maps.  Here are some that we like:

<div class="container-fluid">
  <div class="row">
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/lighthouse.jpg"><img src="inspiration/lighthouse.jpg" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/treehouse.jpg"><img src="inspiration/treehouse.jpg" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/oubliette.png"><img src="inspiration/oubliette.png" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/storm-king.jpg"><img src="inspiration/storm-king-small.jpg" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/mars.pdf"><img src="inspiration/mars.jpg" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px; height: 350px;">
<a href="inspiration/apartment.jpg"><img src="inspiration/apartment.jpg" style="height: 100%; width: 100%; max-width: 250px"></a>
</div>
  </div>
</div>


<div class="alert alert-warning" markdown="1">
__Tip:__ I recommend drawing out on your game on [graph paper](http://print-graph-paper.com/) before you get started.
</div>

## What to submit

You should submit a link to a Github repository which contains the following:

1. An Python notebook called `action_castle.ipynb` that runs Action Castle. (You can use [Google Colab to view IPython Notebooks on Github](https://colab.research.google.com/github/googlecolab/colabtools/blob/master/notebooks/colab-github-demo.ipynb).)
2. An IPython notebook called `my_game.ipynb` that runs the initial version of your game.
3. A text file called `playthrough.txt` with all of the commands that we need to issue to complete your game. It shold be a plain text file with one command per line.
4. A text file called `README.md` containing a short paragraph describing your game, and why you picked that topic.

Submissions should be done on [Gradescope]({{page.submission_link}}).

## Grading
<div class="alert alert-warning" markdown="1">
* Implement Action Castle - 5 points
* Implement Your Own Creation - 5 points
</div>

{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
