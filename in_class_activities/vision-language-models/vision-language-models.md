---
layout: default
img: clip.png
img_link: https://blog.dataiku.com/leveraging-joint-text-image-models-to-search-and-classify-images
caption: Models Like CLIP Create Joint Text-Image Embeddings
title:  Vision Language Models Tutorial🚀
type: in-class
active_tab: homework
release_date: 2024-03-21
due_date: 2024-03-21 23:59:00EST
materials:
    - 
        name: Vision Language Models Tutorial🚀
        url: https://colab.research.google.com/drive/10q3t4BvZuPkp3ctbDejuictJosJraz97?usp=sharing
submission_link: https://www.gradescope.com/courses/704268/assignments/4259379/
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



In Class Activity: Vision Language Models Tutorial🚀
=============================================================

Today in class, play with vision language models.


**What's Inside?** 🧳
* [CLIP](https://arxiv.org/pdf/2103.00020.pdf): A quick tour of CLIP (Contrastive Language–Image Pre-training), where we'll learn how to use this model to link images with text descriptions. 🖼️💬
* [LLaVA](https://llava-vl.github.io/): Next stop is LLaVA, a Large Multimodal Language Model that generates text given an image, opening up new avenues for interactive multimodal chatbots.🤖💬

**Hands-On Fun** 🛠️

We'll be using the 🤗[`transformers`](https://huggingface.co/docs/transformers/en/index) library for interacting with these models. With it, you can wield the power of CLIP and LLaVA with just a few lines of code. Don't worry if you're new to this; we'll go step-by-step!


### What to do 

1. Open [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Save a copy to your own Google Drive 
3. Work through the notebook with one or more partners.
4. Ask if you've got any questions!


4. Please submit your work to [Gradescope]({{page.submission_link}}) by {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 


