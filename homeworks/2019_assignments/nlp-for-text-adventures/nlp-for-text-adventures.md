---
layout: default
img: ELIZA.jpg
img_link: https://en.wikipedia.org/wiki/ELIZA
caption: ELIZA was an early natural language processing program created in the 1960s.
title: NLP for Text-Adventure Games
type: Homework
number: 2
active_tab: homework
release_date: 2020-01-24 
due_date: 2020-01-30 13:30:00EST
attribution: This homework was developed by Daphne Ippolito and Chris Callison-Burch for their  Interactive Fiction and Text Generation class (CIS 700-008) which was taught at the University of Pennsylvania in Spring of 2020.
materials:
    - 
        name: NLP for Text Adventure Games - part 1 (WordNet)
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_1.ipynb
    - 
        name: NLP for Text Adventure Games - part 2 (Word Embeddings)
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_2.ipynb
    - 
        name: NLP for Text Adventure Games - part 3 (Other NLP technologies)
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_3.ipynb
submission_link: https://www.gradescope.com/courses/78405
readings:
-
   title: Vector Semantics and Embeddings 
   authors: Dan Jurafsky and James H. Martin
   venue: Speech and Language Processing (3rd edition draft)
   type: textbook
   url: https://web.stanford.edu/~jurafsky/slp3/6.pdf
-
   title: Magnitude - A Fast, Efficient Universal Vector Embedding Utility Package
   authors: Ajay Patel, Alexander Sands, Chris Callison-Burch, Marianna Apidianaki
   venue: ACL 2018
   type: conference
   url: https://www.aclweb.org/anthology/D18-2021/
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

In the earliest text adventure games, parsers used exact string matching. If a command wasn't in either the form `verb` or `verb object`, the parser would not recognize it. However, parsers and natural language processing (NLP) in general have evolved tremendously since the 1970s. NLP is a vibrant subfield of artificial intelligence.  One of the goals of NLP is to allow computers to understand commands spoken in human language.  This enables technologies like Amazon Alexa, Apple’s Siri or Google’s Assistant.


Early interactive fiction games, as well as the games you implemented for Homework 1, force players to enter commands following a strict syntax, often using the `verb object` form. Players can only say things like `pick rose` or `smell rose` if those commands have been specifically programmed into the parser. 

In this homework you will using advancements in NLP to improve your game. Using different NLP methods, you will 

1. Improve your parser using WordNet.
2. Improve your parser with word embeddings.
3. Incorporate another NLP technology or add a new game-play experience.

The first two parts are structured walkthroughs. 
The 3rd part is open-ended and allows you to apply your creativity. 
The homework deliverables are in italics; make sure to read these carefully.


## Part 1: Improve your Parser with WordNet 

We will start by improving the coverage of the parser in your text adventure game, so that it can handle a variety of user input instead of just a single hard-coded command.  This will allow the player to use other words than what you used when you wrote the command. For example, "Toss/throw/chuck the stick" will all resolve to the same command.

In part 1, we will introduce you to the WordNet resource.  WordNet is a classic resource for natural language processing.  It encodes information about synonyms, antonyms, and is-a relationships between words like _troll_ is-a _monster_.  In NLP, is-a relationships are called hypernyms or hyponyms.

For this task you should work through the ["NLP for Text Adventure Games - part 1" Python notebook](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_1.ipynb), which will introduce you to WordNet and will have you use WordNet to annotate several commands from Action Castle with their word senses, and their hypernyms and hyponyms.  This will allow you to expand out the number of possible commands that your parser can recognize.  After completing the Python notebook, I expanded the number of commands from 7 to several thousand.  

_Upon completion, the notebook saves a file called `word-sense-annotations.json`. You should submit this file to be graded._

## Part 2: Improve your Parser with Word Embeddings

Word embeddings are another NLP technology that will allow you to improving the coverage your game's parser.  Word embeddings are a way of representing the meaning of words using vectors.  This style of meaning representation is different than WordNet. Intead of having structured relationships between words like _troll_ is-a _monster_, word word vector give us a way of computing the similarity of words. This let us compute the most similar words for _troll_, which are _goblins, ogres, elves, troll, ghouls, hobbits, centaurs, unicorns, humanoids, undead,_ and _witches_.

In ["NLP for Text Adventure Games - part 2"](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_2.ipynb), we walk you through how to use a Python package for computing word vectors, called [Magnitude](https://www.cis.upenn.edu/~ccb/publications/magnitude-fast-efficient-vector-embeddings-in-python.pdf), that was developed by two former Penn undergrads.  

The notebook has one part that you are required to implement.  You should write code that uses word embeddings [to find the most similar command](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_2.ipynb#scrollTo=T8HgeMAvRNCf) to a player's input.

_Modify Action Castle from Homework 1 to support recognizing an expanded set of user inputs via WordNet and word embeddings. You can implement this support however you would like, but it should include the `construct_sentence_vector` and `find_most_similar_command` function from the [Part 2 IPython Notebook](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_e.ipynb). Write up a short explanation of how you decided to implement your expanded parser support._

## Part 3. Your Choice

Free choice! Modify your own game from Homework 1 to make it more fun to play.
You can either (1) integrate some other NLP technology into your parser, or (2) use NLP to create a new game playing experience. 

### Other Improvements to the Parser

Some ideas can be found in the  ["NLP for Text Adventure Games - part 3" Python notebook](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_3.ipynb).
This notebook doesn't have any concrete deliverables - it's just ideas for you. A few suggestions are:
1. Use sentence segmentation and coreference resolution to allow the player to chain together commands. For example: "Pick the rose. Smell it."
2. Instead of hardcoding "verb object," use dependency parsing to detect the direct object in the player's command.

_In your homework submission, include a discussion of how you implemented this improvement, and what concepts from NLP you are using. Copy and paste several example interactions with your game that showcase the new parser feature._


### Novel Gameplay Experience

NLP can facilitate gameplay that experiences that wouldn't be possible otherwise.
Use your creativity to create a new character, puzzle, or obstacle that incorporates NLP. A few suggestions are: 

* A guardswoman NPC who will only let you pass if you complement her.
* An ogre who will only marry you if speak like Shakespeare.
* Use a speech-to-text module that allows the player to speak voice commands into the computer's microphone (see part 5 of [this HW](http://artificial-intelligence-class.org/r2d2_assignments/hw4/homework4.html))
* A puzzle where the list of objects in a room is randomly generated, and the player needs to pick out the two that are most similar to each other in order to solve it.

More suggestions can be found in the demo Colab.

_In your homework submission, include a discussion of how you implemented your new gameplay feature, what concepts from NLP it uses, and why you think it makes your game more fun. Copy and paste several example interactions with your game that showcase the new feature._


## What to submit

1. A json file called `word-sense-annotations.json` containing your annotations of the Action Castle commands with their WordNet synsents, hypernyms and hyponyms.  This will be saved in your Google Drive after you complete the [Python notebook from Part 1 of this HW](https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/nlp-for-text-adventures/NLP_for_Text_Adventure_Games_part_1.ipynb).
2. An IPython notebook called`action_castle_improved.ipynb` containing an updated version of your Action Castle game that uses word embeddings and WordNet in its parser.
3. An IPython notebook called `my_game_improved.ipynb` that runs the new version of your custom game with your improvements from Part 3.
4. A text file called `playthrough.txt` with all of the commands that we need to issue to complete your game. It should be a plain text file with one command per line. (This may or may not be identical to Homework 1.)
5. A text file called `README.md`. It should include your explanation from Part 2 and your discussion from Part 3.

**IMPORTANT: We will not run or grade your code if the files are not named as described above.** 

{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
