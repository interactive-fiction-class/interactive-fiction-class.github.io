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
      name: 
      url: 
    - 
      name: LIGHT engironment training data
      url: light_data.tar.gz
submission_link: https://www.gradescope.com/courses/XXX

readings:
- 
   title: Chatbots and Dialogue Systems (especially Section 24.3.2)
   authors: Jurafsky and Martin
   url: https://web.stanford.edu/~jurafsky/slp3/24.pdf
   type: textbook
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


In this homework, you will use the OpenAI API to automatically for a number of tasks in a text adventure game.  We will use it to:
* Perform intent determination on user input to understand what command they are trying to invoke
* Generate descriptions of locations and items in the game
* Predict whether items have certain properties (like `gettable`)
* Generate ideas on how users might try to use an item (listing its "affordances")



# Intent Determination

For computer systems with natural language interfaces, and important task is **intent determination**.  For instance, when a user is talking to Amazon Alexa, it must determine if the user wants it to play music, check the weather forecast, order a product, etc.  After this initial determination, the system ususally forwards the user utterance to a specalized model to handle each individual task.  Language provides us with many different ways of articulating our goals, which makes intent determination a challenging task for computers. 

We will get started using OpenAI by showing how you can use it to perform intent dtermination for text adventure games.  In our first version of the Text Adventure Game, we had a simple keyword-based method of handling the player's intent.  The parser implemented a function called `get_player_intent` that took in a player's command and then decided which of the following actions a player was trying to accomplish:
* **Move** to a new location
* **Examine** an object
* **Get** an object
* **Drop** an object
* Perform a **special** action using an object
* Check the player's **inventory**
* **Redescribe** the scene
* Perform a **sequence** of actions

We collected user intent data during an in-class using [this Colab notebook](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/intent-detection/Collect_Intent_Detection_Data.ipynb).  We elicited different natural langauge responses by showing the annotator a scene in the game and then asking them to describe how a user might express a paricular intent.

Here's an example of the annotation exercise.
```    
---
THE OPENING TO THE DRAWBRIDGE OF THE CASTLE
The trailhead to the forest is a dirt trail, dusty as it has not
rained in a while. The overhang of the trees is luscious and green
with only patches of sunlight beaming through the dense canopy. There
are many large trees, some with arrows still stuck in their trunks.
The trail is treacherous as it leads through the densest part of the
forest, through a stream and to a well-hidden castle. Once inside the
forest, the shade and canopy has provided plenty of opportunities for
foliage to grow making it harder to follow.

Exits: 
* North - Castle entrance
* Outside - Trailhead

You see: 
* arrows
* canopy
* foliage
* trees

How could a player say that they want to GET the ARROW?
>
```
The annotator might type in something like *retrieve the arrows from the tree*.  In doing so, they have created a training item that assicates that natural language command with the `get` intent, and the game command `get arrow`.  

## Create a Prompt for Intent Detection

Here is an example of one way that we can use the data to perform intent determination with the OpenAI API.  We will perform "few shot learning" by creating a prompt that includes each of the natural language commands that you created, followed by the intent, followed by a "stop sequence".  Here's a short sample of what our prompt looks like:

```
gather up the stones
get
###
go to the market
direction
###
collect a lily pad from the water
get
###
take a look at the lock's mechanism
examine
###
Is there any light in the dungeon?
redescribe
###
look at the food and head east
sequence
###
```

We will append a user command to the prompt, and then have OpenAI perform a completion.  If it has successfully learned the pattern in our prompt then it should predict one of the intents. For example if the user inputs `take the sword from its scabbard` then OpenAI should predict the intent `get`.

First, we can construct the prompt from the `intent.json` file.

```
import random

intent_json = load_json(filename)
intents = []

prompt = ""
for intent in intent_json:
  for command_info in intent_json[intent]:
    natural_language_command = command_info['natural_language_command'] 
    intents.append((natural_language_command, intent))

random.shuffle(intents)
for natural_language_command, intent in intents:
  prompt += natural_language_command + "\n"
  prompt += intent  + "\n"
  prompt += '###'  + "\n"

print(prompt)
```

To use this prompt with OpenAI, you can copy and paste it into the [OpenAI Playground](https://beta.openai.com/playground/).  Then you can type in the next user command, and click on the "Generate" button and have it generate a response. 


<center>
<img src="openai-playground-screenshot.png" class="img-responsive"/>
</center>

# Generating Descriptions

# Predicting Item Properties

# Idea Generation for Affordances



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