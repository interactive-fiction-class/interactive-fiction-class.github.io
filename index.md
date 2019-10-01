---
title: CIS 700 - Interactive Fiction and Text Generation - University of Pennsylvania
layout: default
img: play-if-card.png
active_tab: main_page 
---

<!--

<div class="alert alert-danger" markdown="1">
If you're interested in joining the course, [you can sign yourself up for the waitlist](https://forms.cis.upenn.edu/waitlist/index.php).  Note that the number of spots will be limited. 
</div>

-->


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







Course number
: CIS 700 - Interactive Fiction and Text Generation 

Website
: [interactive-fiction-class.org](https://interactive-fiction-class.org/)

Instructors
: [Daphne Ippolito](https://www.seas.upenn.edu/~daphnei/)
: [Chris Callison-Burch](https://www.cis.upenn.edu/~ccb/)

Discussion Forum
: [Piazza](http://piazza.com/upenn/fall2019/cis521)

Time and place
: Fridays xxx TBD

Office hours
: by appointment

Textbooks
: $20-30 [Parsley](http://www.memento-mori.com/parsely-products/) by Jared A Sorensen
: [$10](http://www.drivethrurpg.com/product/108028/Dungeon-World)-[$25](https://www.burningwheel.com/dungeon-world-1/) [Dungeon World](https://dungeon-world.com/) by Sage LaTorra and Adam Koebel
: Optional $31 [Dungeon Master's Guide - Dungeons & Dragons 5th edition Core Rulebook](https://www.amazon.com/Dungeons-Dragons-Dungeon-Rulebook-Roleplaying/dp/0786965622/) by Wizards of the Coast


Grading
: TBD


Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments, and teams of 3-5 for the final project. 

Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. 

