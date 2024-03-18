---
layout: default
img: scribe.png
img_link: https://parl.ai/projects/light/
caption: Can we generate text adventure games from stories?
title: Interactive Fiction
type: Homework
number: 3
active_tab: homework
release_date: 2024-03-09
due_date: 2024-03-19 23:59:00EST
materials:
    - 
      name: CIS-7000-HW3.zip
      url: https://www.cis.upenn.edu/~ccb/teaching/2024sp/CIS-7000-HW3.zip
submission_link: https://www.gradescope.com/courses/704268/assignments/4242609/
readings:
-
   title: Learning to Speak and Act in a Fantasy Text Adventure Game
   authors: Jack Urbanek, Angela Fan, Siddharth Karamcheti, Saachi Jain, Samuel Humeau, Emily Dinan, Tim Rocktäschel, Douwe Kiela, Arthur Szlam, Jason Weston
   venue: EMNLP
   year: 2019
   type: paper
   url: https://arxiv.org/abs/1903.03094
-
   title: Generating Interactive Worlds with Text
   authors: Angela Fan, Jack Urbanek, Pratik Ringshia, Emily Dinan, Emma Qian, Siddharth Karamcheti, Shrimai Prabhumoye, Douwe Kiela, Tim Rocktaschel, Arthur Szlam, Jason Weston
   venue: AAAI
   year: 2019
   type: paper
   url: https://arxiv.org/abs/1911.09194
-
   title: DataDreamer&colon; A Tool for Synthetic Data Generation and Reproducible LLM Workflows
   authors: Ajay Patel, Colin Raffel, Chris Callison-Burch
   venue: ArXiv
   year: 2024
   type: paper
   url: https://arxiv.org/abs/2402.10379
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

