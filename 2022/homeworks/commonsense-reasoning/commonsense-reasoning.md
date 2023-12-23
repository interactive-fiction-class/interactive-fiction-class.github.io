---
layout: default-2022
img: storycloze.png
img_link: https://cs.rochester.edu/nlp/rocstories/
caption: Story Cloze is a task for predicting the right ending sentnece to a 5-sentence story.
title: Natural Language Understanding
type: Homework
number: 3
active_tab: homework
release_date: 2020-02-08
due_date: 2020-02-14 13:30:00EST
materials: 
    - 
       name: Python notebook for ROC Stories 
       url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/commonsense-reasoning/rocstories.ipynb
submission_link: TODO
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
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
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

# Instructions
In this homework, you will be experiment with the ROCSTories dataset, which consists of 5-sentence long stories. You will build a few classifiers for the Story Cloze task. The task involves predicting which of two candidate 5th sentences best ends a story.

You should walk through the [IPython Notebook here](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/commonsense-reasoning/rocstories.ipynb). It walks you through building a sentiment-based system for predicting the correct next ending as well as two neural network-based approaches that learn a classifier for the task.

You should create a writeup describing the experiments you conduct. We will be primarily grading you on this writeup, although you should also submit your code. Your writeup should include
* Your accuracy on the two validation sets and the 2016 test set using...
  - A sentiment-based classifier
  - A neural network trained only on the train set, as well as 2 variants.
  - A neural network trained in a supervised way on the validation set, as well as 2 variants.
* Descriptions of your approaches for each of the above methods/variants. Try to make your descriptions detailed enough that another student could reimplement your approach from them.
* An error analysis:
  - Find a couple examples your sentiment classifier gets wrong and discuss them.
  - Are there any examples that all of your classifiers get wrong? What do you notice about them?
  
### What parameters can your vary?
Here are some ideas:
* The learning rate and optimizer
* The number of training steps
* The number of layers and types of activation functions in the model architecture
* The batch size
* For the supervised model that trains on the validation set, can you also incorporate the unlabeled training data?

# What to submit
* A file containing your writeup, as either `report.pdf` or `report.md`.
* Your modified IPython notebook as `rocstories.ipynb`.





