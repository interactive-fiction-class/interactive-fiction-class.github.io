---
layout: default-2022
title: Alexa Action Castle
img: alexas.jpg
img_link: https://www.amazon.com/alexa-setup-guide/b?ie=UTF8&node=17978645011
caption: Alexa, tell me a story.
type: Homework
number: 6
active_tab: homework
release_date: 2022-03-22 
due_date: 2022-04-11 23:59:00EST
materials:
    - 
        name: Lambda Function Zip
        url: https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/raw/71a272ddeb413a8c399f37f1a527c77d771509a1/homeworks/alexa_action_castle/lambda.zip
    - 
        name: Parsely&colon; Preview n' Play Edition (this contains the Action Castle game).  
        url: http://www.memento-mori.com/pdf/parsely-preview-n-play-edition
    - 
        name: Text from Action Castle  
        url: https://raw.githubusercontent.com/interactive-fiction-class/interactive-fiction-class.github.io/master/homeworks/text-adventure-game/action_castle_text.txt
submission_link: https://www.gradescope.com/courses/354158/assignments/1944235
readings:
    - title: Your First Alexa Skill
      authors: Amazon Alexa
      url: https://developer.amazon.com/en-US/alexa/alexa-skills-kit/start?sc_category=paid&sc_channel=SEM&sc_campaign=SEM-GO%5EBrand%5EAll%5ELD%5EProfessional_Developer%5EEvergreen%5EUS%5EEnglish%5ETex&sc_publisher=GO&sc_content=content&sc_detail=379690615170&sc_funnel=convert&sc_country=US&sc_keyword=how%20to%20make%20a%20alexa%20skill&sc_place=&sc_trackingcode=e&sc_segment=&sc_medium=paid%7CSEM%7CSEM-GO%5EBrand%5EAll%5ELD%5EProfessional_Developer%5EEvergreen%5EUS%5EEnglish%5ETex%7CGO%7Ccontent%7C379690615170%7Cconvert%7CUS%7Chow%20to%20make%20a%20alexa%20skill%7C%7Ce%7C&gclid=CjwKCAjwoduRBhA4EiwACL5RP7Rzwe-X7mZ-Ov4XLlWf2zCOoVCM2oEw2c1Q1pc6cNpDN6jDFWXxbxoCzKcQAvD_Bw
    - title: Adventuron Classroom
      authors: Chris Ainsley / Adventuron Software Limited
      url: https://adventuron.io/classroom/
      note: This is a tutorial aimed at teaching elementary school kids how to program by writing a text adventure game.  I modeled our text adventure game after this Adventuron system.
    - title: How to Make a Text-Based Adventure - Commands and Parser
      authors: The Hitchhiker's Guide to the Galaxy (H2G2)
      url: https://h2g2.com/edited_entry/A20600641
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

For this homework you will re-implement your Action Castle game from [Homework 1](/homeworks/text-adventure-game/text-adventure-game.html) but turning it into a task-oriented dialog system, specifically in the form of a "Skill" for Amazon Alexa. You will be able to reuse a lot of the code you wrote in Homework 1, but the focus of this homework will be to implement _commands_ using Alexa Intents and a _command parser_ by creating Alexa Request Handlers. You can use the original Action Castle game, or if you want to be creative, you can implement any other interactive fiction game you would like. We will play all of your games and give full credit if there are no errors in the flow of the game. 

You will not be using Colab for this assignment.

### Definitions

Before we explain what you will be doing, there are first some Alexa-specific terms we need define.

