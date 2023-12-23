---
layout: default-2022
img: listening.png
img_link: https://xkcd.com/1807/
caption: Intent - Buy it now 
title: Use GPT-3 for Intent Determination
type: in-class
active_tab: homework
release_date: 2022-01-25
due_date: 2022-01-31 23:59:00EST
materials:
    - 
        name: GPT3 for Intent Determination.ipynb
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/intent-detection-2/GPT3_for_Intent_Determination.ipynb
submission_link: https://www.gradescope.com/courses/354158/assignments/1804570
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



In Class Activity: Intent Determination with GPT-3
=============================================================

Today in class you will use the data you created for **intent determination** in text adventure games to train a GPT-3 model to perform the intent determination.  

In our first version of the Text Adventure Game, we had a simple keyword-based method of handling the player's intent.  The parser implemented a function called `get_player_intent` that took in a player's command and then decided which of the following actions a player was trying to accomplish:
* **Move** to a new location
* **Examine** an object
* **Get** an object
* **Drop** an object
* Perform a **special** action using an object
* Check the player's **inventory**
* **Redescribe** the scene
* Perform a **sequence** of actions

The Colab Notebook will guide you through how to train a model to perform intent detection using the data we collected

### What to do

1. Open the [GPT3 for Intent Determination.ipynb](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/intent-detection-2/GPT3_for_Intent_Determination.ipynb).
2. Choose `Runtime > Run all`.
3. The Colab Notebook will ask "Permit this notebook to access your Google Drive files?".  You should grant it permission.
3. You may have to get your Intent annotation data from last time from Gradescope
4. Scroll down to the "START HERE: Create a Prompt for Intent Detection" section of the notebook
5. Complete the interactive annotation activity.  It will save a JSON file to your Google drive.
6. Please submit your work to [Gradescope]({{page.submission_link}}) by {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 


