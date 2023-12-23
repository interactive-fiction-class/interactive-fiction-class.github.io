---
layout: default-2022
img: adventuron.png
img_link: https://en.wikipedia.org/wiki/Zork#/media/
caption: Adventuron is a development platform for text adventure games
title: Optional Extra Credit for HW1
type: Extra Credit
number: 1
active_tab: homework
release_date: 2022-01-17 
due_date: 2022-02-07 23:59:00EST
materials:
    -
      name: Adventuron Documentation
      url: https://adventuron.io/documentation/
    -
      name: Pixray Colab Notebooks
      url: https://github.com/pixray/pixray_notebooks
    - 
      name: (OPTIONAL) Colab notebook by CCB to Generte Art in the Style of Different Artists
      url: https://colab.research.google.com/drive/1JKtGgt6wj2u0xOTDFk9cFkT6XMTyislA?usp=sharing
    - 
      name: (OPTIONAL)  Another notebook by CCB to Generte Art Using Images as Input
      url: https://colab.research.google.com/drive/1utUKewWzXYaG0Fj6FUcOX-mc-YAwC02h?usp=sharing
submission_link: https://www.gradescope.com/courses/354158/assignments/1796853/
readings:
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

For up to one point of extra credit, you can extend our [text adventures](text-adventure-game.md) with either or both of the following ideas:

* Export the games from our colab format to Adventuron, which is a platform for developing text adventure games.
* Generate art for our games automatically using neural networks. 

## Adventuron 

Adventuron is a platform for developing text adventure games. Adventuron  was designed to teach young kids some programming concepts. Adventuron uses a particular file format, and then generates HTML files for the games that you can host on websites like itch.io.  

For this part of the extra credit, you should write a program to export our CoLab notebook games to the Adventuron file format.  The file format is documented [here](https://adventuron.io/documentation/#_reference_guide).  You should implement
* [Locations](https://adventuron.io/documentation/#QuickStartLocations)
* [Objects](https://adventuron.io/documentation/#QuickStartObjects)
* [Barriers](https://adventuron.io/documentation/#QuickStartBarriers)

You aren't required to implement [special commands](https://adventuron.io/documentation/#QuickStartCommands) or [precondition variables](https://adventuron.io/documentation/#QuickStartBooleanExpressions), but if you figure out how to do it, go for it!

You should test your code by trying to export Action Castle into the Adventuron format and then run it in [Adventuron Classroom](https://adventuron.io/classroom/), which is a development environment.  You should be able to play the exported game by pressing the Play button. 

### What to submit

* A colab notebook to take the HW1 game and export it to a text file that is in the Adventuron file format.  
* A README that describes 
1. how to run your program
2. which aspects of our text adventure games are properly exported and which you're not able to export.


You can submit your files to [Gradescope]({{page.submission_link}}).


## Graphics

Despite being called "text adventure games", with the advent of computer graphics, text adventure games began to featured graphics that depicted locations and items. Because computer graphics were in their infancy when adventure games had their heyday, the graphics used in them were 8-bit and pixelated.  This aesthetic lives on in many modern indie text adventure games. 



For the graphics EC, you should adapt the [Pixray colab notebook](https://github.com/pixray/pixray) developed by an artist named [Tom White aka dribnet](https://drib.net/about) who makes art with nerual networks.  Pixray takes in text prompts and generate pixelated artwork that represents the rompt.  Here are some scenes from Action Castle that I generated using Pixray:





<div class="container-fluid">
  <div class="row">


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/cottage.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Inside Cottage #pixelart
  </li>
  </ul>
</div>


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/garden_path.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Cottage on Garden Path #pixelart
  </li>
  </ul>
</div>


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/great_hall.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Great Hall #pixelart
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/rosebush.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Rosebush #pixelart
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/throne_room.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Throne Room #pixelart
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/candle-lit.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> A candle with ancient runes burning in the dark #pixelart
  </li>
</ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/pixel_art/ghost.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> skeletal king haunting a dark room #pixelart
  </li>
</ul>
</div>

</div>
</div>


I also generated art for Action Castle with in a non-pixelated style using CLIP+GANs.  Here are some examples of that art.  Since it was a castle theme, I appended the phrase "medieval art" to the text prompts to try to influence the style of the art. 



<div class="container-fluid">
  <div class="row">


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/locations/cottage/cottage.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Inside Cottage - medieval art
  </li>
  </ul>
</div>


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/locations/garden_path/garden_path.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Cottage on a garden path - medieval art
  </li>
  </ul>
</div>


<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/locations/feasting_hall/feasting_hall.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Feasting Hall - medieval art
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/items/rosebush/rosebush.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Rosebush - medieval art
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/locations/throne_room/throne_room.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> Throne Room  - medieval art
  </li>
  </ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/items/candle/candle.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> A candle with strange runes - medieval art
  </li>
</ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/items/ghost/ghost.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> skeletal king haunting a dark room - medieval art
  </li>
</ul>
</div>



<div class="col-lg-4 col-md-6 col-xs-12" style="margin-bottom: 20px;">
  <ul class="list-unstyled">
  <li>
        <img src="https://github.com/interactive-fiction-class/interactive-fiction-class.github.io/blob/master/homeworks/text-adventure-game/action_castle_art/items/troll/troll.png?raw=true" class="img-rounded" style="height: 100%; width: 100%; max-height: 250px; max-width: 250px;" />
  </li>
  <li>
    <b>Prompt:</b> hungry troll - medieval art
  </li>
</ul>
</div>

</div>
</div>


I got really excited about generating art with neural nets, so I also tried [generating art in the style of different artists](https://drive.google.com/drive/folders/1yf7r2pRAdNXP7wXGjA_p0V6Swpte8I7r?usp=sharing).  Here's an example of a few hundred different versions of ["cottage on a garden path"](https://drive.google.com/drive/folders/1vuAJvTLdNMRBIoxERfNQDl-BmMbr2ABM?usp=sharing) and ["inside cottage"](https://drive.google.com/drive/folders/1FeZjwixKaJEFf_1qcdI5zYPPRM_9aCaN?usp=sharing) in the style of different artists. 


For this extra credit assignment, you should write a colab notebook to 
1. Create an image using pixray for every location and object in the game, saving them to Google drive
2. Experiment with different prompts as input to pixray, allowing the user to select pixel art versus non-pixel art, and to attach their own keywords like "medieval art" for action castle.  
3. Display the images in when playing text adventure game in our colab notebook. 
4. Optionally, write a function that generates many different pictures for the same object/location in the game and then lets someone interactively pick their favorites.  It could remember the keywords that the user liked, and then use other images in that style.


## What to submit

* Your Colab notebook, along with clear instructions on how to run it
* A README file that explains what you tried, and what worked best
* A zip file with your best images for each location/item in action castle.

You can submit your files to [Gradescope]({{page.submission_link}}).


{% if page.readings %} 
## Recommended readings
{% for reading in page.readings %}
* {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a>.  <i>{{ reading.note }}</i>
{% endfor %}
{% endif %}
