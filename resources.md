---
title: CMSC 491/691-11 - Resources
layout: default
img: play-if-card.png
active_tab: resources 
---

# Resources

## Story Datasets

<table class="table table-striped">
  <thead>
    <tr>
      <th>Dataset</th> 
      <th>Papers</th>
      <th>Paper Code</th>
      <th>Hugging Face Link</th>
      <th>Leaderboard</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.datasets %}
	<tr>
	<td width="20%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="30%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	<td width="10%">
	 {% if dataset.code %}
	 <a href="{{dataset.code}}">{{dataset.code}}</a>
	 {% endif %}
	</td>
	
	<td width="10%">
	 {% if dataset.hugging_face %}
	 <a href="{{dataset.hugging_face}}">{{dataset.hugging_face}}</a>
	 {% endif %}
	</td>
	
	<td width="10%">
	 {% if dataset.leaderboard %}
	 <a href="{{dataset.leaderboard}}">{{dataset.leaderboard}}</a>
	 {% endif %}
	</td>
	
	</tr>
{% endfor %}
</tbody>
</table>

## Mixed Visual + Textual Datasets


<table class="table table-striped">
  <thead>
    <tr>
      <th>Dataset</th> 
      <th>Papers</th>
      <th>Paper Code</th>
      <th>Hugging Face Link</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.vision %}
	<tr>
	<td width="16%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="30%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	<td width="20%">
	 {% if dataset.code %}
	 <a href="{{dataset.code}}">{{dataset.code}}</a>
	 {% endif %}
	</td>
	
	<td width="20%">
	 {% if dataset.hugging_face %}
	 <a href="{{dataset.hugging_face}}">{{dataset.hugging_face}}</a>
	 {% endif %}
	</td>
	
	
	</tr>
{% endfor %}
</tbody>
</table>



## Cloze Tests

<table class="table table-striped">
  <thead>
    <tr>
      <th>Dataset</th> 
      <th>Papers</th>
      <th>Leaderboard</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.eval %}
	<tr>
	<td width="40%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="50%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	
	<td width="10%">
	 {% if dataset.leaderboard %}
	 <a href="{{dataset.leaderboard}}">{{dataset.leaderboard}}</a>
	 {% endif %}
	</td>
	
	
	</tr>
{% endfor %}
</tbody>
</table>




## Data Scrapers & Processors

