---
layout: default-2022
img: Scheherazade.jpg
caption: Queen Scheherazade, the storyteller from One Thousand and One Nights (Arabian Nights)
title: Plot Graph Generation
type: Homework
number: 3
active_tab: homework
release_date: 2022-02-03
due_date: 2022-02-15 23:59:00EST
materials:
    - 
        name: Colab Notebook
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/plots/HW3_plot.ipynb
submission_link: https://www.gradescope.com/courses/354158/assignments/1829348
readings:
    -
      title: Crowdsourcing Narrative Intelligence
      authors: Boyang Li, Stephen Lee-Urban, Darren Scott Appling, and Mark O. Riedl
      url: http://www.cogsys.org/journal/volume2/article-2-4.pdf
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

In the paper [Crowdsourcing Narrative Intelligence](http://www.cogsys.org/journal/volume2/article-2-4.pdf), Li et al. created the Scheherazade algorithm to generate plot graphs from a collection of crowdsourced stories.
Head over to the [Colab Notebook](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/plots/HW3_plot.ipynb) for more information on what you'll be doing.

## What to Submit

1. An IPython notebook called `HW3-plot.ipynb` that runs your plot graph implementation.
2. A document (doc/docx, txt, pdf) that has your answers to the questions found at the end of the notebook.
3. **Two** graph files: one named `plotgraph.html` that is your final (initialized, pruned, & improved) plot graph using your clusters, one named `gold.html` using the clusters from Part 2.

If you decide to do the extra credit, please submit a file for that graph as well: `ec.html`. You may include your answers to the questions in your document under a section labeled "Extra Credit".

Submissions should be done on [Gradescope]({{page.submission_link}}).

## Grading
<div class="alert alert-warning" markdown="1">
- Implementation of the Scheherazade algorithm - 15 points
- Answers to questions - 10 points
- Graph files - 5 points
- Extra Credit - 5 points
</div>

{% if page.readings %} 
## Required Reading
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
