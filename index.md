---
title: CIS 700-008 - Interactive Fiction and Text Generation - University of Pennsylvania
layout: default
img: heroes_journey.png
active_tab: main_page 
---

<!--
<div class="alert alert-warning" markdown="1">
Want to join the class, but didn't attend the first lecture? Here are the steps to follow:
1. [Get a permit by signing yourself up for CIS 700-008 via the waitlist system](https://forms.cis.upenn.edu/waitlist/index.php).  
2. [Do the for-credit in-class assignment from the first lecture](http://interactive-fiction-class.org/in_class_activities/play-text-adventures/play-text-adventures.html).
3. [Listen to recording of the first lecture](https://upenn.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=8b5f2734-0738-4f52-90f5-ab3c01236b7c) and [look over the slides](http://interactive-fiction-class.org/slides/text-adventure-games.pdf).
4. [Complete the first homework assignment before class on Thursday](http://interactive-fiction-class.org/homeworks/text-adventure-game/text-adventure-game.html).
</div>
-->

<!--
<div class="alert alert-success" markdown="1">
[Post your game here.](https://docs.google.com/document/d/1XpBEevYpHvLjCr-3CkAhERN_GPHsjNmkPo-Wf9KjxDs/edit?usp=sharing)
</div>
-->

<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
{% if page.type == "in-class" %}
<!-- In class activity -->
<div class="alert alert-info">
The in-class activity for {{ page.due_date | date: "%A %b %-d" }} will be to <a href="{{page.url}}">{{ page.title }}</a>.  
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
<a href="{{page.url}}">{{page.type}} {{page.number}}: {{page.title}}</a> has been released.  
{% if page.deliverables %}
The assignment has multiple deliverables.
<ul>
{% for deliverable in page.deliverables %}
<li>{{ deliverable.due_date | date: "%b %-d, %Y" }} - {{deliverable.description}}.</li>
{% endfor %}
</ul>
{% else %}
It is due before {{ page.due_date | date: "%I:%M%p" }} on {{ page.due_date | date: "%A, %B %-d, %Y" }}.
{% endif %}
</div>
{% endif %}
{% endif %}
{% endif %}
{% endfor %}
<!-- End alert for upcoming homework assignments -->


<!--
<div class="alert alert-success" markdown="1">
A great example of what you could build if you take this class is the [AI Dungeon](https://play.aidungeon.io/), which is an interactive fiction game  that was developed by a student at BYU using [Open AI's GPT-2](https://openai.com/blog/better-language-models/) large scale language model.
</div>
-->
<div class="alert alert-success" markdown="1">
This course will be offered in Spring 2022!  It will be held on Tuesdays and Thursdays from 1:45pm-3:15pm Eastern.  We’ll be handling the permits for that class via the [CIS Waitlist System](https://forms.cis.upenn.edu/waitlist/index.php) which will open around Nov 23, after the early registration period. 
</div>

Course number
: CIS 700-008 - Interactive Fiction and Text Generation 

Course Description
: In this course, we will study how natural language processing is used to develop interactive and creative text applications. We will first cover text adventure games, which are interesting for artificial intelligence research since to succeed at a such games an AI agent needs to understand language, perform common-sense reasoning, and interact with objects in a constrained world.   We cover approaches to interpreting user input via a natural language understanding component called the "parser".  We will discuss various strategies for representing a world and modeling how it changes based on user interaction. Next, we will also cover topics like common-sense reasoning tasks, and extracting of narrative structure from stories. Finally, we will discuss natural language generation, both in the context of dialog agents and story generation.  We will touch upon human-computer interaction, biases in language models, and other topics.





<!-- 
: This class will cover severl areas.
* Text Adventure Games - How they are implemented and how we can build agents that automatically solve them.
* Common-sense Reasoning - TODO
* Narrative Understanding - Extracting narrative structure (event schemas) from text
* Text Generation - Generating natural-sounding text that follows a desired style, narrative arc, or other attribute.
* Chatbots / Dialog Systems - TODO
-->

Website
: [interactive-fiction-class.org](http://interactive-fiction-class.org/)

Instructors
: [Daphne Ippolito](https://www.seas.upenn.edu/~daphnei/)
: [Chris Callison-Burch](https://www.cis.upenn.edu/~ccb/)

Discussion Forum
: [Piazza](https://piazza.com/upenn/spring2020/cis700008)

Time and place
: Spring 2019, Thursdays from 1:30-4:30pm in Towne 327 (The Hartman Family Technology Entrepreurship Forum)
: First day of class is January 16, 2020
: Last day of class is April 23, 2020

Office hours
: Daphne - Thursdays after class
: Chris - by appointment

<!--
Textbooks
: $20-30 [Parsley](http://www.memento-mori.com/parsely-products/) by Jared A Sorensen
: [$10](http://www.drivethrurpg.com/product/108028/Dungeon-World)-[$25](https://www.burningwheel.com/dungeon-world-1/) [Dungeon World](https://dungeon-world.com/) by Sage LaTorra and Adam Koebel
: Optional $31 [Dungeon Master's Guide - Dungeons & Dragons 5th edition Core Rulebook](https://www.amazon.com/Dungeons-Dragons-Dungeon-Rulebook-Roleplaying/dp/0786965622/) by Wizards of the Coast
-->

Grading
: There will be five homeworks and a final project. In addition, you will be required to present a paper in class.
* 10% Paper Presentation
* 5% Class Participation 
* 45% Homeworks 
* 40% Final project

Paper Presentations
: Over the course of the semester, each student must prepare a 10-15 minute presentation on a research paper relevant to the course. Since these presentation will be a substantial component of the learning experience in the class, slides must be prepared and emailed to us at least 72 hours in advance of the lecture they will be presented in (eg. by 3PM on the Monday before the presenation date), so that we can provide feedback on them. Failure to send us the slides ahead of time will result in a grade penalty on the presentation. 

Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments, and teams of 2-4 for the final project. 

Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days only apply to the homeworks. They cannot be used on the final project, which must be finished by the final day of class.  Late days may not be used for paper presentations.**