* [Archive of Our Own Scraper](https://github.com/radiolarian/AO3Scraper)
* [Fanfiction Scraper](https://github.com/smilli/fanfiction)
* Process your own book data: [BookNLP](https://github.com/booknlp/booknlp)

## IF Environments

<table class="table table-striped">
  <thead>
    <tr>
      <th>Dataset</th> 
      <th>Papers</th>
      <th>Paper Code</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.if %}
	<tr>
	<td width="16%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}}{% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="50%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	
	<td width="30%">
	 {% if dataset.code %}
	 <a href="{{dataset.code}}">{{dataset.code}}</a>
	 {% endif %}
	</td>
	
	
	</tr>
{% endfor %}
</tbody>
</table>



## Planning Systems

<table class="table table-striped">
  <thead>
    <tr>
      <th>Planner/Code</th> 
      <th>Papers</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.planning %}
	<tr>
	<td width="16%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="50%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	</tr>
{% endfor %}
</tbody>
</table>

## Character Modeling

* [Versu](https://versu.com/)
* [Character Relations](https://github.com/dbamman/characterRelations)

## Knowledge Bases

<table class="table table-striped">
  <thead>
    <tr>
      <th>Knowledge Base</th> 
      <th>Papers</th>
      <th>Hugging Face Link</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.knowledge %}
	<tr>
	<td width="16%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="50%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	<td width="30%">
	 {% if dataset.hugging_face %}
	 <a href="{{dataset.hugging_face}}">{{dataset.hugging_face}}</a>
	 {% endif %}
	</td>
	</tr>
{% endfor %}
</tbody>
</table>



## Other Code

<table class="table table-striped">
  <thead>
    <tr>
      <th>Code</th> 
      <th>Papers</th>
    </tr>
  </thead>
  <tbody>


{% for dataset in site.data.resources.other %}
	<tr>
	<td width="16%">
	 {% if dataset.url %}
	 <a href="{{dataset.url}}">{{dataset.name}}</a> {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% else %}
	 {{dataset.name}} {% if dataset.info %} - {{dataset.info}} {% endif %}
	 {% endif %}
	</td>
	
	<td width="50%">
	 {% if dataset.paper1 %}
	 <a href="{{dataset.paper_url1}}">{{dataset.paper1}}</a>
	 {% endif %}
	 {% if dataset.paper2 %}
	 and
	 <a href="{{dataset.paper_url2}}">{{dataset.paper2}}</a>
	 {% endif %}
	</td>
	
	</tr>
{% endfor %}
</tbody>
</table>


### Libraries & Toolkits
* [Hugging Face](https://huggingface.co/) - Hugging Face provides state-of-the-art general-purpose neural language model architectures like BERT, GPT-2, and others.
* [Hugging Face Transformer Library](https://github.com/huggingface/transformers)
* [AllenNLP](https://allennlp.org) - Deep learning for NLP with state of the art models
* [Spacy](https://spacy.io) - Industrial-Strength Natural Language Processing in Python
* [NLTK - Natural Language Toolkit](https://www.nltk.org/) - Basic NLP tools for Python & interfacing with some external models
* [Stanford NLP](https://nlp.stanford.edu/software/)
* [Stanza](https://stanfordnlp.github.io/stanza/) - Stanford NLP for Python
* [ConvKit](https://convokit.cornell.edu/) - Cornell Conversation Analysis Toolkit

## Tutorials 

* [How To Make Custom AI-Generated Text With GPT-2](https://minimaxir.com/2019/09/howto-gpt2/) by [Max Woolf](https://minimaxir.com)
* [BERT End to End (Fine-tuning + Predicting) in 5 minutes](https://colab.research.google.com/github/tensorflow/tpu/blob/master/tools/colab/bert_finetuning_with_cloud_tpus.ipynb)
* [How to use Google Speech to Text API to transcribe long audio files](https://towardsdatascience.com/how-to-use-google-speech-to-text-api-to-transcribe-long-audio-files-1c886f4eb3e9)
* [Video Tutorial - Beginners Guide To Coding An Illustrated Text Adventure Game (with Adventuron Classroom)](https://adventuron.blogspot.com/2019/07/video-tutorial-beginners-guide-to.html) by Chris Ainsley

## Extras

### Noteable IF Games in Research
* [Save the Date](http://paperdino.com/save-the-date/) by [Chris Cornell (Montolli)](http://paperdino.com/)
* [The Icebound Concordance](https://www.ice-bound.com/) by [Aaron Reed](http://aaronareed.net/) and [Jacob Garbe](http://www.jacobgarbe.com/)
* [Prom Week](https://promweek.soe.ucsc.edu/)
* [Façade](https://www.playablstudios.com/facade)

### Inspiration

* [Actual Play Podcasts](https://www.polygon.com/podcasts/2018/9/26/17860176/best-dungeons-dragons-dd-podcasts-tabletop-gaming) - both of our favorite is The Adventure Zone
* [Giant list of Actual Play Podcasts](https://tabletopbellhop.com/actual-play-podcasts/)
* Play games with friends on [Roll 20](https://roll20.net/)
* [chooseyourstory.com](http://chooseyourstory.com)
* [AI Dungeon](https://play.aidungeon.io)
* Try some games on [Itch.io](https://itch.io/games/tag-interactive-fiction/tag-text-based) to figure out what you like and don't like in an IF game
* [Interactive Fiction Database](https://ifdb.org/)
* [Interactive Fiction Wiki](https://www.ifwiki.org/)

### Other Courses

* Nick Montfort's [Interactive Narrative](https://nickm.com/classes/interactive_narrative/2019_fall/) course at MIT

### Content Generation for TRPGs and IF

* [Print graph paper](http://print-graph-paper.com) - just blank graph paper!
* [Random Generators for Tabletop Games](https://donjon.bin.sh)
* [TesselationPlot for RPG Maps](https://community.wolfram.com/groups/-/m/t/1794056)
* [RPG Map Editor 2](https://deepnight.net/tools/rpg-map/)
* [RPGgen](https://www.rpggen.dev/) - a collection of generators

### Other Languages for Writing Interactive Fiction

* [Adventuron Classroom](https://adventuron.io/classroom/)
* [Tracery](http://tracery.io/) ([repo](https://github.com/galaxykate/tracery/tree/tracery2))
* [ink](https://www.inklestudios.com/ink/) ([repo](https://github.com/inkle/ink))
* [Twine](https://twinery.org/) ([repo](https://github.com/tweecode/twine))
* [Inform 7](http://inform7.com/)
* [ADRIFT](https://www.adrift.co/)
* [TADS](http://www.tads.org/)
* [Quest](http://textadventures.co.uk/quest/)
* [Storychoices](http://wiki.failbettergames.com/)
* [Varytale](http://www.varytale.com/home.php)
