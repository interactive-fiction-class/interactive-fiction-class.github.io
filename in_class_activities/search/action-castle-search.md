---
layout: default
img: DFS.png
img_link: https://xkcd.com/761/
caption: DFS is not useful for all occasions 
title: Search Algorithms for Action Castle
type: in-class
active_tab: homework
release_date: 2022-01-15
due_date: 2022-02-21 23:59:00EST
materials:
    - 
        name: Search Algorithms for Action Castle.ipynb
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/search/Search_Algorithms_for_Action_Castle.ipynb
submission_link: https://www.gradescope.com/courses/354158/assignments/1861402
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



In Class Activity: Search Algorithms for Action Castle
=============================================================

Today in class you will implement a breadth-first search (BFS) algorithm for our first Text Adventure Game, Action Castle. To use search algorithms, we need to define 6 elements:
* States
* An Initial State
* Actions
* Transitions
* Path Cost
* A Goal Test

We'll walk through how to do define these properties for our the Text Adventure Game that we implemented in HW1, and then we'll use BFS to find the best sequence of commands in order to complete the game.


### What to do 

1. Open [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Implement the following functions:
* `game.get_state()`
* `parser.get_available_actions()`
* `goal_test()`

3. Please submit your work to [Gradescope]({{page.submission_link}}) by {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 


