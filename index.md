---
title: CIS 700-008 - Interactive Fiction and Text Generation - University of Pennsylvania
layout: default
img: heroes_journey.png
active_tab: main_page 
---


<div class="alert alert-info" markdown="1">
If you're interested in joining this course (CIS 700-008), [you can sign yourself up for the waitlist](https://forms.cis.upenn.edu/waitlist/index.php).  Note that the number of spots will be limited. 
</div>



<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
<div class="alert alert-info">
<a href="{{page.url}}">{{ page.title }}</a> has been released.  
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
{% endfor %}
<!-- End alert for upcoming homework assignments -->



<div class="alert alert-success" markdown="1">
A great example of what you could build if you take this class is the [AI Dungeon](https://play.aidungeon.io/), which is an interactive fiction game  that was developed by a student at BYU using [Open AI's GPT-2](https://openai.com/blog/better-language-models/) large scale language model.
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
: [Mailing List](https://groups.google.com/d/forum/cis700-2019-iftg)

Time and place
: Spring 2019, Thursdays from 1:30-4:30pm (Towne 327 Active Learning Classroom)

Office hours
: by appointment

<!--
Textbooks
: $20-30 [Parsley](http://www.memento-mori.com/parsely-products/) by Jared A Sorensen
: [$10](http://www.drivethrurpg.com/product/108028/Dungeon-World)-[$25](https://www.burningwheel.com/dungeon-world-1/) [Dungeon World](https://dungeon-world.com/) by Sage LaTorra and Adam Koebel
: Optional $31 [Dungeon Master's Guide - Dungeons & Dragons 5th edition Core Rulebook](https://www.amazon.com/Dungeons-Dragons-Dungeon-Rulebook-Roleplaying/dp/0786965622/) by Wizards of the Coast
-->

Grading
: TBD. Below is a sample grading rubric, which will change.
: There will be three homeworks and a final project. In addition, you will be required to present a paper from the required reading in class.
* 10% Paper presentation
* 45% Homeworks 
* 45% Final project

Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments, and teams of 2-4 for the final project. 

Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. 
