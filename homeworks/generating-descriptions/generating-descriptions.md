---
layout: default
img: scribe.png
img_link: https://parl.ai/projects/light/
caption: Automatically write descriptions for text adventure games
title: Generating Descriptions
type: Homework
number: XXX
active_tab: homework
release_date: 2020-02-22
due_date: 2020-02-28 13:30:00EST
materials:
    - 
      name: Python notebook for GPT-2 finetuning
      url: https://colab.sandbox.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/language-model/hw4_transformer.ipynb
    - 
      name: LIGHT data
      url: light_data.tar.gz
submission_link: https://www.gradescope.com/courses/XXX

readings:
-
   title: Learning to Speak and Act in a Fantasy Text Adventure Game
   authors: Jack Urbanek, Angela Fan, Siddharth Karamcheti, Saachi Jain, Samuel Humeau, Emily Dinan, Tim Rocktäschel, Douwe Kiela, Arthur Szlam, Jason Weston
   venue: EMNLP
   year: 2019
   type: paper
   url: https://arxiv.org/pdf/1903.03094.pdf
-
   title: Generating Interactive Worlds with Text
   authors: Angela Fan, Jack Urbanek, Pratik Ringshia, Emily Dinan, Emma Qian, Siddharth Karamcheti, Shrimai Prabhumoye, Douwe Kiela, Tim Rocktaschel, Arthur Szlam, Jason Weston
   venue: AAAI
   year: 2019
   type: paper
   url: https://arxiv.org/abs/1911.09194
attribution: This homework was developed by George Tolkachev, Yahan Liu, Muyang Zhou, Yutong Liu, Daphne Ippolito and Chris Callison-Burch for UPenn's Interactive Fiction and Text Generation class.
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

# Instructions


In this homework, you will automatically write descriptions of locations and items in a text adventure game. 

You will use a dataset for [Learning in Interactive Games with Humans and Text ("LIGHT")](https://parl.ai/projects/light/) that was created by Facebook AI Research. 


## Part 1 - Fine-tune on LIGHT data

Use the code that you wrote for the [Fine-Tune a Neural Language Model for Text Generation homework](../language-model/language-model.html) to finetune to the LIGHT data. 

### Create seperate models for objects, locations, and characters

### Clean up the descriptions

* Truncate the generated descriptions so that they only describe one thing, and so that they don't end mid-ssentence.

* Rerank?


## Part XXX - Predicting neighboring locations and objects in locations

### Condition the generation of a location based on the text that got generated for its neighbors.

## Part XXX - Generate actions associated with each object

This might be better as a seperate homework that covers the "What can you do with a rock" paper.


## Part XXX - Create a text adventure game with your automatically generated descriptions  



# What to Submit
Submit a file `report.pdf` with your answers to the above questions. 



## Recommended readings

<table>
   {% for publication in page.readings %}
    <tr>
      <td>
	{% if publication.url %}
		<a href="{{ publication.url }}">{{ publication.title }}</a>
        {% else %}
		{{ publication.title }}
	{% endif %}
	{{ publication.authors }}.
	{{ publication.venue }}  {{ publication.year }}.

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