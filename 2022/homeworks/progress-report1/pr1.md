---
layout: default-2022
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/
title: Project Preparation and Literature Review
type: Project Milestone
number: 2
active_tab: homework
release_date: 2022-03-20
due_date: 2022-04-04 23:59:00EST
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
* Make progress on the suggested next steps that the class staff and your classmates left for you on your project proposal.
* Read at least 3 papers related to your proposed project. (See the Lit Review section)
* Finish collecting any datasets that you need and make sure they are in a format that you can work with.
* Outline a more definite plan on the types of methods you want to use. What will your system look like?
   * If your project involves doing text parsing with tools like AllenNLP/Stanza/Spacy, do some experiments to see whether the parsing you want to do is feasible. 

For those with extra ambitious projects, we suggest doing these bullet points for this milestone as well:
* If your project involves training/fine-tuning a neural network, try training some preliminary models and observing the outputs.
* If your project involves a user experience of some sort, create a mock-up of the user interface (even if it's not fully functional/feature-complete yet).

## Informal Lit Review
For this milestone we would like you to do a short literature review of at least 3 papers relating to your project **that are not already listed on the course website**. It might seem arbitrary to restrict you from not using papers from the course website, but we want to encourage you to go out on your own and find interesting new work to include in your project! We'd encourage you to do more than 3, but 3 is the minimum requirement for full credit. 

There are a couple of ways to find papers.

1) To find good papers, we recommend starting with a highly relevant paper (maybe from the course website or one that was suggested to you), and either looking through the paper's Related Works section or using [Google Scholar](https://scholar.google.com/) to find papers that cite it. You can also use [Semantic Scholar](https://www.semanticscholar.org/) to do this as they distinguish between "Highly Influential" citations and standard citations, which could help you narrow down your search.

2) You can also look through conference proceedings, such as [ACL Anthology](https://aclanthology.org/) or the [AAAI Digital Library](https://www.aaai.org/Library/conferences-library.php) to search through only papers that were accepted to top AI/NLP conferences. Doing this may help you find some "diamonds in the rough" (i.e. papers that are of high quality but do not have many citations yet by virtue of them being very new).

3) Alternatively, you can use Google Scholar or Semantic Scholar to search by keywords. This might be more difficult if you are not as familiar with the jargon of the area. If you would like to search this way and are having trouble finding the relevant keywords, feel free to reach out to one of us!

We recommend starting with these three methods to find papers then skimming ~10 or more of them before deciding on which three to include. This should ensure that the three you find are relevant.

**Note: While the writing itself might be informal for this part, the paper selection and insights should be high quality.**

Each team should submit a document titled `lit_review.pdf` which should contain, for each paper:
* The title of the paper, the year of publication, and a link to the paper.
* A paragraph with a short summary of the paper's contributions. (2-3 sentences)
* A bulleted list of your thoughts on the paper and how it relates to your project.


## Proposal
For the main milestone writeup, create a new document which describes the progress you've made so far. Feel free to copy from your project proposal where appropriate. Even if you do copy, you might need to fill in more details.
Your document should include the following sections:

__Title__ & __Author Names__: What are you calling your project? These are not graded but still important! (No section header for these bits)
1. __Project Description__: This is the "what" and the "why" of your project. 
 * The "what": Explain the main idea of your project and what you are trying to accomplish. It's okay if these have changed since the project proposal.
 * The "why": If it's a research project, what's your research question (i.e., what are you trying to prove with this work)? If it's an artifact that you're creating, why are you creating it?
2. __Related Work__: What previous research will you be using, building off of, or being inspired by? Tell a short "story" using what you found out from the Lit Review above. This can include papers from the course schedule as well as anything else you want to cite.
3. __Methods__: What are the steps to accomplish your project? This should describe both the steps you've done so far (data collection and system planning) and the ones you plan to do. This doesn't have to be the final methods that you end up using, but writing out a plan out will help you figure out some details you might not have thought of otherwise!
4. __Data__: What data have you decided to use? Where did you get it from, what does it look like, and what are some potential problems with it?
5. __Evaluation Plan__: What will you be using to evaluate your research question or that the components of your interactive experience are working well? 
  * These can be things like accuracy, diversity metrics, perplexity, BLEU/ROUGE scores, success rate, human evaluation scores, etc. depending on your project.
6. __Preliminary Results (optional)__: Describe any results you have so far. These can include results for intermediate steps that build toward your main project goal. If you haven't gotten anything working succesfully yet, negative results or plans for experiments to run are great to report too! This section should include tables, plots, and example system outputs where applicable.
7. __Attribution__: For each of your team mates, write a couple sentences describing their main contributions to the project so far and what each person plans to do for the rest of the project.

# What to Submit
Submit the following to [Gradescope](https://www.gradescope.com/courses/354158/assignments/1944469):
* `lit_review.pdf` which contains your literature review. This can be in any format you like. We find that using Google Docs and then downloading as a PDF works well for this sort of thing.
* `milestone2.pdf` which contains your milestone 2 submission. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points as well. While not required, we highly recommend that you use LaTeX and a conference template. You may choose to use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/acl-rolling-review-template/jxbhdzhmcpdm).

# Grading
<div class="alert alert-warning" markdown="1">
* Project Description: Make sure you do not only include a description of the project, but also a reason why this project is important (i.e. motivation) (1pt)
* Related Work: Do not just summarize previous work, but relate it to your project. (1pt)
* Methods: What have you completed up to now? What do you plan on doing? Write down a concrete plan of action. (1pt)
* Data: Do not just list the datasets, but describe them, and explain how you will use them. (1pt)
* Evaluation Plan: What evaluation metrics you chose and why? Are they applicable to your task? (1pt)
* Attribution: Do not forget to note which team member will do what. This is where most students last year lost points! (1pt)
</div>

