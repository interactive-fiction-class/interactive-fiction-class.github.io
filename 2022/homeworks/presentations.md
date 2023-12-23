---
layout: default-2022
img: presentation.jpg
img_link: https://www.learner.org/wp-content/uploads/2020/05/two-bit-circus-lesson-plans-unit-elementary-school-engineering-towers-group-presentation-1298x672.jpg
title: Paper Presentation
active_tab: homework
release_date: 2022-01-21 
attribution: This homework was developed by Lara Martin and Chris Callison-Burch for their Interactive Fiction and Text Generation class (CIS 700-008) which was taught at the University of Pennsylvania in Spring 2022.
submission_link: https://www.gradescope.com/courses/354158/assignments/1782400

---

<div class="alert alert-info">
This assignment is due the Monday of the week of your presentation before 3PM EST. 
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


{{page.title}}
=============================================================

# Instructions

Once you are assigned a group and paper, you will be told the approximate date when your presentation will be. (Since the lecture material moves around as the course progresses, the presentation dates might move as well.)


Your presentation should be about 15 minutes long + a few minutes for questions. Give each member of your group equal time for presenting (e.g., if you have 3 people, each person gets 5 minutes)

Your talk should include:
- a summary of the paper,
- what the strengths of the paper are,
- what the weaknesses of the paper are, and
- how it relates to story generation and interactive fiction playing or generation
   - if it's not about either, how could it be used for making stories or interactive fiction?
   - if it's about story generation, how could it be used for creating or playing interactive fiction?
   - if it's about interactive fiction, how could it be used for story generation?

Tip: Read the paper assigned to your group and *discuss it with each other* before making your slides.

You are strongly encouraged to set up an appointment to go over your slides with Artemis, Chris, Lara, or Liam before you give your in-class presentation.

Slides will be due Monday at 3PM on the week of your presentation (with the exception of the people presenting for Module 1, who we will allow you to give us the slides the day before and will be more lenient in grading your presentation since we won't have much time to go over it with you ahead of time).


## What to submit

1. <a href="{{page.submission_link}}">A Powerpoint (ppt or pptx) file or a link to where we can find the slides online (e.g., Google Slides).</a>


{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
