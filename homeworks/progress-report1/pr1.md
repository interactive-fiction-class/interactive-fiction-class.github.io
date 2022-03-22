---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: The Term Project
title: Baseline and Lit Review
type: Project Milestone
number: 2
active_tab: homework
release_date: 2022-03-20
due_date: 2022-03-28 23:59:00EST
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

For this milestone, you should read papers that are related to your project and finish cleaning data and setting up a baseline. In particular you should: 
* Make progress on the suggested next steps we and your classmates left for you on your project proposal.
* Read at least 3 papers related to your proposed project. (See lit review section)
* Finish collecting any datasets that you need and make sure they are in a format that you know how to process.
* If your project involves doing text parsing with tools like AllenNLP/Stanza/Spacy, do some experiments to see whether the parsing you want to do is feasible. 

For those with extra ambitious project, we suggest doing these bullet points for this milestone as well:
* If your project involves training/fine-tuning a neural network, try training some preliminary models and observing the outputs.
* If your project involves a user experience of some sort, create a mock-up of the user interface (even if it's not fully functional/feature-complete yet).

## Lit Review
For this milestone we would like you to do a short literature review of at least 3 papers relating to your project **that are not already listed on the course website**. The seemingly arbitrary restriction of them not being on the course website is to encourage you to go out on your own and find interesting new work to include in your project! We encourage you to do more than 3, but 3 is the minimum requirement for full credit. 

To find good papers, we recommend starting with a highly relevant paper (maybe from the course website), and use [Google Scholar](https://scholar.google.com/) to find papers that cite it. You can also use [Semantic Scholar](https://www.semanticscholar.org/) to do this as they distinguish between "Highly Influential" citations and standard citations, which could help you narrow down your search. 

You can also use the [ACL Anthology](https://aclanthology.org/) to search through only papers that were accepted to top NLP conferences. This resource may help you find the "diamonds in the rough" (i.e. papers that are of high quality but do not have many citations yet by virtue of them being very new)

We recommend starting with these methods to find papers then skimming ~10 or more of them before deciding on the three to include. This should ensure that the three you find are of high quality.

Each team should submit a document titled `lit_review.pdf` which should contain, for each paper:
* The title of the paper, the year of publication, and a link to the paper.
* A paragraph with a short summary of the paper's contributions. (2-3 sentences)
* A bulleted list of your thoughts on the paper and how it relates to your project.

## Writeup
For the main milestone writeup, create a new document which describes the progress you've made so far. Feel free to copy from your project proposal where appropriate. Your document should include the following sections:

1. __Project Description__: This should explain the main idea of your project and what you are trying to accomplish. If these have changed sincde the project proposal, this section should reflect those changes.
2. __Related work__: What previous research will you be using, building off of, or inspired by? This should largely be a copy of your `lit_review.pdf` just strung together in one cohesive section. This can include papers from the course schedule as well as anything else you want to cite.
3. __Method__: What are the steps to accomplish your project. This should describe both the steps you've done so far and the ones you plan to do.
4. __Data__: What data have you decided to use? What does it look like, and what are some potential problems with it?
5. __Evaluation__: What methodologies will you be using to evaluate the research question  you are answering or that the components of your interactive experience are working well? 
  * These can be things like accuracy, diversity metrics, BLEU score, success rate, human evaluate scores, etc. depending on your project.
6. __Preliminary Results__: Describe any results you have so far. These can include results for intermediate steps that build toward your main project goal. If you haven't gotten anything working succesfully yet, negative results or plans for experiments to run are great to report too! This section should include tables, plots, and example system outputs where applicable.
6. __Attribution__: For each of your team mates, write a couple sentences describing their main contributions to the project.

# What to Submit
Submit the following to Gradescope:
* `milestone2.pdf` which contains your project proposal. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points as well. While not required, we highly recommend that you use LaTeX. You may choose to use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/acl-rolling-review-template/jxbhdzhmcpdm).
* `lit_review.pdf` which contains your literature review. This can be in any format you like. We find that using google docs and then downloading as a PDF works well for this sort of thing.
