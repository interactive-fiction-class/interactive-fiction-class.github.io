---
layout: default-2022
img: motivation.png
img_link: https://xkcd.com/2154/
caption: Motivation  
title: Experiment with the LIGHT Quest Dataset
type: in-class
active_tab: homework
release_date: 2022-03-29
due_date: 2022-04-01 23:59:00EST
materials:
    - 
        name: Colab Notebook for Characters and Quests
        url: https://colab.research.google.com/github/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/in_class_activities/dialogue-2/Characters_and_Quests.ipynb
submission_link: https://www.gradescope.com/courses/354158/assignments/1959911/
readings:
    -
      title: "How to Motivate Your Dragon: Teaching Goal-Driven Agents to Speak and Act in Fantasy Worlds"
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



In Class Activity: Characters and Quests
=============================================================

Today in class we will explore a new set of data from the Facebook AI team that created the LIGHT data set from their paper [How to Motivate Your Dragon: Teaching Goal-Driven Agents to Speak and Act in Fantasy Worlds](https://arxiv.org/abs/2010.00685). Here is the abstract for the paper.

> We seek to create agents that both act and communicate with other agents in pursuit of a goal. Towards this end, we extend LIGHT (Urbanek et al., 2019)–a large-scale crowd-sourced fantasy text-game—with a dataset of “quests”. These contain natural language motivations paired with in-game goals and human demonstrations; completing a quest might require dialogue or actions (or both). We introduce a reinforcement learning system that (1) incorporates large-scale language modeling-based and commonsense reasoning-based pre-training to imbue the agent with relevant priors; and (2) leverages a factorized action space of action commands and dialogue, balancing between the two. We conduct zero-shot evaluations using held-out human expert demonstrations, showing that our agents are able to act consistently and talk naturally with respect to their motivations.

The thing that I find exciting about this work as compared to the in-class exercise we did last week is that it will potentially allow us to add **goals** to characters to help guide their dialogue, rather than just have them perform chit-chat.


# Characters and Quests 

As we ave seen, characters in the LIGHT dataset have a description and a persona, which is a first person description of who they are.  For example:


* Queen - I am second in command under the king. I have a great power of authority. I am worshiped and seen as a wise and beautiful leader.
* King - I am a king of the whole empire. I give rules and pursuit them. I am brave and fearless.
* Dragon - I am a dragon living in the mountains. I enjoy hoarding treasure. I terrorize the local populace for fun.


In this new dataset, we add **motivations** that drive the characters.  Here is an example:

```
{
    "character": "The King Visiting The Shipyard",
    "persona": "I am the King. I rule this land, and all power is mine to hold.  My kingship is a divine right passed down from my father to me, and it will be passed down to my son someday. I live in luxury, but I am also at risk from other rulers who may want to take over my kingdom. A king must be a man of war, always prepared to defend his land.",
    "description": "You are in the Royal Shipyard.\nA massive shipyard with different Five dry docks. each dry dock has several wooden cranes and rope works. The dry docks are made of stone and the water gate is all harden wood.\nThere's a dock, a water gate is all harden wood, a rope work, a water gate, two cranes, a Fishing ships, and a rope here.\nThe thief is here.\n\nYou are carrying nothing.",
    "goal": "get rope work",
    "short_motivation": "I plan to inspect the rope work",
    "mid_motivation": "I plan to instruct the Chief Naval Engineer to build me a new warship",
    "long_motivation": "I plan to attack an enemy kingdom with my new warship",
    "timeline": [
        {
            "label": "15 minutes ago",
            "action": "hug foreman of Royal Shipyard"
        },
        {
            "label": "10 minutes ago",
            "action": "wear coveralls"
        },
        {
            "label": "5 minutes ago",
            "action": "follow foreman of Royal Shipyard"
        },
        {
            "label": "10 minutes from now",
            "action": "go Chief Naval Engineer's office"
        },
        {
            "label": "1 hour from now",
            "action": "give orders to Chief Naval Engineer"
        },
        {
            "label": "8 hours from now",
            "action": "go castle"
        }
    ]
}
```


#  Exploring the data

Today we will experiment with a few tasks that explore this dataset.

1. Given a location in a game, generate characters that might be there.  Output their names and personas.
2. Given a character and a location, generate their motivations.
3. Given a pair of characters and their motivations, genrate dialogue and see if it is different than without adding motivation.

The goal for the day is open-ended so feel free to explore other things that you're excited by.

# What to do

1. Open the [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Save a copy of the notebook into your own drive. Choose `File > Save a copy in Drive`.
3. Read through the code, and fill in the TODO sections.
4. Submit your completed notebook and your `action_castle.txt` file to [Gradescope]({{page.submission_link}}).



{% if page.readings %} 
## Related Readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}

