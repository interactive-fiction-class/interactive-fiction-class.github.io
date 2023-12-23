---
layout: default-2022
img: ATOMIC.png
img_link: https://www.researchgate.net/publication/328685565_ATOMIC_An_Atlas_of_Machine_Commonsense_for_If-Then_Reasoning
caption: "ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning"
title: COMET-ATOMIC Schema
type: Homework
number: 5
active_tab: homework
release_date: 2022-03-15
due_date: 2022-03-21 23:59:00EST
materials:
    - 
        name: Colab Notebook
        url: https://colab.research.google.com/drive/1EF4Twf1Iuhvsu5UAykeMifYz6wlXw3Y5?usp=sharing
submission_link: https://www.gradescope.com/courses/354158/assignments/1928540
readings:
    -
      title: "(COMET-)ATOMIC-2020: On Symbolic and Neural Commonsense Knowledge Graphs"
      authors: Jena D. Hwang, Chandra Bhagavatula, Ronan Le Bras, Jeff Da, Keisuke Sakaguchi, Antoine Bosselut, and Yejin Choi
      url: https://arxiv.org/abs/2010.05953
    -
      title: "ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning"
      authors: Maarten Sap, Ronan Le Bras, Emily Allaway, Chandra Bhagavatula, Nicholas Lourie, Hannah Rashkin, Brendan Roof, Noah A. Smith, and Yejin Choi
      url: https://arxiv.org/abs/1811.00146
    -
      title: "COMET: Commonsense Transformers for Automatic Knowledge Graph Construction"
      authors: Antoine Bosselut, Hannah Rashkin, Maarten Sap, Chaitanya Malaviya, Asli Celikyilmaz, and Yejin Choi
      url: https://aclanthology.org/P19-1470/
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

[ATOMIC](https://arxiv.org/abs/1811.00146) is a crowdsourced commonsense knowledge graph that is used for state-of-the-art commonsense reasoning tasks. In this homework, you will be working with [COMET-ATOMIC-2020](https://arxiv.org/abs/2010.05953), a BART transformer model finetuned on an updated version of the original ATOMIC. You will take the information provided to you by COMET-ATOMIC-2020 and structure it into a schema used to track the state of a story.

Go to the colab notebook link above for more information.


## What to Submit

1. An IPython notebook called `HW5_Schemas.ipynb` that runs your COMET-ATOMIC schema. **Important: Save the output for the Story Tracking Questions!**
2. A document (doc/docx, txt, pdf) that has **your schema explanation and the answers to the COMET-ATOMIC questions** found at the end of the notebook.


Submissions should be done on [Gradescope]({{page.submission_link}}).

## Grading
<div class="alert alert-warning" markdown="1">
* Code - 2 points
* Schema Diagram/Explanation - 2 points
* Story Tracking Questions - 15 points (3 pts each)
* COMET-ATOMIC Questions - 6 points (2 pts each)
</div>

{% if page.readings %} 
## Related Readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}

