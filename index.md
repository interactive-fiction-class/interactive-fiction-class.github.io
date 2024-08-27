---
title: CIS 7000-001 - Interactive Fiction and Text Generation - University of Pennsylvania
layout: default
img: heroes_journey.png
active_tab: main_page 
---

<!--
<div class="alert alert-warning" markdown="1">
Want to join the class, but didn't attend the first lecture? Here are the steps to follow:
1. [Get a permit by signing yourself up for CIS 700-001 via the waitlist system](https://forms.cis.upenn.edu/waitlist/index.php).  
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
<div class="alert alert-danger">
The in-class activity for {{ page.release_date | date: "%A %b %-d" }} will be to <a href="{{page.url}}">{{ page.title }}</a>.  
</div>
<!-- Other participation activity -->
{% elsif page.type == "participation" %}
<div class="alert alert-info">
The participation activity <a href="{{page.url}}">{{ page.title }}</a> is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-success">
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
<!--
<div class="alert alert-success" markdown="1">
First day of class is Thursday, January 13, 2022 at 1:45pm-3:15pm Eastern. It will take place virtually. Here is the [Zoom link](https://upenn.zoom.us/j/95868341588?pwd=a0NvbkhtUEdYTTk5d0Vmc2VvcHJrUT09). We look forward to seeing you there!
</div>
-->

Course number
: CIS 7000-001 - Interactive Fiction and Text Generation 

Prerequisites 
: At least one of the following courses
: CIS 4190/5190
: CIS 5200
: CIS 4210/5210
: CIS 5220
: CIS 5300

Course Description
: We know now that artificial intelligence (AI) can play chess or even Go, but can AI play text adventure games (also known as interactive fiction)? What about roleplaying games like Dungeons & Dragons? In this course, we will be looking at the subfields of automated story generation (teaching computers to tell stories), interactive fiction (teaching computers to play through stories), and their intersection (teaching computers to tell and then play through the stories). This class will teach you about computational creativity and help develop your skills in natural language processing and cognitive modeling. 

Learning Objectives
* Understanding the challenges of creating text-based games and automatically generating stories.
* Implement and appraise the value of different technologies (Neural Language Models, Dialogue Systems, Scripts, Planning, and Commonsense Reasoning) in story generation/interactive fiction playing.
* Argue for the appropriate components of a working story generation system or interactive fiction--playing system.
* Create your own story generation system or interactive fiction--playing system.




<!-- 
: This class will cover several areas.
* Text Adventure Games - How they are implemented and how we can build agents that automatically solve them.
* Common-sense Reasoning - TODO
* Narrative Understanding - Extracting narrative structure (event schemas) from text
* Text Generation - Generating natural-sounding text that follows a desired style, narrative arc, or other attribute.
* Chatbots / Dialog Systems - TODO
-->

Website
: [interactive-fiction-class.org](http://interactive-fiction-class.org/)

Instructors
: [Chris Callison-Burch](https://www.cis.upenn.edu/~ccb/)

TAs
: [Andrew Zhu](https://zhu.codes)
: Anson Runsheng Huang
: Kyle Jaewoo Song

Discussion Forum
: [Ed Discussion](https://edstem.org/us/courses/50468/discussion/)

Time and Place
: Spring 2024, Tuesdays & Thursdays from 1:45-3:15pm EST in Towne 327
: First day of class is January 18, 2024
: Last day of class is April 30, 2024
: Final project presentations will be held on May 7th from 9am-noon in Towne 100.

Office Hours (see the [Staff](/staff.html) page for office hour locations)
: Chris - Thursdays from 3:15-5pm in Towne 280
: Andrew - [By appointment](https://calendar.app.google/h3cWzezazMe9c8a69)
: Anson - Fridays noon-2pm on [Zoom](https://upenn.zoom.us/j/4447479378)
: Kyle - Mondays 4-6pm in the Levine 6th floor bump


Course Materials
: There is no textbook for this course, but you will be required to puchase a varitey of materials including games, software, and API credits. If any of these are prohibitively expensive for your budget, please let the instructor know.

Games
: [Labyrinth The Adventure Game](https://www.amazon.com/Jim-Hensons-Labyrinth-Adv-Game/dp/1916011551/) - $35 on Amazon
: [Action Castle](http://www.memento-mori.com/pdf/parsely-preview-n-play-edition) - Free (you can optionally buy it in the rad [Parsley book in print](http://www.memento-mori.com/books/parsely-book) or [PDF](http://www.memento-mori.com/pdf/parsely-pdf)) - $20-30


Materials 
: [ChatGPT Plus subcription](http://chat.openai.com) - $20/month
: [Midjourney subscription](https://www.midjourney.com/home) - $10/month 


<!--
: $20-30 [Parsley](http://www.memento-mori.com/parsely-products/) by Jared A Sorensen
Books
: (Optional) [So You Want To Be A Game Master: Everything You Need to Start Your Tabletop Adventure for Dungeons and Dragons, Pathfinder, and Other Systems](https://www.amazon.com/gp/product/1645679152/ref=ox_sc_act_title_1?smid=ATVPDKIKX0DER&psc=1) - $25 on Amazon

: [$10](http://www.drivethrurpg.com/product/108028/Dungeon-World)-[$25](https://www.burningwheel.com/dungeon-world-1/) [Dungeon World](https://dungeon-world.com/) by Sage LaTorra and Adam Koebel
: Optional $31 [Dungeon Master's Guide - Dungeons & Dragons 5th edition Core Rulebook](https://www.amazon.com/Dungeons-Dragons-Dungeon-Rulebook-Roleplaying/dp/0786965622/) by Wizards of the Coast
-->

Grading
: There will be six homeworks and a final project. In addition, you will be required to present academic papers in class.
* 15% Paper Presentations + Class Participation
* 55% Homeworks (6 in total)
* 30% Final Project

Paper Presentations
: Over the course of the semester, each student must prepare one or more 10-15 minute presentations on a research paper relevant to the course. Since these presentation will be a substantial component of the learning experience in the class, slides must be prepared and emailed to us at least 72 hours in advance of the lecture they will be presented in (e.g., by 3PM on the Monday before the presenation date), so that we can provide feedback on them. Failure to send us the slides ahead of time will result in a grade penalty on the presentation. 

Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments, and teams of 3-5 for the final project.

Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days only apply to the homeworks. They cannot be used on the final project, which must be finished by the final day of class.  Late days may not be used for paper presentations.**
