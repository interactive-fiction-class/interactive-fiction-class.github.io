---
layout: default-2022
img: text-only-counterstrike.png
img_link: https://www.explainxkcd.com/wiki/index.php/91:_Pwned
caption: Text Adventure Games
title: Leaderboards for Object Properties and Intent Determination 
type: Extra Credit
number: 2
active_tab: homework
release_date: 2022-02-07 
due_date: 2022-02-21 23:59:00EST
readings:
---

<!-- Check whether the assignment is ready to release -->
{% capture today %}{{site.time | date: '%Y%m%d'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%Y%m%d'}}{% endcapture %}
{% if due_date < today %} 
<div class="alert alert-danger">

Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<!-- Check whether the assignment is up to date -->
{% capture this_year %}{{'now' | date: '%Y'}}{% endcapture %}
{% capture due_year %}{{page.due_date | date: '%Y'}}{% endcapture %}
{% if this_year != due_year %} 
<div class="alert alert-danger">
Warning: this assignment is out of date.  It may still need to be updated for this year's class.  Check with your instructor before you start working on this assignment.
</div>
{% endif %}
<!-- End of check whether the assignment is up to date -->


<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} at {{ page.due_date | date: "%I:%M%p" }} EST. 
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


{{page.type}} {{page.number}}: {{page.title}}
=============================================================

## Instructions

For this extra credit opportunity, we have created two leaderboards to create some friendly competition to see who can  build the best __object properties__ predictor extending what you did in [HW2](https://interactive-fiction-class.org/homeworks/generating-descriptions/generating-descriptions.html), and the best __intent determination__ module extending what you did for the [intent determination in-class activity](https://interactive-fiction-class.org/in_class_activities/intent-detection-2/intent-detection-2.html).


PLEASE NOTE THIS IS ABSOLUTELY OPTIONAL AND INTENDED TO BE FUN!! 👩‍💻🤖🤗

For each leaderboard the first place team will receive 1 point extra credit, the secondp place team will get 1/2 point extra credit, and the third place team will get 1/3 point extra credit. 


###  Object Properties Instructions


Instructions: The properties test data (attached below) is a json with keys the object ids, accompanied by object name, base form, and descriptions. You should submit a labels.txt file where each line contains the object id and predictions for each property in order: is_container, is_drink, is_food, is_gettable, is_surface, is_wearable, is_weapon.

* Download and classify: [`properties_test_data.json`](https://static.us.edusercontent.com/files/btCFF2ijC45dI92uaI3jLexz)
* What to submit: A file called `labels.txt` 
* Where to submit: [Gradescpope link](https://www.gradescope.com/courses/354158/assignments/1835401/submissions)


###  Intent Detection Instructions


: The intent test data (attached below) is a jsonl file, where each json line contains the location name and natural language command. You should submit a labels.txt file where each line contains the intent prediction your code made (e.g. get, direction, examine etc.). Please make sure you use the same order as the test data, i.e. your first line in labels.txt should be your prediction for the first line in the jsonl file, and so on. 

* Download and classify: [`intent_test_data.jsonl`](https://static.us.edusercontent.com/files/inN2r4GogXkzcAsssmambkv1)
* What to submit: A file called ` labels.txt`
* Where to submit: [Gradescpope link](https://www.gradescope.com/courses/354158/assignments/1836318/submissions)


