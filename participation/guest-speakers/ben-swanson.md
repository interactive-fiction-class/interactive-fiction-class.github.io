---
layout: default
img: ubisoft.jpg
img_link: https://news.ubisoft.com/en-us/article/7Cm07zbBGy4Xml6WgYi25d/the-convergence-of-ai-and-creativity-introducing-ghostwriter
caption: Ubisoft's Ghostwriter
title: think of questions for our guest speaker Ben Swanson
type: participation
speaker: Ben Swanson
active_tab: homework
release_date: 2024-02-17
due_date: 2024-03-12 13:45:00EST
materials:
    - 
        name: Ubisoft's Ghostwriter
        url: https://news.ubisoft.com/en-us/article/7Cm07zbBGy4Xml6WgYi25d/the-convergence-of-ai-and-creativity-introducing-ghostwriter
    -
        name: Generating Video Game Scripts with Style
        url: https://aclanthology.org/2023.nlp4convai-1.11/
    -
        name: Story Centaur&colon; Large Language Model Few Shot Learning as a Creative Writing Tool
        url: https://aclanthology.org/2021.eacl-demos.29/
submission_link: https://www.gradescope.com/courses/704268/assignments/4120872
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



Participation Activity: Research Our Guest Speaker
=============================================================

We'll have several guest speakers this semester, including game designers, AI professors and industrial researchers.  For each speaker, you should learn a bit about them before they give their talk, and prepare at least one question that you'd like us to ask them to hear their insights about our course topics. 

You should [submit your question to gradescope]({{page.submission_link}}), along with a short bio for the speaker and the websites that you used to research them  before class begins.

On {{ page.due_date | date: "%A, %B %-d, %Y" }} our guest speaker will be **{{ page.speaker }}**.
