---
layout: default
title: Modules
active_tab: recordings
---


<div class="alert alert-info">
Below, you'll find links to pre-recorded lectures. You can also <a href="https://upenn.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=82b51ccf-a22c-44fb-9582-ad99000835ae">find recordings of the live lectures from this semester on Panoto</a>.  You don't have to watch both sets of recordings - you can pick either the pre-recorded lectures or the live lectures. 
</div>



<!-- Create a HTML anchor for the most recent module -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% assign now = now | plus: 0 %}
<!-- End create a HTML anchor for the most recent module -->




{% for module in site.data.modules %}


<!-- Create a HTML anchor for the most recent module -->
{% capture module_start_date %}{{module.start_date | date: '%s'}}{% endcapture %}
{% capture module_end_date %}{{module.end_date | date: '%s'}}{% endcapture %}
{% assign module_start_date = module_start_date | plus: 0 %}
{% assign module_end_date = module_end_date | plus: 0 %}


{% if module_start_date <= now and module_end_date >= now %}
<a name="now"></a> 
{% endif %}


# Module {{ forloop.index }}: {{module.title}}




{{module.description}}


{% if module.intro_video %}  * **Intro:** Module {{ forloop.index }} [[Video]]({{module.intro_video}}) {% endif %}
{% for lesson in module.lessons %}
* **Lesson {{ forloop.index }}:** {{lesson.title}}
{%if lesson.video %}[[Video]]({{lesson.video}}){% endif %}
{% endfor %}


{% if module.slides %}
Slides: [[Slides]](slides/{{module.slides}})
{% endif %}


{% if module.readings %} 
Readings:
{% for reading in module.readings %}
{% if reading.url %}
*  {% if reading.optional %}<b>Optional:</b> {% endif %} {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a> 
{% else %}
*  {% if reading.optional %}<b>Optional</b> {% endif %} {{ reading.authors }}, {{ reading.title }} 
{% endif %}
{% endfor %}
{% endif %}

{% if module.homework %} 
Homework:

<ul>
{% for page in site.pages %}
{% capture due_year %}{{page.due_date | date: '%Y'}}{% endcapture %}

{% if page.title contains module.homework %}
<li><a href="{{page.url}}">{{ page.title }}</a> {% if this_year == due_year %}  (due {{ page.due_date | date: "%A, %B %-d, %Y" }}) {% endif %}</li>
{% endif %}
{% endfor %}
</ul>
{% endif %}



{% if module.quiz %} 
Quiz:

<ul>
{% for quiz in module.quiz %}

{% capture due_year %}{{quiz.due_date | date: '%Y'}}{% endcapture %}
<li> {{ quiz.title }}  {% if this_year == due_year %}  (due {{ quiz.due_date | date: "%A, %B %-d, %Y" }})  {% endif %}</li>
{% endfor %}
</ul>
{% endif %}




{% endfor %}