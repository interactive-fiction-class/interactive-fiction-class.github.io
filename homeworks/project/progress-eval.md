---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/
title: Human Evaluation
type: Project Milestone
number: 4
active_tab: homework
release_date: 2024-03-21
due_date: 2024-04-30 13:45:00EST
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

Now that you've created an outline for your presentation that may or may not be missing experimental results, it's time
to populate some of these results! Since many of you are creating interactive experiences for your final projects,
it's important to think about how to design evaluations for those experiences and analyze the data you collect.

For this Milestone, we are asking you to think about what metrics you want to evaluate your system on and design an
interface to perform this evaluation. We'll use the last two class meetings to participate in other groups' evaluations,
so that each group gets a chance to collect human feedback.

**Although this milestone is due before class on Tuesday, 4/30 (the last day of class), we will also be using
Thursday, 4/25 for human evaluation. This milestone is due before class.**

To be specific, for this Milestone, you should:

* Design a human evaluation for your interactive system - this involves not just building the system and choosing
  metrics to examine, but also thinking about what research questions these metrics answer.
* Create an interface for conducting your human evaluation, to be used in class on 4/25 and 4/30.
* Write detailed instructions for your classmates to participate in your evaluation.
* Write up your methods in a submission for this milestone.

### Writeup Sections

The writeup should have the following sections. Much of the content will also be helpful when writing up your final
report, so you might want to write it in the same format as your report.

__Title__ & __Author Names__.

1. __Evaluation Metrics__: You should have begun thinking about metrics in the previous milestone. In this milestone,
   you should explain why you chose these metrics, what parts of your interactive experience they test, and how they
   help answer the research question(s) you put forth.
2. __Collection Methodology__: How do you plan to collect these metrics? This is a good section to include screenshots
   of your evaluation interface. If you're using additional quantitative metrics that don't require a human judge,
   include how you plan to collect them here too. You should go into specific detail about your system.
3. __Instructions to Evaluators__: For a human evaluation, what do the evaluators need to do? Give them specific,
   detailed instructions for what to look for and how to interact with your interface. These should be written with your
   classmates as the audience in mind: they won't necessarily be familiar with your system.

In addition to being an important part of a research paper's methodology, conferences like ACL require authors to
include information like this in their submissions (see
[section D of the Responsible NLP Checklist](https://aclrollingreview.org/static/responsibleNLPresearch.pdf)).

### Grading

<div class="alert alert-warning" markdown="1">
* Metrics - 2 points
* Methodology - 2 points
* Instructions - 2 points
* Interface - 2 points
* In-class participation - 2 points
</div>

# What to Submit

Submit the following to [Gradescope]({{page.submission_link}}):

* `milestone4.pdf` which contains your milestone 4 writeup. To make grading easier, your writeup should include
  section headers corresponding to each of the bulleted points.
* A zip file containing the code for your evaluation interface, if any. The code should include a README describing its
  high-level layout, any setup instructions, and how to run the interface.
