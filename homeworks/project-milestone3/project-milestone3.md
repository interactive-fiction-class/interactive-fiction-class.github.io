---
layout: default
img: estimating_time.png
caption: Don't Panic
img_link: https://xkcd.com/1658/   
title: The Term Project
title: Project Milestone 2
type: Homework
number: 6
active_tab: homework
release_date: 2020-02-26
due_date: 2020-04-29 13:30:00EST
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
<b>There will be no extensions on this due date. You may not use late days.</b>
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
For your final project you should prepare a 10 minute presentation for the class and a report documenting what you accomplished. The presentation is due on Thursday April 23 in class while your report is due on the last day of the term, April 29th.

## Presentation
Your presentations can either be done live in class on Thursday, or you can pre-record it and email a link to us before the start of class. To fit in all 10 presentation, we will be strictly enforcing a 10-minute time limit.
Chris's general rule-of-thumb is about 1 minute per slide, so you should aim to have no more than 10 or so content slides.
If you have built an interactive experience, you might want to record a video of it or take screenshots instead of doing a live demo. (If we have time at the end of class, we can always go back and do the live demo). 
As long as you stay in the time limit, you are welcome to have multiple team-members trade off speaking in the presentation.

### Presentation Grading
TODO

## Report
You report is a document that describes what you have managed to accomplish. It should be a self-contained document that explains what you have accomplished. You are welcome (and encouraged) to build off your Milestone 2 progress report. At this point in the class, all of you have read and presented on academic papers. You should use these as inspiration for what a good writeup looks like.

### Report Sections
It should have the following sections.

1. __Introduction__: This should explain the main idea of your project and describe in general terms your most significant accomplishments. Why is your project interesting?  
2. __Related work__: What previous research works does your project rely on? What other projects exist that are similar? If you used a dataset you didn't collect yourself, where did you get it from? Include explanations in complete sentences along with in-text citations to these sources. 
3. __Data__: What datasets, if any, did you use? If youhave collected or built your own dataset, how did you go about doing this? What are some potential problems/challenges you encountered with the data?
4. __Method__: Explain the steps involved in your project. This section should include enough detail that someone reading it could reasonably attempt to reproduce your work. This should describe both the steps you've done so far and the ones you plan to do.
5. __Evaluation__: What methods does yours results section use to evaluate the research question  you are answering or that the components of your interactive experience are working well?
These can be things like accuracy, diversity metrics, BLEU score, success rate, human evaluate scores, etc. depending on your project.
6. __Results__: Describe your main results. This can include negative results too. This section should use tables, plots, examples of system outputs, and other figures to support the results.
7. __Discussion__: This is a _meta_ section to discuss how the project went.
What things did you try that didn't work out?
If you were to start over from scratch, what would you do differently? If someone were to continue working on this project, what do you suggest are good next steps/good future work?
6. __Attribution__: For each of your teammates, write a couple sentences describing their main contributions to the project. If you have any concerns about distribution of work, feel free to email us directly.

### Report Grading
Your report will be graded on the following criteria.
1. __Formatting__: All of the sections described in the previous section are present and clearly marked. The report includes a title of the project and the name of the author at the top. Images, tables, and other figures have captions and are referenced in the text. The paper makes use of inline citations that follow a standard convention ([IEEE](https://pitt.libguides.com/citationhelp/ieee), [Chicago](https://pitt.libguides.com/citationhelp/chicago), ([APA](https://pitt.libguides.com/citationhelp/APA), etc.).
2. __Communication__: Your report should be targeted at an audience who is familiar with NLP but has not taken the class and knows nothing about what you have done so far. You can imagine your audience as either the readers of a technical blog post (if you took the interactive experience option) or as reviwers of a paper submission to an NLP conference such as ACL (if you took the research question option). You should aim to make your methods section clear enough that others could attempt to reproduce your work and your results section clear enough that readers understand exactly what experiments you ran.
3. __Style__: You should write in paragraphs and complete sentences unless there is a very good reason not to.
4. __Content__: The report answers all relevant questions posed in the previous section. Images, tables, plots, of other figures are used to support the report' contents.
5. __Length__: I don't want to assign a strict word length requirement, but if your paper has fewer than 1,500 words (not including referneces) then it is very likely you have not provided enough detail.

# What to Submit
Submit the following to Gradescope:
* `report.pdf` which contains your project report. While not required, we highly recommend that you use LaTeX. You may choose to use the [template from the Association for Computational Linguistics](https://www.overleaf.com/latex/templates/acl-2020-proceedings-template/zsrkcwjptpcd).
* `slides.pdf` a pdf version of the slides you present in class.