* **Skill:** A 3rd party application for Amazon Alexa.
* **Request:** What the user is trying to accomplish when they talk to Alexa.
* **Request Handler:** The processes that send and receive requests.
* **Intent:** A schema for capturing the Request (i.e., taking a command and turning it into something Alexa can work with).
* **[Slot](https://medium.com/enpit-developer-blog/alexa-what-are-slots-and-how-to-read-slot-values-ea050047df0c):** Variables within an Intent.
* **Interaction Model:** Determines whether the current Skill can handle certain Requests.

### Starter Code

We have provided [starter code for an Alexa adventure game](https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/raw/71a272ddeb413a8c399f37f1a527c77d771509a1/homeworks/alexa_action_castle/lambda.zip).  You are free to modify it however you want and bring in any dependencies you feel will be useful, but do not forget to add them to `requirements.txt`.

* The `lambda_function.py` file contains all of the Request Handlers. Add your Request Handlers here.
* `game_classes.py` and `game_utils.py` hold all of the Action Castle code. Put your game code here.
* `constants.py` is just a list of global constants you want the entire application to have access to. You might not need this.
* You probably won't need to edit `utils.py` unless you want to add extra utilities.


#### Setting up the Environment
![Click on the "Console" button](/assets/img/developer.png)
Sign in to the [Alexa Developer Console](https://developer.amazon.com/en-US/alexa/alexa-skills-kit/start?sc_category=paid&sc_channel=SEM&sc_campaign=SEM-GO%5EBrand%5EAll%5ELD%5EProfessional_Developer%5EEvergreen%5EUS%5EEnglish%5ETex&sc_publisher=GO&sc_content=content&sc_detail=571868003723&sc_funnel=convert&sc_country=US&sc_keyword=alexa%20developer%20console&sc_place=&sc_trackingcode=e&sc_segment=&sc_medium=paid%7CSEM%7CSEM-GO%5EBrand%5EAll%5ELD%5EProfessional_Developer%5EEvergreen%5EUS%5EEnglish%5ETex%7CGO%7Ccontent%7C571868003723%7Cconvert%7CUS%7Calexa%20developer%20console%7C%7Ce%7C&gclid=CjwKCAjwoduRBhA4EiwACL5RP8suprxHnexM4TslG_jvjmEYp2-lbEjkdUA-sCXTwZ2URKafzWGjshoCYREQAvD_BwE) (see image above). 

Then click on "Create Skill". Select the *Custom Model* and *Alexa Hosted (Python)* options. In the next page select the *Start from Scratch* option.  Once you create your skill, click on it and go on the `Code` tab. There you can copy and paste the template files we gave you in `lambda.zip`, or even better, you can use Python's `import` functionality. 

#### What to Do
You will be defining a set of [Amazon Intents](https://developer.amazon.com/en-US/docs/alexa/interaction-model-design/design-the-custom-intents-for-your-skill.html) and implementing [Request Handlers](https://developer.amazon.com/en-US/docs/alexa/alexa-skills-kit-sdk-for-java/handle-requests.html) to parse them.  You may find it useful to look into the [ASK Skills Documentation](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/api/core.html).

In `lambda_function.py`, each Request Handler has its own class, and within that class there is a `can_handle()` function and a `handle()` function. `can_handle()` is where you specify the Intent (aka the keywords) to trigger this. `handle()` is what will happen when it's triggered.

Add a new Handler class for each command and then add it to the `SkillBuilder()` at the end of the file with the command  `sb.add_request_handler(yourHandlerClass())`.
*Note:* We have implemented the "direction" Request Handler for you (lines 30-70 of `lambda_function.py`). You will still have to implement the Intents in the Interaction Model. You can use the "direction" Request Handler as a guide for creating other Request Handlers. 

Once you have your Handlers all setup, you need to add them to the Interaction Model as Intents. You can find the Intents in the Developer Console by going to the "Build" tab, selecting "Interaction Model" and then "Intents". The Intents page should look something like this:
![Interaction Model](/assets/img/intents.png)


#### Some Useful Commands
* `ask_utils.is_request_type(type)(handler_input)`: checks if the Request type is equal to the input type. 
* `ask_utils.is_intent_name(name)(handler_input)`: checks if the Request Intent name is equal to the input name.
* `ask_utils.request_util.get_slot(handler_input, slot_name)`: returns an object of the Slot with name slot_name. You can use obj.value to get the string name of the Slot. 


### Debugging:
* You can test your Skill in the *Test* tab of the console. The logs from there will be on [CloudWatch](https://aws.amazon.com/cloudwatch/).
    * **Important:** To start the Skill, you will first need to say/type: `open action castle`
* You can use [CloudWatch](https://aws.amazon.com/cloudwatch/) to debug your code. When you are in the Code tab in the Alexa developer console, you can click on CloudWatch logs to be directed on your skill’s log output. 


### Invite Beta Testers

In order to submit your code, you should invite the TAs as beta testers. [Here are the instructions](https://developer.amazon.com/en-US/docs/alexa/custom-skills/skills-beta-testing-for-alexa-skills.html) on how to do this. Our emails are:`artemisp@seas.upenn.edu` & `ldugan@seas.upenn.edu`. When you release a Skill for beta testing you need to complete the _Privacy and Compliance Component_. You can safely answer *no* to all those questions.  


## What to Submit

You should invite the TAs to be beta testers for your Skill, as instructed in the relevant section above. You should also submit:

1. A text file called `playthrough.txt` with all of the commands that we would need to complete your game. It shold be a plain text file with one command per line.
2. A zipped folder called `lambda.zip` that contains the code for your game.

Submissions should be done on [Gradescope]({{page.submission_link}}).

## Grading
<div class="alert alert-warning" markdown="1">
* Play through runs fully (full points)
* Play through runs but not complex enough (50% points)
* Playthrough plays partially but errors at some point (50% points)
* Skill does not start up but code shows effort (30% points)
* The code and the play through show inadequate exploration of Alexa API documentation (0% of the points)
</div>

{% if page.readings %} 
## Recommended Readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
