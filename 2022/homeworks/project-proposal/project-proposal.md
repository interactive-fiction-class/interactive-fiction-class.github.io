---
layout: default-2022
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: The Term Project
title: Project Proposal and Lightning Talk
type: Project Milestone
number: 1
active_tab: homework
release_date: 2022-02-28
due_date: 2022-03-16 23:59:00EST
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

The project is a chance for you to delve into one of the topics we have covered in class. You can choose between two directions: creating a novel interactive experience or answering a research question. For the direction that you choose, write a project proposal that answers the questions below. You should also prepare to give a two-minute "lightning" presentation on your proposal in class on March 17. Some examples of projects brainstormed by students in the 2020 iteration of this class can be found [here](https://docs.google.com/document/d/1YXUCVWTTc2ks7dkHTjpyEy4mEUTGBo192olya-k_G2Y/edit?usp=sharing).

If you are trying to decide between multiple project ideas, or if you're struggling to come up with something, we highly encourage you to come to Office Hours and discuss it with the staff. We are all experienced researchers and should be able to help you narrow down which ideas of yours are the most feasible + interesting.

## Build a novel interactive experience
Use the techniques we have learned in class to build a novel interactive experience that involves generated text. While fine-tuning a large language model such as GPT-3 on a custom dataset could be a component of your project, we are expecting something more involved than just this. Can you expand upon Homeworks 1 and 2 to build a text-based game that uses NLP and language models to make a novel and fun game experience? Can you incorporate elements from Homeworks 3 and 4 into your generation? By the end of the semester, you should have a demo that runs either in Colab or on a website showcasing your interactive experience.

Write a project proposal that includes the following sections:
1. __Project Description__: What novel interactive experience do you propose to design?
  - Give an example mockup of what the user experience will look like.
2. __Proposed Method__: How will you be using text generation systems or other NLP concepts from class in order to enable the interactive experience? Will you need to train your own neural networks?
  - Write 2-3 paragraphs explaining your proposed method.
3. __Data__: What data will be needed to build your interactive experience?
  - Does the needed data already exist?  If so, how much data is available?
4. __Related work__: Do similar games/experiences exist to the one you propose to create?
  - Give pointers to them and explain how you think they relate to your project idea.
5. __Team members__: Give a list of the students who will participate in this project, and what contribution you expect each one to make to the project.


## Attempt to answer a research question about text generation or interactive fiction
In class, we have discussed multiple open questions related to text generation. Choose one of these questions and conduct experiments to attempt to answer the question. By the end of the semester, you should have an academic paper that describes the research question, the experiments you ran to try and answer it, and an analysis of the experimental results.

Write a project proposal that includes the following sections:
1. __Project Description__: What research question or problem are you trying to solve?
  - Write a problem definition (1 to 2 paragraphs)
  - Give an illustrative example of the problem and/or your proposed solution.
2. __Data__: What kind of data will you need to train and evaluate your method?
  - Does the needed data already exist?  If so, how much data is available?
3. __Evaluation__: What evaluation metrics do you plan to use to answer your research question?
4. __Related work__: What previous research has been done on this research question?
  - Give pointers to several research papers that you think are relevant along with short explanations of how you think they relate to your project idea.
5. __Team members__: Give a list of the students who will participate in this project, and what contribution you expect each one to make to the project.

# What to Submit
Submit to Gradescope:
* `proposal.pdf` which contains your project proposal. To make grading easier, your proposal should include section headers corresponding to each of the bulleted points as well. Latex is preferred but not required.

Prepare the following for class:
* A two minute "lightning" presentation pitching your idea to the class. You should add **a single slide** to this [Google Slides presentation](https://docs.google.com/presentation/d/14SnEPKNyEtDZuUlJnIRxx57xQInliMvK4pLdnVurh5E/edit?usp=sharing). _Please prepare at most a single slide. You will have time for a longer presentation at the end of the semester._
  - For some examples of past lightning talks, you can find the 2020 slides [here](https://docs.google.com/presentation/d/1EMII1GDGO3IdfHfrV6Lnrkbe1vMEUoyOjoZ3QePUFf4/edit?usp=sharing)


# Grading
<div class="alert alert-warning" markdown="1">
* Project Description - 1 point
* Proposed Method or Evaluation - 1 point
* Data - 1 point
* Related Work - 1 point
* Team Members - 1 point
* Lightning Talk - 2 points
</div>
