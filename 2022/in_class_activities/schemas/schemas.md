---
layout: default-2022
title: WordNet Schemas
img: wordnet.png
img_link: https://wordnet.princeton.edu/
type: in-class
active_tab: homework
release_date: 2022-03-03
due_date: 2022-03-10 23:59:00EST
materials:
    - 
        name: WordNetSchemas.ipynb
        url: https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/schemas/WordNetSchemas.ipynb
submission_link: https://www.gradescope.com/courses/354158/assignments/1905780
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
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% endif %}

{% if page.materials %}
<div class="alert alert-info">
The materials that you will need for this in-class activity are:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}



In Class Activity: WordNet Schemas
=============================================================

In this assignment, you will be getting hands-on experience with working with WordNet and manipulating the data.
Pretend that you (or, rather, your agent) are in the middle of playing a text adventure game. Different characters are asking for various items, but you don't have the exact items. You will be using WordNet to form schemas of your inventory items and going your representations to find the most similar item.



### What to do 

1. Download [{{page.materials[0].name}}]({{page.materials[0].url}}). OR Save a copy of the colab here: [https://colab.research.google.com/drive/17QRQgPwLiQW8qLvLJnAJC3gA_Fgm5MGM?usp=sharing](https://colab.research.google.com/drive/17QRQgPwLiQW8qLvLJnAJC3gA_Fgm5MGM?usp=sharing) (Select `File > Save a Copy in Drive` from the Colab menu)
2. Fill in the TODOs.
3. Submit your work to [Gradescope]({{page.submission_link}}) by {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 