In [homework 1](https://interactive-fiction-class.org/homeworks/text-adventure-game/text-adventure-game.html), we manually built our own text adventure games.  In [homework 2](https://interactive-fiction-class.org/homeworks/gpt-parser/gpt-parser.html), we created a GPT Parser that could create evocative descritpions and do better understanding of user commands.  In this hoework assignment, we are going to try to use GPT to generate games.  Our goal for this homework is to take a few paragraphs of a work of fiction as input, and then generate a game as output.

We'll approach this via fine-tuning GPT 3.5 to translate between fiction and a JSON data structure that we can load into our `text_adventure_game` format.  In order to do this we'll need a few hundred examples of fiction stories paired with an appropriate JSON output that represents that story in our game format.  

Where can we get that kind of data?  It doesn't exist, so we'll create a synthetic data set that approximates whT we want.  To create our synthetic data, we'll start with a few hundred game locations, and then have GPT-4 write fiction that takes place in that location.  The games will come from a dataset called **LIGHT** (Learning in Interactive Games with Humans and Text) that has several hundred locations, and several thousand characers and items.

After we have created the synthetic data of (fiction, JSON) pairs, we'll fine tune a model on that data.  After we have fine-tuned the model, we will try to generate a new game given a story as input.

This assignment will have 3 main parts:
1.  **Generate synthetic data** - You will familiarize youself with the LIGHT data and its JSON representation.  Given a JSON of a game state, you'll prompt GPT-4 to generate literary fiction in zero-shot fashion.  We'll generate fiction for 100 game states from LIGHT.  This will be our synthetic data set.   For this part will also experiment with "prompt augmentation" to make our fiction more interesting. 
2.  **Fine-tune a model on your data** -  We will fine-tune GPT-3.5 to on our synthetic dataset.  We'll reverse the order of the inputs and outputs from part 1.  We'll use the fiction stories and as input, and genrate the game state for the story as output.
3.  **Create a game from a story** -  After fine tuning, we will have you create game states from a story of your chosing or a story that you have written.  After you the generate the game states of the locations in JSON format, you will editing them into a playable game.

### Using our Starter code

We have provided [a Python Notebook and data for HW3]({{page.materials[0].url}}).  I recommend using Visual Studio Code for this homework. You'll be making changes to the `HW3.ipynb` file.  You should read through the whole Python Notebook carefully, and add your code to all places marked TODO.

#### Environment Setup

To run this code in your Python IDE, you'll need to install the openai python package via `pip`, and you'll need to set two environment variables named `OPENAI_API_KEY` and `HELICONE_API_KEY`.


First [download the zip file]({{page.materials[0].url}}), then create a virtual environment and install
the dependencies.  Here's how I recommend that you set up your environment:
```
$ unzip CIS-7000-HW3.zip
$ cd CIS-7000/HW3/
$ python3 -mvenv venv
$ source venv/bin/activate
(venv) $ pip install -e .'[dev]'
(venv) $ pip install openai tiktoken
```

If you're using VS code then you can send your HELICONE_API_KEY and your OPENAI_API_KEY to it when you launch it from the command line:
```
$ cd path/to/homework/CIS-7000/HW3/
$ source venv/bin/activate
(venv) $ HELICONE_API_KEY=sk-helicone-XXXXXXX-XXXXXX OPENAI_API_KEY=sk-XXXXXXXXXXXXXXX   code .
```
You should replace `sk-helicone-XXXXXXX-XXXXXX` with your Helicone code which you can find [here](https://edstem.org/us/courses/50468/discussion/4413041), and `sk-XXXXXXXXXXXXXXX` with your OpenAI API key, which you can find [here](https://platform.openai.com/api-keys).  




## Part 1: Generate synthetic data

We'd like to be able to convert stories into playable games.  To do so, we'd like to fine to a LLM on a bunch of data of stories paired with JSON objects that we can load into our `text_adventure_games` package.  Unfortunately, that data doesn't exist.  We'll create it ourself by generating stories from a bunch of existing text adventure games that were created by Jason Weston's group at Facebook Research.

Here's an example of what we'll do.  Given a game location in our JSON format, we'll have GPT-4 write a story for the game location.  

Here's an [example of a location JSON](location.html).  You can find out more about the [full JSON specification for our text adventure games here](json_format.html).

We'll prompt GPT-4 to wriet some fiction for it with this prompt:
> Write this scene for a historical fantasy or suspense novel. Use a 3rd person narration to provide a deep understanding of the characters' thoughts and emotions, as well as to describe the environment and objects in the room in detail. Opt for past tense, as it's the common tense for these genres. 
>
>Start your scene in medias res, or in the middle of a conversation. Have your characters engaged in a discussion about the Duke's next grand hunting conquest. As part of the dialogue, ensure that the power dynamics and hidden agendas are subtly highlighted. For instance, Lady Isolde should be written as seemingly praising the Duke's hunting exploits, but her genuine motive is to gain insights about his cruel hunting methods. Simultaneously, present Sir Lionel as a vigilant protector who speaks less and observes more, diverting attention or suspicion from Lady Isolde whenever necessary. The tensions between the characters and the secrets they conceal should add an underlying suspense to their conversation.

GPT will then generate this story:

> The Duke of the Castle stood erect, his menacing silhouette outlined by the flicker from the towering fireplace. Lady Isolde, her emerald eyes shimmering in the firelight, leaned forward, a masterwork of feigned fascination etched onto her delicate features. 
>
> "Your last hunt, my lord, was the stuff of legends," she cooed, lavish praise cloaking her shrewd motives. She yearned not for tales of grandeur, but for uncomfortable truths about his barbarous practices. 
>
> As quiet as the white ivory floor beneath them, stood Sir Lionel, his keen gaze upon the Duke unblinking, his large hand tightly around the hilt of his sword. Always vigilant, always prepared. The armour he wore was as old as the castle, carrying the scars of battles past, yet it remained, like the knight himself, unyielding and ready for combat. 
>
> The room, a testament to the Duke's gruesome conquests, cloaked them all. Each mounted head, each piece of antique weaponry told a tale as brutal and unmerciful as the eyes of the Duke himself. He was the predator, and this castle was his hunting ground. The walls bore witness to his savagery, while the ceiling, embellished with murals of his triumphs, watched from above, an ever-present reminder of his so-called greatness. 
>
> "Indeed, Lady Isolde," the Duke boomed, breaking her train of thought, "And the next will be grander. The Old Forest has a beast that is yet to know my blade." His cold, hard chuckles echoed deafeningly around the room as he twirled the ivory dagger in his hand. 
>
> Sir Lionel, ever her protector, turned his gaze towards her, his sharp, blue eyes flashing a warning. Lady Isolde returned the glance before leaning towards the Duke, her voice sweet and enticing. "That sounds fascinating, my lord. It would be a privilege to hear more." She paused, her heart pounding as she held the Duke’s gaze. Pretending could be a dangerous game, but it was the only one she could play without raising suspicions. 
>
> For that was the game in this castle, a ballet performance of power, debauchery and secrets. It was not the lions or the Duchesses who were hunted in this twisted dance. Instead, it was the truth that was the prey in the Duke's cruel conquest.


You might ask "How did you create such a good prompt?"  Here's the secret: I didn't, GPT did. I used prompt augmentation.

### Prompt Augmentation 

Prompt augmentation is common for image generation systems like DALLE-3, where a simple prompt like "make a picture of a wharf" gets augmented to be more elaborate 

> A picturesque scene of a bustling wharf at sunset. The wharf is filled with activity, featuring docked boats of various sizes, from small fishing vessels to larger sailboats. People are seen walking along the wooden planks, some carrying fishing gear, while others are engaged in lively conversations. The setting sun casts a golden hue over the scene, with the water reflecting the vibrant colors of the sky. Seagulls fly overhead, adding to the lively atmosphere. The background shows a distant view of the town, with quaint buildings and a few trees dotting the landscape.

<img src="DALLE-wharf.png"/>

You'll get to experiment with prompt augmentation in this HW.

**For Part 1, you'll the class's Helicone account account, so you won't have to pay for to create the syntheic training data yourself.**    


## Part 2: Fine-tune a model on your data

In Part 1, you will generate stories for about 500 locations, and then use them to fine-tune our system. In Part 2 of the homework the JSON will be the *output* of the process.  We'll be training GPT to translate fiction onto a game state, so that we can make *interactive fiction*. 


In this part of the homework, you'll learn how to [fine-tune the OpenAI models](https://beta.openai.com/docs/guides/fine-tuning) to perform a specific task.  You'll fine-tune GPT-3.5-turbo with this data using the web interface on OpenAI's playground to fine-tune a model.  You can get to it by clicking on this link (https://platform.openai.com/finetune) or by clicking on the "Fine-tuning" menu item on the playground.   Once you have fine-tuned your model, via the web interface, you'll learn how to call your model via the API.


<!--
Here's an example of what my fine-tuned model produced for this short passage from the Wizard of Oz by Frank Baum
-->


**Note: for Part 2 and 3 of the HW, you'll be using your own account, so you'll pay for the fine tuning job yourself.  It will cost &dollar;20-&dollar;30 depending on your length. You should only need to run fine-tuning once.  You can reduce costs by working in a group, and/or by limiting the number of fine-training examples you use to 100 items.**    


## Part 3: Create a game from a story

For this part, let's make your own game by generating mutliple game locations with the custom stories and connect them into a text game. You can make your own write story, or pick one that you like.  Here's [a story that I wrote with GPT-3](the-eternal-country.txt), which you're welcome to use if you'd like. 

For this part you should generate 5 game states with 5 descriptions. You will have 5 locations along with the characters and items. Use your creativity here!  You'll need to do some editing to stitch your system's location JSON outputs into the game JSON format.  If you want an example of a game JSON, here's the [JSON for Action Castle](action_castle.json).

You'll play the game, and write about it in your homework writeup.

## What to submit

Please submit the following:
- Completed `hw3.ipynb`
- Your synthetic training data with your augmented prompts and descriptions `synthetic_data.jsonl`
- Your fine-tuning data `fine_tuning_data.jsonl`
- Your completed game state `custom_game.json`. 
- A game trancript `game_transcript.json` that shows that you can play it.
- A README.md with a writeup that discusses what you learned by doing the homework, and analyzes each of the 3 parts.

You should submit your completed homework to [Gradescope]({page.submission_link}).  You can work teams.  Only one team member should submit - be sure to specify who your partner was when you make your submission.  If your group is >2 students, you should do one extension per additional teammate and describe what youd di in the homework writeup.  The extensions are up to you!

## Possible Extensions

Here are some ideas for extensions you can do:

### Comparison of prompting techniques for creating fiction

In Part 1 of the homework , we have you generate stories via prompt augmentation.  As an extension you could compare how good those stories are versus simpler ways of prompting.  For instance, you could generate stories for the same locations using:

The augmented prompting technique from the HW
Your original prompt
No prompt at all (just the JSON for the scene)
You could display the different stories for a scene in random order to human judges (your teammates or your friends), and ask them to rank them from best story to worst story (allowing for ties).   If you collect judgments for many scenes, then you could see how often each prompting technique beats the others, according to human preferences.

### Comparison of fine-tuning versus few-shot prompting and zero-shot prompting

For Part 2 of the homework, we have you fine-tune GPT 3.5 to produce a JSON location from a story.  You could compare this fine-tuning strategy against few-shot prompting of GPT-4 where you give it 3-5 examples of (story, JSON) pairs.  You could also compare against a zero-shot  instruction following prompt where you give detailed instructions on what the JSON output should look like.  You could calculate how often each of the 3 strategies produces valid JSON that can be used to load a location.

### Generating Python code for Actions or Blocks

For part 3, we have you generate 5 locations and then manually edit them into a game.  We leave out several things that are needed for a game, including creating blocks and creating special actions.  You could try creating a few-shot GPT-4 model to automatically create Python code Actions or Blocks.  You could generate several examples, try to integrate them into your game by including them in a Python notebook, and then describe what you did and how well your approach worked.

### Updating game objects based on the GptParser's descriptions

In HW2, we used GPT to generate descriptions for our game.  Sometimes it hallucinated new items, or elaborated on existing items.  You could use what you learned in HW3 to try to create new in-game objects for things that the GptParser generated but aren't in the game already, and to update the descriptions of items that are already in the game to match GPT's descriptions.  Describe what you did, and show some examples.

Generating Location JSON from images

In this HW, we looked at fine-tuning GPT3.5 to generate JSON from locations from stories.  As an extension, you could try to  using GPT-4 Vision (gpt-4-vision-preview) to generate JSON by giving several examples of images (user) paired with JSON (assistant) in a few-shot prompt.  Then the user could give a new image, and it would generate game JSON describing that location.  You can document your prompt and how you created it, along with some example outputs, and your qualitative impressions of them.

Creating an interactive world builder

For part 3, we have you generate 5 locations and then manually edit them into a game.  Could you build a tool that allows a user to create the whole world interactively, rather than having to manually edit JSON together?




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
