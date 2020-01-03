---
layout: default
img: File:Zork_I_box_art.jpg
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Zork, an early intractive fiction game released in 1977.
title: CIS 521 Homework 1 "Play a Text-Adventure Game"
active_tab: homework
release_date: 2020-01-01 14:59:00EDT
due_date: 2020-01-23 14:59:00EDT
materials:
    - 
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


<div class="alert alert-info" markdown="span">
Links to tutorials and other Python resources are posted on the [schedule page](/lectures.html) in the Python Review parts.</div>


Homework 1: Play a Text Adventure Game
=============================================================


## Instructions

In this home, you will play a couple text-adventure games, and answer some questions about them. This is **not** a partner homework; you should complete it on your own.

1. Play the text adventure game [Bronze](http://iplayif.com/?story=http://www.ifarchive.org/if-archive/games/zcode/Bronze.zblorb), either until you win it or you have spent over an hour on it.
2. Play [AI Dungeon 2](https://colab.sandbox.google.com/github/nickwalton/AIDungeon/blob/master/AIDungeon_2.ipynb), a machine-generated text adventure.
3. Answer the quetions in the following section.

### Questions
1. Were you able to beat Bronze?
2. What do you perceive are the challenges in designing a text adventure game as compared to non-interactive fiction?
3. While AI Dungeon 2 is fun to play, it clearly gets a lot of things wrong. What is the system lacking as compared to hand-crafted games?
4. If you had near-infinite resources (for GPUs, to build datasets, to collect human annotations, etc.), how would you propose to improve AI Dungeon to make it more fun to play?


## What to submit

Submit a PDF containing the question answers.
