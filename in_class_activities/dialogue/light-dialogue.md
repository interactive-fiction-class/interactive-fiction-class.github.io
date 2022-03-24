---
layout: default
img: dialogue.png
img_link: https://xkcd.com/1423/
caption: Conversation 
title: Train GPT-3 to Perform Dialogue for NPCs
type: in-class
active_tab: homework
release_date: 2022-03-24
due_date: 2022-03-28 23:59:00EST
materials:
    - 
        name: Colab Notebook for training GPT3 on LIGHT Dialogue
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/dialogue/Fine-Tune_OpenAI_on_LIGHT_Dialogues.ipynb
submission_link: XXX
readings:
    -
      title: How to Motivate Your Dragon&colon; Teaching Goal-Driven Agents to Speak and Act in Fantasy Worlds
      authors: Prithviraj Ammanabrolu, Jack Urbanek, Margaret Li, Arthur Szlam, Tim Rocktäschel, Jason Weston
      url: https://arxiv.org/pdf/2010.00685.pdf
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
{% else %}
<!-- Homework assignment -->
<div class="alert alert-info">
This assignment is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>

{% endif %}

{% if page.materials %}
<div class="alert alert-info">
The materials that you will need for this in-class activity are:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}



In Class Activity: Train GPT-3 to Perform Dialogue for NPCs
=============================================================

Today in class you will train GPT-3 to perform dialogue for non-player characters in games.  We will use a different part of [Facebook's LIGHT dataset](https://parl.ai/projects/light/), which we previously used to generate descriptions for items and locations in our text adventure games.  


# Characters in LIGHT 


Characters have a description, a persona (a first person description of who they are and what their motivations might be), a character type (person, creature or object), a location (```in_room_id```) and an inventory (```carrying_objects```).

Here is an example of the Gravedigger character.
```python
light_environment['characters']['203']

{'base_form': ['gravedigger'],
 'carrying_objects': [890],
 'char_type': 'person',
 'character_id': 203,
 'corrected_name': 'gravedigger',
 'desc': 'You might want to talk to the gravedigger, specially if your looking for a friend, he might be odd but you will find a friend in him.',
 'ex_room_ids': [100, 349],
 'in_room_ids': [62],
 'is_plural': 0,
 'name': 'gravedigger',
 'orig_room_id': 349,
 'personas': ["I am low paid labor in this town. I do a job that many people shun because of my contact with death. I am very lonely and wish I had someone to talk to who isn't dead."],
 'wearing_objects': [],
 'wielding_objects': []}
 ```
 
Here are some other examples of characters' names and their personas in LIGHT.

* Witches - I only mastered one spell in witch school. I can speak with inanimate objects. I use this spell in espionage. I work for the government.
* Queen - I am second in command under the king. I have a great power of authority. I am worshiped and seen as a wise and beautiful leader.
* King - I am a king of the whole empire. I give rules and pursuit them. I am brave and fearless.
* Dragon - I am a dragon living in the mountains. I enjoy hoarding treasure. I terrorize the local populace for fun.
* Knight - I am a knight. I come from a lower-ranking noble family. I serve under the king, as my father did before me. In times of war, I fight on horseback.
* Faeries - I giggle as I toss about my hair.  Some of the male faeries take notice and give chase.  How I love to tease them!  For they will never catch me.
* Talking Cat - I am a talking cat. I can speak to humans. I have scared many, many children.
* A Rat - I stick to the edge, nose up and ready for any morsels that may drop my way. Or sometimes they don't, but I often don't know until my jaws are upon it. A hunk of moldy crust, the edge of a dropped hymnbook, it is all fair game.
* A Spider - I am a black widow spider.  I am spinning my web.  I hope to catch something delicious.  I will sit and wait until something is caught in my web.  Then it is game over for them.
Ghosts - I am a ghost that haunts a castle. I do not recall how I came to exist. I make noises when I sense someone in my vicinity.

# Dialogues in LIGHT

Here is an example conversation from LIGHT.  It's a dialogue between two characters in a specific setting.  Each character takes a turn in the conversation, which can consist of a line of dialogue, or an action (which I've maked as "stage direction" as if this were a play), or they can make a gesture (called an *emote* in the LIGHT data).

> **Setting:**
> * Watchtower - The tower is the largest section of the castle. It contains an observatory for nighttime scouting, but is also used by the wise men to study the stars. Armed guardsmen are always to be found keeping watch. 
>
> **Characters:**
> * Court wizard - I am an advisor of anything magical. I sell spells to those who need them. I am wealthy and hold an important place in political life
> * Soldier - I came from the fertile valley when I was conscripted. The king needed strong farmer's sons to fight in the war. I am very unhappy here in the cold, damp, rainy north. I miss my friends and my dog. I hope to go back to my father's farm when the war ends.
>  
> **Conversation:** <br />
> Court wizard: "A quiet night this evening..." <br />
> Soldier: "Yes it is" <br />
> Court wizard: "Have any else come up this eve? i had hoped for a quiet night to examine the stars" <br />
> Court wizard: Gestures - Ponder <br />
> Soldier: "Yes, a few came through, but it is a cold night for me, i am used to warmer weather" <br />
> Soldier: Gestures - Nod <br />
> Court wizard: "Well, you are but a common soldier.  no doubt you are used to such a lot.  thankfully i have my spells to keep me warm." <br />
> Court wizard: Gestures - Sigh <br />
> Soldier: "I am a soldier doing my job" <br />
> Soldier: Gestures - Grin <br />
> Court wizard: "Yes... well... very well then.  see that you do!  no slacking off while your betters are about." <br />
> Soldier: "No sir" <br />
> Court wizard: "When, for example, was this horn last tested?  it looks dented.  how can we be sure it will work?" <br />
> Soldier: "A year ago, test it out or cause a need to use it" <br />
> Court wizard: "Mayhap i will speak to the king about such lackness.  or perhaps i can sell him a spell that will serve just as well." <br />
> Court wizard: Gestures - Frown <br />
> Soldier: "Good idea, i agree, go do that" <br />
> Soldier: Stage Direction - Hug court wizard <br />
> Court wizard: "Get off of me, you fool!  who gave you permission to touch me!" <br />
> Court wizard: Stage Direction - Hit soldier <br />
> Soldier: "To the jail with you" <br />
> Soldier: Stage Direction - Hit court wizard <br />


### What to do

1. Open the [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Choose `Runtime > Run all`.
3. XXX


{% if page.readings %} 
## Related Readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}

