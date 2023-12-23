---
layout: default-2022
title: CIS 700 - Lectures
active_tab: lectures
---


<!-- Create a HTML anchor for the most recent lecture -->
{% assign anchor_created = false %}
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
<!-- End create a HTML anchor for the most recent lecture -->

<!--
<div class="alert alert-info">
You can <a href="https://upenn.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=8b5f2734-0738-4f52-90f5-ab3c01236b7c">watch recordings of the lecture videos online</a>.
</div>
-->

<div class="alert alert-info">
The lecture schedule will be updated as the term progresses. You can find more details under the <a href="/modules.html">Modules</a> tab.
</div>

<table class="table table-striped">
  <thead>
    <tr>
      <th>Date</th> 
      <th>Lecture Topic</th>
      <th>Activity</th>
      <th>Academic Papers</th>
      <th>Supplemental Media</th>
      <th>Homework Due</th>
    </tr>
  </thead>
  <tbody>
    {% for lecture in site.data.2022.lectures %}
	    {% assign required = nil %}
	    {% assign optional = nil %}
	    {% assign mod_num = nil %}
	    {% assign slides = nil%}
	    {% assign video = nil%}
	    {% assign speaker = nil%}
	    {% assign speaker_url = nil%}

	    <!-- Find matching section in modules -->
	    {% for module in site.data.2022.modules %}
		    {% for lesson in module.lessons %}
			    {% if lecture.title == lesson.title %}
				    {% assign mod_num = module.module_number %}
				    {% assign required = lesson.readings%}
				    {% assign optional = lesson.optional%}
				    {% assign slides = lesson.slides%}
				    {% assign video = lesson.video%}
				    {% assign speaker = lesson.guest_speaker%}
				    {% assign speaker_url = lesson.guest_url%}
				    {% assign speaker2 = lesson.guest_speaker2%}
				    {% assign speaker_url2 = lesson.guest_url2%}
				    {% break %}
			    {% endif %}
		    {% endfor %}
	    {% endfor %}


	    <!-- Create a HTML anchor for the most recent lecture -->
	    {% capture lecture_date %}{{lecture.date | date: '%s'}}{% endcapture %}
	    {% assign lecture_date = lecture_date | plus: 0 %}
	    {% assign now = now | minus: 14400 %}

	    <tr
	    {% if anchor_created != true and lecture_date >= now %}
	      {% assign anchor_created = true %}
	      id="now" 
	    {% endif %}

	    {% if lecture.type %}
	      {% if lecture.type and lecture.type == 'deadline' %}
		class="warning"
	      {% else if lecture.type and lecture.type == 'no_lecture' %}
		class="danger"
	      {% endif %}
	    {% endif %}
	    >

	    <!-- End create a HTML anchor for the most recent lecture -->
	      <td width="14%">{{ lecture.date | date: '%a, %b %-d, %Y' }}</td>
	      <td width="16%">
		 {{ lecture.title }}<br>
		 {% if mod_num %}(<a href="modules.html#module{{mod_num}}">Module {{mod_num}}</a>)
			{% if slides %}
			  <a href="{{ slides }}">[slides]</a>
			{% endif %}

			{% if video %}
			  <a href="{{ video }}">[video] </a>
			{% endif %}

			{% if speaker %}
			  {% if speaker_url %}
			    by <a href="{{ speaker_url }}">{{ speaker }}</a> 
			  {% else %} 
			  by {{ speaker }}
			  {% endif %}
			{% endif %}
		      	{% if speaker2 %}
		      	  and
			  {% if speaker_url2 %}
			    <a href="{{ speaker_url2 }}">{{ speaker2 }}</a> 
			  {% else %} 
			    {{ speaker2 }}
			  {% endif %}
			{% endif %}
		{% endif %}
	      </td>
	      <td width="12%">
		  {% for activity in lecture.activities %}
		    {% if activity.url %}
		      <a href="in_class_activities/{{ activity.url }}">{{ activity.title }}</a> 
		    {% else %}
		      {{ activity.title }}
		    {% endif %}
		  {% endfor %}
	      </td>
	      <td>
		{% if required %} 
		<ul>
		  {% for reading in required %}
		    <li>
		    {% if reading.url %}
			{{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a> 
		      <br />
		    {% else %}
		       {{ reading.authors }}, {{ reading.title }} 
		      <br />
		    {% endif %}
		    </li>
		  {% endfor %}
		</ul>
		{% endif %}
	      </td>
	       <td>
		{% if optional %} 
		<ul>
		  {% for reading in optional %}
		    <li>
		    {% if reading.url %}
			{{ reading.authors }}, <a href="{{ reading.url }}">{{ reading.title }}</a> 
		      <br />
		    {% else %}
		       {{ reading.authors }}, {{ reading.title }} 
		    {% endif %}
		    </li>
		  {% endfor %}
		</ul>
		{% endif %}
	      </td>
	      <td>
		{% if lecture.homework_due %} 
		  {% for hw in lecture.homework_due %}
		    {% if hw.url %}{% if hw.url contains '://' %}<a href="{{hw.url}}">{% else %}<a href="homeworks/{{hw.url}}">{% endif %}{{hw.title}}</a>
		    {% else %}{{hw.title}} 
		    {% endif %}
		    {% if hw.note %}<i>{{hw.note}}</i>{% endif %}
		  {% endfor %}
		{% endif %}
	      </td>
	    </tr>
    {% endfor %}
    
  </tbody>
</table>

