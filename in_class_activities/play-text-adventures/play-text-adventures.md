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

Today in class you will play a couple text-adventure games in groups of 2-4 people, and answer some questions about them. We are going to play two games:

1. [Bronze](http://iplayif.com/?story=http://www.ifarchive.org/if-archive/games/zcode/Bronze.zblorb).  This is a text adventure game in the style of classic games like [Zork](http://textadventures.co.uk/games/view/5zyoqrsugeopel3ffhz_vq/zork) and other [Infocom games](https://en.wikipedia.org/wiki/Classic_Text_Adventure_Masterpieces_of_Infocom).  

2. [AI Dungeon 2](https://colab.sandbox.google.com/github/nickwalton/AIDungeon/blob/master/AIDungeon_2.ipynb). This is a modern a machine-generated text adventure.  It uses a neural network based language model called [GPT-2](https://openai.com/blog/better-language-models/).

## Bronze: A Classic Text Adventure

The parser for Bronze has a limited vocabulary.  This cheatsheet should guide to what commands are allowable in text adventure games:

<center>
<img src="play-if-card.png" class="img-responsive"/>
</center>

Helpfully, the very first interaction with Bronze is a question asking you ``Have you played interactive fiction before? >``.  We recommend responding ``no``.  If you do, then Bronze will display a bunch of userful hints about what commands you can use at each location in the game.

While you're plaing this game, please do the following:
* __Draw a map of the game__ as you go.  Drawing maps was a normal practice in classific interactive fiction games.  We'll ask you to take a snapshot of your map and turn it in via Gradescope at the end of the class period.
* __Keep track of failed commands__.  Write down or copy-and-paste a list of any commands that you try that the game fails to understand.


## AI Dungeon 2

Unlike classic text adventures, AI Dungeon will let you enter any command that you want to.  Rather than having an internal representation of the game as a map with locations and objects, it generates its descriptions on the fly, based on your commands and what has been described so far.  On the one hand, this demonstrates the power of modern neural language models.  On the otherhand, it removes some of elements that are important to game play.  For instance, if you come across a locked door in AI Dungeon, you can just say ``Pick the key up off the ground and unlock the door``.  Just by saying it, you will have created a key from nothing.  

We recommend starting out with a game in the __fantasy__ setting.  Play along as if you are a character from  Lord of the Rings.

While you're plaing this game, please do the following:
* __Keep track of bad responses__.  Sometimes the game fails to understand your intent, and sometimes it generates illogical responses.  Once you see this, copy-and-paste what you said, and how the game responded.  Write down why you think it was a bad reponse.
* __Try to force the game off into a different setting__.  The game starts off as a Dungeons and Dragons-style adventure.  You can get it off track quickly by not playing to character type.  If you manage to make the game take a funny turn that breaks the theme, copy-and-paste it to share with us.

<!--
You are Bob, a wizard living in the kingdom of Larion. You have a staff and a spellbook. You finish your long journey and finally arrive at the ruin you've been looking for. You look around and see that it's not much different than when you left it.

You walk through the ruins and eventually find yourself in a large room with many doors on all sides. You knock on one of them and hear someone opening it up. It is none other than Elana!

> "Hello, darling!  How are you?  Shall we go to brunch?"

"Hi, I'm fine!" Elana says as she walks out of the door.
"I was just about to ask how you were doing."
"Oh, well I'm good. What do you want?"
"Well... I mean..."

> "Mimosas!"

"Mimosas!" Elana gasps.
"Yeah, they're delicious! And I love brunch!"
"Brunch sounds great! Let me get us some food then!"
"Sure thing, let's go!"

> Make a reservation on OpenTable and hale an Uber.

You quickly order up a table for two at OpenTable and book an uber to take you there. When you arrive, you find that it's indeed brunch time. The place looks very fancy, but the waiters don't seem to be wearing uniforms or anything else that would give away their identity.

> Tell the maitre d' that we have a reservation.

"We have a reservation here," you say.
"Ah, yes, I remember seeing you on this list. Well then, if you'll excuse me, I must inform my superior that we have a reservation."
-->

## Questions
1. How many of the rooms did you explore in Bronze? This is tracked for you in the title bar at the top of the game.  Did you solve any of puzzles?
1. When you tried a command and it failed, where you able to re-issue a different command that the game could understand?  If so, give an example.  If not, what did you do instead?
2. What do you perceive are the challenges in designing a text adventure game as compared to non-interactive fiction?
3. While AI Dungeon 2 is fun to play, it clearly gets a lot of things wrong. What is the system lacking as compared to hand-crafted games?
4. If you had near-infinite resources (for GPUs, to build datasets, to collect human annotations, etc.), how would you propose to improve AI Dungeon to make it more fun to play?



