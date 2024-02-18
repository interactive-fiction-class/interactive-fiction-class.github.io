---
layout: default
img: scribe.png
img_link: https://ai.meta.com/blog/introducing-light-a-multiplayer-text-adventure-game-for-dialogue-research/
caption: Learning in Interactive Games with Humans and Text (LIGHT)
title: think of questions for our guest speaker Jason Weston
type: participation
speaker: Jason Weston
active_tab: homework
release_date: 2024-02-17
due_date: 2024-02-27 13:45:00EST
materials:
    - 
        name: Learning to Speak and Act in a Fantasy Text Adventure Game
        url: https://arxiv.org/abs/1903.03094
    - 
        name: Generating Interactive Worlds with Text 
        url: https://arxiv.org/abs/1911.09194
    - 
        name: I love your chain mail! Making knights smile in a fantasy game world&colon; Open-domain goal-oriented dialogue agents
        url: https://arxiv.org/abs/2002.02878
    - 
        name: How to Motivate Your Dragon&colon; Teaching Goal-driven Agents to Speak and Act in Fantasy Worlds 
        url: https://arxiv.org/abs/2010.00685
submission_link: https://www.gradescope.com/courses/704268/assignments/4120036
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
{% elsif page.type == "participation" %}
<div class="alert alert-info">
This activity counts towards your participation grade. It is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% endif %}

{% if page.materials %}
<div class="alert alert-info">
The materials that you will need for this activity are:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}



Participation Activity: Research Our Guest Speaker
=============================================================

We'll have several guest speakers this semester, including game designers, AI professors and industrial researchers.  For each speaker, you should learn a bit about them before they give their talk, and prepare at least one question that you'd like us to ask them to hear their insights about our course topics. 

You should [submit your question to gradescope]({{page.submission_link}}), along with a short bio for the speaker and the websites that you used to research them  before class begins.

On {{ page.due_date | date: "%A, %B %-d, %Y" }} our guest speaker will be **{{ page.speaker }}**.
