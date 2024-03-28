---
layout: default
caption: Let's build our own AI Dungeon!
title: Building an AI Game Master
type: Homework
img: mouse_character_image_small.png
caption: Mausritter character portrait
number: 4
active_tab: homework
release_date: 2024-03-19
due_date: 2024-04-02 23:59:00EST
materials:
   -
      name: hw4.ipynb
      url: /homeworks/ai-gm/hw4.ipynb
submission_link:
readings:
  - title: Kani&colon; A Lightweight and Highly Hackable Framework for Building Language Model Applications
    authors: Andrew Zhu, Liam Dugan, Alyssa Hwang, Chris Callison-Burch
    venue: NLP-OSS @ EMNLP
    year: 2024
    type: paper
    url: https://aclanthology.org/2023.nlposs-1.8/
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

*Author: Andrew Zhu (andrz@seas.upenn.edu)*

In this homework, we'll use Kani to build a simple Game Master (GM) for
the [Mausritter TTRPG](https://losing-games.itch.io/mausritter). Your GM will help walk you through creating a mouse and
rolling dice to overcome challenges in the game. Along the way, you'll learn the basics of
the [Kani library](https://kani.readthedocs.io/en/latest/), function calling with LLMs, and how a LLM can use structured
information to act as a game state manager.

We won't implement more complex systems like combat or spellcasting in this homework, but extending this system to make
a more comprehensive GM (e.g. adding inventory tracking, combat, spellcasting, structured tracking of NPCs, ...) would
make for a great class final project.

This assignment will have 3 main parts:

1. **Gain familiarity with Kani and function calling** - You will learn how Kani can be used to expose external APIs to
   LLMs by connecting GPT-4 with a dice rolling library.
2. **Use function calling to build a character creator agent** - We'll show how LLMs can be used to generate structured
   data by creating an agent to walk a new player through the Mausritter character creation process. Your agent will be
   able to roll dice for the player, help translate natural language to game mechanics, and save their character sheet
   once it's created.
3. **Put everything together in an AI GM** - We'll use function calling and the structured character created by
   your agent to create a grounded AI GM. It will have the ability to reference your character sheet and roll saves
   based on your mouse's stats. Finally, we'll see how a grounded AI GM compares to a prompting-only approach. 

## What You'll Need

- A copy of the [Mausritter rules](https://losing-games.itch.io/mausritter) (available for free on itch.io)
- Your [Helicone key](https://www.helicone.ai/developer)
- The [Kani documentation](https://kani.readthedocs.io/en/latest/)
- The [d20 documentation](https://d20.readthedocs.io/en/latest/start.html)

### Using our Starter code

We have provided [a Python Notebook for HW4]({{page.materials[0].url}}). I recommend using Visual Studio Code
for this homework. You'll be making changes to the `HW4.ipynb` file. You should read through the whole Python Notebook
carefully, and add your code to all places marked TODO.

#### Environment Setup

To run this code in your Python IDE, you'll need to install a couple python packages via `pip`, and you'll need to set
the `OPENAI_API_KEY` environment variable to your Helicone key.

First [download the notebook]({{page.materials[0].url}}), then create a virtual environment and install
the dependencies. Here's how I recommend that you set up your environment:

```shell
$ mkdir hw4
$ cd hw4
$ python3.10 -m venv venv
$ source venv/bin/activate
(venv) $ pip install jupyter 'kani[openai]' d20
```

If you're using VS code then you can send your OPENAI_API_KEY to it when you launch it from
the command line:

```
$ cd path/to/hw4
$ source venv/bin/activate
(venv) $ HELICONE_API_KEY=sk-helicone-XXXXXXX-XXXXXX code .
```

You should replace `sk-helicone-XXXXXXX-XXXXXX` with your Helicone key which you can
find [here](https://edstem.org/us/courses/50468/discussion/4413041).

## What to submit

Please submit the following:

- Completed `hw4.ipynb`
- The most recent transcripts of your character creator agent and AI GMs: `creator-TIME.json`, `gm-TIME.json` ,
  and `gm-structureless-TIME.json`
- The images you generated of your character (saved in the `dalle/` folder)
- A `README.md` that describes your high-level implementation of each part of the homework and any interesting findings

You should submit your completed homework to [Gradescope]({page.submission_link}). You can work in teams. Only one team
member should submit - be sure to specify who your partner was when you make your submission. If your group is >2
students, you should do one extension per additional teammate and describe what you did in the homework writeup. The
extensions are up to you!

# Recommended readings

<table>
   {% for publication in page.readings %}
    <tr>
      <td>
	{% if publication.url %}
		<a href="{{ publication.url }}">{{ publication.title }}</a>
        {% else %}
		{{ publication.title }}
	{% endif %}
	{% if publication.authors %}	      
		- {{ publication.authors }}.
	{% endif %}
	{% if publication.year %}	
		{{ publication.venue }}  {{ publication.year }}.
	{% endif %}

	{% if publication.abstract %}
	<!-- abstract button -->
	<a data-toggle="modal" href="#{{publication.id}}-abstract" class="label label-success">Abstract</a>
	<!-- /.abstract button -->
	<!-- abstract content -->
	<div id="{{publication.id}}-abstract" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="{{publication.id}}">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <h4 class="modal-title" id="{{publication.id}}">{{publication.title}}</h4>
        </div><!-- /.modal-header -->
        <div class="modal-body">
        {{publication.abstract}}
        </div><!-- /.modal-body -->
	</div><!-- /.modal-content -->
	</div><!-- /.modal-dialog -->
	</div><!-- /.abstract-content -->
	{% endif %}
	{% if publication.bibtex %}
	<!-- bibtex button -->
	<a data-toggle="modal" href="#{{publication.id}}-bibtex" class="label label-default">BibTex</a>
	<!-- /.bibtex button -->
	<!-- bibtex content -->
	<div id="{{publication.id}}-bibtex" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="{{publication.id}}">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <h4 class="modal-title" id="{{publication.id}}">{{publication.title}}</h4>
        </div><!-- /.modal-header -->
        <div class="modal-body">
 	   <pre>{{publication.bibtex}}
           </pre>
        </div><!-- /.modal-body -->
	</div><!-- /.modal-content -->
	</div><!-- /.modal-dialog -->
	</div><!-- /.bibtex-content -->
	{% endif %}

</td></tr>
  {% endfor %}
</table>
