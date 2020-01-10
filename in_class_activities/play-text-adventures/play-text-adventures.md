---
layout: default
img: zork.jpg
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Zork, an early intractive fiction game released in 1977.
title: Play Text-Adventure Games
type: in-class
active_tab: homework
release_date: 2020-01-04
due_date: 2020-01-16 23:59:00EST
materials:
    - 
        name: Bronze, A Fractured Fairy Tale by Emily Short
        url: http://iplayif.com/?story=http://www.ifarchive.org/if-archive/games/zcode/Bronze.zblorb 
    - 
        name: AI Dungeon
        url: https://play.aidungeon.io
submission_link: https://www.gradescope.com/courses/59562
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



{% if page.type == "in-class" %}
<!-- In class activity -->
<div class="alert alert-info">
This is the in-class activity for {{ page.due_date | date: "%A %B %-d" }}.
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% endif %}

{% if page.materials %}
<div class="alert alert-info">
The materials for this assignment are here:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}



In Class Activity: Play Text Adventure Games
=============================================================

Today in class you will play a couple text-adventure games, and answer some questions about them. We are going to play two games:

1. [Bronze](http://iplayif.com/?story=http://www.ifarchive.org/if-archive/games/zcode/Bronze.zblorb).  This is a text adventure game in the style of classic games like [Zork](http://textadventures.co.uk/games/view/5zyoqrsugeopel3ffhz_vq/zork) and other [Infocom games](https://en.wikipedia.org/wiki/Classic_Text_Adventure_Masterpieces_of_Infocom).  

2. [AI Dungeon 2](https://colab.sandbox.google.com/github/nickwalton/AIDungeon/blob/master/AIDungeon_2.ipynb). This is a modern a machine-generated text adventure.  It uses a neural network based language model called [GPT-2](https://openai.com/blog/better-language-models/).

## Classic Text Adventures

The parser for Bronze has a limited vocabulary.  This cheatsheet should guide to what commands are allowable in text adventure games:

<center>
<img src="play-if-card.png" class="img-responsive"/>
</center>

Helpfully, the very first interaction with Bronze is a question asking you ``Have you played interactive fiction before? >``.  We recommend responding ``no``.  If you do, then Bronze will display a bunch of userful hints about what commands you can use.

While you're plaing this game, please do the following:
* __Draw a map of the game__ as you go.  Drawing maps was a normal practice in classific interactive fiction games.  We'll ask you to take a snapshot of your map and turn it in via Gradescope at the end of the class period.
* __Keep track of failed commands__.  Write down or copy-and-paste a list of any commands that you try that the game fails to understand.


## AI Dungeon 2

Unlike classic text adventures, AI Dungeon will let you enter any command that you want to.  Rather than having an internal representation of the game as a map with locations and objects, it generates its descriptions on the fly, based on your commands and what has been described so far.  On the one hand, this demonstrates the power of modern neural language models.  On the otherhand, it removes some of elements that are important to game play.  For instance, if you come across a locked door in AI Dungeon, you can just say ``Pick the key up off the ground and unlock the door``.  Just by saying it, you will have created a key from nothing.  


While you're plaing this game, please do the following:
* __Keep track of bad responses__.  Sometimes the game fails to understand your intent, and sometimes it generates illogical responses.  Once you see this, copy-and-paste what you said, and how the game responded.  Write down why you think it was a bad reponse.


### Questions
1. How many of the rooms did you explore in Bronze? This is tracked for you in the title bar at the top of the game.  Did you solve any of puzzles?
1. When you tried a command and it failed, where you able to re-issue a different command that the game could understand?  If so, give an example.  If not, what did you do instead?
2. What do you perceive are the challenges in designing a text adventure game as compared to non-interactive fiction?
3. While AI Dungeon 2 is fun to play, it clearly gets a lot of things wrong. What is the system lacking as compared to hand-crafted games?
4. If you had near-infinite resources (for GPUs, to build datasets, to collect human annotations, etc.), how would you propose to improve AI Dungeon to make it more fun to play?



