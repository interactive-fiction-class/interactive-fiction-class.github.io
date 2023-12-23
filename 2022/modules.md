---
layout: default-2022
title: CIS 700 - Modules
active_tab: modules
---
<!-- Create a HTML anchor for the most recent module -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% assign now = now | plus: 0 %}
<!-- End create a HTML anchor for the most recent module -->

{% for module in site.data.2022.modules %}<a href="#module{{module.module_number}}">[Module {{module.module_number}}]</a> {% endfor %}


{% for module in site.data.2022.modules %}


<!-- Create a HTML anchor for the most recent module -->
{% capture module_start_date %}{{module.start_date | date: '%s'}}{% endcapture %}
{% capture module_end_date %}{{module.end_date | date: '%s'}}{% endcapture %}
{% assign module_start_date = module_start_date | plus: 0 %}
{% assign module_end_date = module_end_date | plus: 0 %}


{% if module_start_date <= now and module_end_date >= now %}
<a name="now"></a>
{% endif %}
<div id="module{{ module.module_number}}"></div>
# Module {{ module.module_number}}: {{module.title}}

<i>{{ module.start_date | date: "%A, %B %-d, %Y" }} to {{ module.end_date | date: "%A, %B %-d, %Y" }}</i>


{{module.description}}

{% if module.hw %} 
### Homework
{% capture this_year %}{{now | date: '%Y'}}{% endcapture %}
<ul>
{% for hw in module.hw %}

	{% capture due_year %}{{hw.due_date | date: '%Y'}}{% endcapture %}

	<li> <a href="homeworks/{{hw.url}}">{{ hw.title }}</a>{% if this_year == due_year %}, due {{ hw.due_date | date: "%A, %B %-d, %Y" }} at 11:59PM EST ({{hw.percentage}} of final grade) {% endif %}</li>
{% endfor %}
</ul>
{% else %}
No homework for this module.
{% endif %}


{% for lesson in module.lessons %}
### Lesson {{ forloop.index }}: {{lesson.title}}{% if lesson.slides %} [[Slides]]({{lesson.slides}}){% endif %}{%if lesson.video %} [[Video]]({{lesson.video}}){% endif %}
{% if lesson.guest_speaker %} Guest Lecturer: <a href="{{ lesson.guest_url }}">{{lesson.guest_speaker}}</a>{% endif %}
{% if lesson.guest_speaker2 %} and <a href="{{ lesson.guest_url2 }}">{{lesson.guest_speaker2}}</a>{% endif %}

{% if lesson.presentations %}
{% for pres in lesson.presentations %}
*  <i><a href="{{ pres.url }}">{{ pres.title }}</a></i> - presented by {{ pres.presenters }}
{% endfor %}
{% endif %}


<b>Academic Papers:</b>
{% if lesson.readings %}
{% for reading in lesson.readings %}
{% if reading.url %}
*  {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}{% if reading.length %} (video, {{reading.length}}){% endif %}</a>
{% else %}
*  {{ reading.authors }}, {{ reading.title }}
{% endif %}
{% endfor %}
{% else %}
<div style="display: inline-block; margin-left: 39px;">None</div>
{% endif %}

{% if lesson.optional %} 
<b>Supplemental Media:</b>
{% for reading in lesson.optional %}
{% if reading.url %}
*  {{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}{% if reading.length %} (video, {{reading.length}}){% endif %}</a> 
{% else %}
*  {{ reading.authors }}, {{ reading.title }}
{% endif %}
{% endfor %}
{% endif %}
{% endfor %}

<hr>

{% endfor %}
