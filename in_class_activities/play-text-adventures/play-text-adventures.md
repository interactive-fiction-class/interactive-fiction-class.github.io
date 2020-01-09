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


## Instructions

Today in class, you will play a couple text-adventure games, and answer some questions about them. 

1. Play the text adventure game [Bronze](http://iplayif.com/?story=http://www.ifarchive.org/if-archive/games/zcode/Bronze.zblorb), either until you win it or you have spent over an hour on it.  Draw a map of the game as you go.
2. Play [AI Dungeon 2](https://colab.sandbox.google.com/github/nickwalton/AIDungeon/blob/master/AIDungeon_2.ipynb), a machine-generated text adventure.
3. Answer the quetions in the following section.



### Questions
1. Were you able to beat Bronze?
2. What do you perceive are the challenges in designing a text adventure game as compared to non-interactive fiction?
3. While AI Dungeon 2 is fun to play, it clearly gets a lot of things wrong. What is the system lacking as compared to hand-crafted games?
4. If you had near-infinite resources (for GPUs, to build datasets, to collect human annotations, etc.), how would you propose to improve AI Dungeon to make it more fun to play?



