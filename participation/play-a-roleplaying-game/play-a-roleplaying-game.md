---
layout: default
img: mausritter.png
img_link: https://mausritter.com
caption: Mausritter, Sword-and-whiskers role-playing
title: Play A Roleplaying Game
type: participation
active_tab: homework
release_date: 2024-01-18
due_date: 2024-01-23 13:45:00EST
materials:
    - 
        name: Labyrinth The Adventure Game
        url: https://www.amazon.com/Jim-Hensons-Labyrinth-Adv-Game/dp/1916011551/?th=1
    - 
        name: Mausritter (Boxed Set)
        url: https://www.exaltedfuneral.com/products/mausritter-boxed-set?variant=40501558444134
    - 
        name: Or a free version of Mausritter
        url: https://losing-games.itch.io/mausritter
submission_link: https://www.gradescope.com/courses/704268/assignments/3958911/
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
This is the in-class activity for {{ page.release_date | date: "%A %B %-d" }}.
</div>
{% elsif page.type == "participation" %}
<div class="alert alert-info">
This activity counts towards your participation grade. It is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% endif %}

{% if page.materials %}
<div class="alert alert-info">
The materials that you will need for this activity are:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}



Participation Activity: Play A Roleplaying Game
=============================================================

As a fun homework assignment, I'm asking everyone to try playing a roleplaying game with your friends or your classmates.  The goal of this assignment is to ensure that everyone has experience with classic pen-and-pencil interactive fiction. You have two options for which game to play.  You can either play 

* Labyrinth The Adventure Game, which is based on the movie Labyrinth (1986) which is a cult classic from when I was a kid.  
* Mausritter, which is a Dungeons and Dragons like game, but you play as mice.  Mausritter is a great example of a kind of indie role playing game from a movement called the ["Old School Renaissance"](https://en.wikipedia.org/wiki/Old_School_Renaissance).

Both of these games are excellent introductions to RPGs and are friendly to newcomers.   They both have beautiful artifacts.  Labyrinth is a lovely book that you can buy on Amazon with one-day delivery. Mausritter has a stunning boxed set for sale on Exalted Funeral. Delivery will take longer for Mausritter, but you can download a digital copy for free on itch.io. 

If you'd like to lead a game or play with classmates, please use the class discussion forum to arrange a time to play. If you have experience with RPGs, especially as a game master, I'd love it if you could to lead a game.  

As you're playing the game think about the following things:
* What sort of things does the game master do in the game? Hint: game masters are typically responsible for describing the setting, and playing the role of the 'non-player characters' and monsters.
* How could large language models be used to help a game master generate compelling descriptions and dialogue? Do you think an LLM could replace a GM?
* How would you implement the rules of the game like dice mechanics for combat, ability checks, and inventory management? 

We'll ask you to answer a few questions on Gradescope:
* What game did you play?
* Was this your first time playing a role playing game?
* Who did you play with?
* Describe your character
* Upload your character sheet
* Describe the gaming session
* What sort of things does the game master do in the game?
* How do you think an AI system could be used to aid or enhance the game playing experience?

