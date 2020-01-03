---
layout: default
img: zork.jpg
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Zork, an early intractive fiction game released in 1977.
title: CIS 521 Homework 2 "Build a Text-Adventure Game"
active_tab: homework
release_date: 2020-01-16 
due_date: 2020-01-30 23:59:00EST
materials:
    - 
submission_link: https://www.gradescope.com/courses/78405
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


<div class="alert alert-info" markdown="span">
Links to tutorials and other Python resources are posted on the [schedule page](/lectures.html) in the Python Review parts.</div>


Homework 1: Build a Text Adventure Game
=============================================================


## Instructions

In this home, you will play a small text-adventure game. It can be on any topic or telling any story of your choice. This homework can be completed in groups of up to 2 people. We will play some of the games in class, so the more creative/exciting you make it, the better!

Since this is a graduate-level class, we leave the implementation details open-ended. You may use any programming language or platform of your choice. However, we have put together a small Python library which may be useful. TODO: Add link here

### Story Requirements
Your game should include all of the following:

* The ability to take as input arbitrary strings. In other words, the user must be able to type commands like "take the octopus from the tank" rather than the game providing a multiple choice list of possible options.
* At least 3 "rooms"
* At least 3 objects that can be interacted with. These can be doors, keys, tools, octupi, etc.
* At least one "win" state and at least one "lose" state.

### NLP Requirements
In the earliest text adventure games, parsers used exact string matching. If a command wasn't in either the form `verb` or `verb object`, the parser would not recognize it. However, parsers and NLP in general have evolved tremendously from the 1970s.
In addition to the story requirements, we ask that you take advantage of at least **two** advancements from the last four decades of NLP research to either make your parser more intelligent than simple string matching or to otherwise improve the game-playing experience.
Some possible ideas are:

* Using word2vec similarity to allow the parser to do "fuzzy" matching of similar words.
* Using a modern dependency parser to extract the verb and object from a user input.
* A guardswoman NPC who will only let you pass if you [complement her](https://textblob.readthedocs.io/en/dev/quickstart.html#sentiment-analysis).
* An ogre who will only marry you if [you tell him a joke](https://ccc.inaoep.mx/~villasen/bib/LEARNING%20TO%20LAUGH%20(AUTOMATICALLY).pdf).

You will likely find (Spacy)[https://spacy.io/usage/facts-figures], (NLTK)[https://www.nltk.org/], or (AllenNLP)[https://github.com/allenai/allennlp] useful for completing this task.

## What to submit

1. An instance of your game that *I can run easily*. This can be a Google Colab, a Unix command-line program, or a website link. If running your game requires me to install non-standard dependencies, you should include a detailed README. 

2. A link to your code, ideally as a Github repository or Google Colab.

3. A report that describes how you used **two** advancements in NLP to improve the quality of your game. You should cite relevent papers, and explain how you are using the methods introduced in them.

If you are submitting a Google Colab or IPython notebook, you can include your report as part of the notebook itself, and all you need to submit is a single notebook link. Likewise, if you are using a Github repository, you can put your report into the README, and all you need to submit is the Github link.
