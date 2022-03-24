---
layout: default
img: dialogue.png
img_link: https://xkcd.com/1423/
caption: Conversation 
title: Train GPT-3 to Perform Dialogue for NPCs
type: in-class
active_tab: homework
release_date: 2022-03-24
due_date: 2022-03-28 23:59:00EST
materials:
    - 
        name: Colab Notebook for training GPT3 on LIGHT Dialogue
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/dialogue/Fine-Tune_OpenAI_on LIGHT_Dialogues.ipynb
submission_link: XXX
readings:
    -
      title: How to Motivate Your Dragon&colon; Teaching Goal-Driven Agents to Speak and Act in Fantasy Worlds
      authors: Prithviraj Ammanabrolu, Jack Urbanek, Margaret Li, Arthur Szlam, Tim Rocktäschel, Jason Weston
      url: https://arxiv.org/pdf/2010.00685.pdf
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



In Class Activity: Train GPT-3 to Perform Dialogue for NPCs
=============================================================

Today in class you will train GPT-3 to perform dialogue for non-player characters in games.  We will use a different part of [Facebook's LIGHT dataset](https://parl.ai/projects/light/), which we previously used to generate descriptions for items and locations in our text adventure games.  


# Characters in LIGHT 


Characters have a description, a persona (a first person description of who they are and what their motivations might be), a character type (person, creature or object), a location (```in_room_id```) and an inventory (```carrying_objects```).

Here is an example of the Gravedigger character.
```python
light_environment['characters']['203']

{'base_form': ['gravedigger'],
 'carrying_objects': [890],
 'char_type': 'person',
 'character_id': 203,
 'corrected_name': 'gravedigger',
 'desc': 'You might want to talk to the gravedigger, specially if your looking for a friend, he might be odd but you will find a friend in him.',
 'ex_room_ids': [100, 349],
 'in_room_ids': [62],
 'is_plural': 0,
 'name': 'gravedigger',
 'orig_room_id': 349,
 'personas': ["I am low paid labor in this town. I do a job that many people shun because of my contact with death. I am very lonely and wish I had someone to talk to who isn't dead."],
 'wearing_objects': [],
 'wielding_objects': []}
 ```



### What to do

1. Open the [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Choose `Runtime > Run all`.
3. XXX


{% if page.readings %} 
## Related Readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}

