---
layout: default
img: Scheherazade.jpg
caption: Queen Scheherazade, the storyteller from One Thousand and One Nights (Arabian Nights)
title: Plot Generation
type: Homework
number: 3
active_tab: homework
release_date: 2022-02-01 
due_date: 2022-02-14 23:59:00EST
materials:
    - 
        name: Colab Notebook
        url: 
submission_link: 
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




### Starter code

We have provided [starter code for a basic text adventure game](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb).  You are free modify it however you want, and bring in any dependencies you feel will be useful.

### Task 1: Implement the plot graph creation algorithm from _Crowdsourcing Narrative Intelligence_

In the paper [Crowdsourcing Narrative Intelligence](http://www.cogsys.org/journal/volume2/article-2-4.pdf), Li et al. created an algorithm to generate plot graphs from a collection of crowdsourced stories.

Head over to the [Colab Notebook]()



<!--You should modify the provided code to:
1. Create the 13 locations from Action Castle (Cottage, Garden Path, Fishing Pond, Winding Path, Top of the Tall Tree, Drawbridge, Courtyard, Tower Stairs, Tower, 
Dungeon Stairs, Dungeon, Great Feasting Hall, Throne Room).
2. Create the items for the game (fishing poll, rosebush, club, fish, the troll etc.).
3. Update the code so that it can handle the actions/commands/preconditions that are described by the Action Castle module.

<div class="alert alert-warning" markdown="1">
__Need a hint on how to get started?__ I as able to re-implement the whole of the Action Castle game$$^*$$ using the starter code by modifying the ```build_game``` function, the ```check_preconditions``` function, and by adding a few new methods to the [Special functions section](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/Text_Adventure_Game.ipynb#scrollTo=YNrsHhpMTC8w).  None of the other starter code needed to be modified. It took me about 5 hours total to implement the game.
</div>-->


### Task 2: Generate plot graphs

Use the code you implemented in Task 1 to generate a plot graph for the [Bank Robbery data provided](), and use a library to display your graph. (If you used Pydot for your graph, you can use Graphviz to display it. If you used Networkx, try matplotlib.) Name the file `robbery.png`.

Then, find a dataset (you can try one of the ones listed on the [resources page](https://interactive-fiction-class.org/resources.html)), and make a plot graph from it as well. Call the file `dataset.png`. You will need to write your own function to read in this data since every dataset will be in a different format.

<div class="alert alert-warning" markdown="1">
__Note:__ You will probably want to take a subset of the data from the dataset you find, especially if the dataset is larger. You can pare it down by hand or using an algorithm (for example, LDA).
</div>


## What to submit

You should submit a link to a Github repository which contains the following:

1. An IPython notebook called `plot.ipynb` that runs your plot graph implementation.
2. A document (doc/docx, txt, pdf) that has your answers to the questions found on the original notebook.
3. **Two** picture files: one named `robbery.png`, one named `dataset.png`


Submissions should be done on [Gradescope]({{page.submission_link}}).

{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
