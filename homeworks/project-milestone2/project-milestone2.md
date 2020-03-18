---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: The Term Project
title: Project Milestone 1
type: Homework
number: 6
active_tab: homework
release_date: 2020-02-26
due_date: 2020-04-02 13:30:00EST
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

For the first milestone, we will have expected you to finish some of the initial work for your project, and written up your preliminary method and results. In particular you should be working on the following: 
* Make progress on the suggested next steps we left for you on your project proposal.
* Finish collecting any datasets that you need and making sure they are in a format that you know how to process.
* If your project involves doing text parsing with tools like AllenNLP, do some experiments to see whether the parsing you want to do is feasible. 
* If your project involves training/fine-tuning a neural network, try training some preliminary models and observing the outputs.
* If your project involves a user experience of some sort, create a real mock-up of the user interface (even if it's not fully functional/feature-complete yet).


## Attempt to answer a research question about text generation or interactive fiction
Create a new document which describes the progress you've made so far. Feel free to copy from your project proposal as appropriate. Your document should include the following sections:

1. __Project Description__: This should explain the main idea of your project and what you are trying to accomplish. If these have changed sincde the project proposal, this section should reflect those changes.
2. __Related work__: What previous research has been done on this research question? Give pointers to relevant research papers and websites.
3. __Method__: What are the steps to accomplish your project. This should describe both the steps you've done so far and the ones you plan to do.
4. __Data__: What data have you decided to use? What does it look like, and what are some potential problems with it?
5. __Evaluation__: What methodologies will you be using to evaluate the research question  you are answering or that the components of your interactive experience are working well? 
  * These can be things like accuracy, diversity metrics, BLEU score, success rate, human evaluate scores, etc. depending on your project.
6. __Preliminary Results__: Describe any results you have so far. These can include results for intermediate steps that build toward your main project goal. If you haven't gotten anything working succesfully yet, negative results are great to report to! This section should include tables, plots, and example system outputs where applicable.
6. __Attribution__: For each of your team mates, write a couple sentences describing their main contributions to the project.

# What to Submit
Submit the following to Gradescope:
* `milestone1.pdf` which contains your project proposal. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points as well. While not required, we highly recommend that you use LaTeX. You may choose to use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/acl-2020-proceedings-template/zsrkcwjptpcd).

Prepare the following for class:
* A three minute "lightning" presentation giving an update of the coolest/most intesting things you've mamagaed to accomplish so far. Since we'll be doing this over voice call, elect 1 of your teammates to give the presentation.

