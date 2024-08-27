---
title: CMSC 491/691-11 - Interactive Fiction and Text Generation - UMBC
layout: default
img: heroes_journey.png
active_tab: main_page 
---

<!--
<div class="alert alert-warning" markdown="1">
Want to join the class, but didn't attend the first lecture? Here are the steps to follow:
1. [Get a permit by signing yourself up for CIS 700-001 via the waitlist system](https://forms.cis.upenn.edu/waitlist/index.php).  
2. [Do the for-credit in-class assignment from the first lecture](http://interactive-fiction-class.org/in_class_activities/play-text-adventures/play-text-adventures.html).
3. [Listen to recording of the first lecture](https://upenn.hosted.panopto.com/Panopto/Pages/Sessions/List.aspx?folderID=8b5f2734-0738-4f52-90f5-ab3c01236b7c) and [look over the slides](http://interactive-fiction-class.org/slides/text-adventure-games.pdf).
4. [Complete the first homework assignment before class on Thursday](http://interactive-fiction-class.org/homeworks/text-adventure-game/text-adventure-game.html).
</div>
-->

<!--
<div class="alert alert-success" markdown="1">
[Post your game here.](https://docs.google.com/document/d/1XpBEevYpHvLjCr-3CkAhERN_GPHsjNmkPo-Wf9KjxDs/edit?usp=sharing)
</div>
-->

<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
{% if page.type == "in-class" %}
<!-- In class activity -->
<div class="alert alert-danger">
The in-class activity for {{ page.release_date | date: "%A %b %-d" }} will be to <a href="{{page.url}}">{{ page.title }}</a>.  
</div>
<!-- Other participation activity -->
{% elsif page.type == "participation" %}
<div class="alert alert-info">
The participation activity <a href="{{page.url}}">{{ page.title }}</a> is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-success">
<a href="{{page.url}}">{{page.type}} {{page.number}}: {{page.title}}</a> has been released.  
{% if page.deliverables %}
The assignment has multiple deliverables.
<ul>
{% for deliverable in page.deliverables %}
<li>{{ deliverable.due_date | date: "%b %-d, %Y" }} - {{deliverable.description}}.</li>
{% endfor %}
</ul>
{% else %}
It is due before {{ page.due_date | date: "%I:%M%p" }} on {{ page.due_date | date: "%A, %B %-d, %Y" }}.
{% endif %}
</div>
{% endif %}
{% endif %}
{% endif %}
{% endfor %}
<!-- End alert for upcoming homework assignments -->


<!--
<div class="alert alert-success" markdown="1">
A great example of what you could build if you take this class is the [AI Dungeon](https://play.aidungeon.io/), which is an interactive fiction game  that was developed by a student at BYU using [Open AI's GPT-2](https://openai.com/blog/better-language-models/) large scale language model.
</div>
-->
<!--
<div class="alert alert-success" markdown="1">
First day of class is Thursday, January 13, 2022 at 1:45pm-3:15pm Eastern. It will take place virtually. Here is the [Zoom link](https://upenn.zoom.us/j/95868341588?pwd=a0NvbkhtUEdYTTk5d0Vmc2VvcHJrUT09). We look forward to seeing you there!
</div>
-->

# CMSC 491/691-11 - Interactive Fiction and Text Generation at UMBC

## Fall 2024

### Prerequisites 
: At least one of the following courses if you are an undergrad:
: CMSC 341 or CMSC 341H

### Course Description
: We know now that artificial intelligence (AI) can play chess, Go, or even Starcraft, but can AI play text adventure games (also known as interactive fiction)? What about roleplaying games like Dungeons & Dragons? In this course, we will be looking at the subfields of automated story generation (teaching computers to tell stories), interactive fiction (teaching computers to play through stories), and their intersection (teaching computers to tell and then play through the stories). This class will teach you about computational creativity and help develop your skills in natural language processing and cognitive modeling. 

### Learning Objectives
By the end of the course, you will be able to...
1. Understand the challenges of creating text-based games and automatically generating stories.
2. Implement and appraise the value of different technologies (Neural Language Models, Dialogue Systems, Scripts, Planning, and Commonsense Reasoning) in story generation/interactive fiction playing.
3. Argue for the appropriate components of a working story generation system or interactive fiction--playing system.
4. Create your own story generation system or interactive fiction--playing system.




<!-- 
: This class will cover several areas.
* Text Adventure Games - How they are implemented and how we can build agents that automatically solve them.
* Common-sense Reasoning - TODO
* Narrative Understanding - Extracting narrative structure (event schemas) from text
* Text Generation - Generating natural-sounding text that follows a desired style, narrative arc, or other attribute.
* Chatbots / Dialog Systems - TODO
-->

### Staff
**Instructor**
: [Lara J. Martin](https://laramartin.net)
: [laramar@umbc.edu](mailto:laramar@umbc.edu)

**Grader**
: Vineeth Nunna
: [vnunna1@umbc.edu](mailto:vnunna1@umbc.edu)

**Office Hours**
: Lara - Thursdays from 3:15-5pm in ITE 216
: Vineeth - 

### Logistics
**Time and Place**
: Fall 2024, Tuesdays & Thursdays from 11:30am - 12:45pm ET in Sondheim 110
: First day of class is August 29, 2024
: Last day of class is December 10, 2024
: Final project presentations will be held on December 12th from 10:30am - 12:30pm in Sondheim 110

### Course Materials
: There is no textbook for this course, but you will be required to puchase a varitey of materials including games, software, and API credits. If any of these are prohibitively expensive for your budget, please let the instructor know.

#### Games
<!-- : [Labyrinth The Adventure Game](https://www.amazon.com/Jim-Hensons-Labyrinth-Adv-Game/dp/1916011551/) - $35 on Amazon -->
: [Action Castle](http://www.memento-mori.com/pdf/parsely-preview-n-play-edition) - Free (you can optionally buy it in the rad [Parsley book in print](http://www.memento-mori.com/books/parsely-book) or [PDF](http://www.memento-mori.com/pdf/parsely-pdf)) - $20-30
: Optional: [Dungeon Master's Guide - Dungeons & Dragons 5th edition Core Rulebook](https://www.amazon.com/Dungeons-Dragons-Dungeon-Rulebook-Roleplaying/dp/0786965622/) by Wizards of the Coast - $31

#### Materials 
: [ChatGPT Plus subcription](http://chat.openai.com) - $20/month
<!--: [Midjourney subscription](https://www.midjourney.com/home) - $10/month -->


<!--
: $20-30 [Parsley](http://www.memento-mori.com/parsely-products/) by Jared A Sorensen
Books
: (Optional) [So You Want To Be A Game Master: Everything You Need to Start Your Tabletop Adventure for Dungeons and Dragons, Pathfinder, and Other Systems](https://www.amazon.com/gp/product/1645679152/ref=ox_sc_act_title_1?smid=ATVPDKIKX0DER&psc=1) - $25 on Amazon

: [$10](http://www.drivethrurpg.com/product/108028/Dungeon-World)-[$25](https://www.burningwheel.com/dungeon-world-1/) [Dungeon World](https://dungeon-world.com/) by Sage LaTorra and Adam Koebel

-->

### Grading

| Assignment | 491 (undergrad) | 691 (grad) |
|----------------|---------------------|----------------|
| Homework 1 | 5% | 5% |
| Homework 2 | 10% | 10% |
| Homework 3 | 10% | 10% |
| Homework 4 | 10% | 10% |
| Homework 5 | 10% | 10% |
| Homework 6 | 10% | 10% |
| Project | 30% | 30% |
| Knowledge Checks | 15% | 5% |
| Paper Presentations | - | 10% |


**Knowledge Checks**
: These checks are in place to see how well you all are understanding the material as the course goes. These might look like clicker questions (using Poll Everywhere), "minute" questions to get you to think about the topic of the day, or a small in-class assignment. These will not be graded for accuracy, just whether or not you did them.
If you cannot attend a lecture for any reason, you can make up the "minute" questions or assignments in your own time. They will be posted either on Blackboard or the course website (this website).
Your two lowest grade class knowledge checks (i.e., incomplete or missing submissions) will be dropped.

**Paper Presentations (Grad students only)**
: Over the course of the semester, each student must prepare one or more 10-15 minute presentations on a research paper relevant to the course. Since these presentation will be a substantial component of the learning experience in the class, slides must be prepared and emailed to us at least 72 hours in advance of the lecture they will be presented in (e.g., by 3PM on the Monday before the presenation date), so that we can provide feedback on them. Failure to send us the slides ahead of time will result in a grade penalty on the presentation. 

### Class Policies
#### Collaboration Policy
: Unless otherwise noted, you ARE allowed to work in pairs on the homework assignments, and teams of 3-5 for the final project.

#### Late Day Policy
: Each student has five free "late days".  Homeworks can be submitted at most two days late.  If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days only apply to the homeworks. They cannot be used on the last deadline for the final project, which must be finished by the final day of class.  Late days may not be used for paper presentations.**

#### Academic Integrity
: If you are struggling because of the material or having difficulties completing the assignments on time, please [reach out to Dr. Martin](mailto:laramar@umbc.edu) rather than copying another student or looking up answers online. We can come up with a solution to help you out before you feel like you need to resort to cheating.
: I care a lot about the students who take my classes, and that also means that I take cheating very seriously. Plagiarism or any sort of cheating is not tolerated in this class. All work submitted must be your own (or, if permitted, with partners---see [Collaoration Policy](#collaboration-policy). If you are allowed external sources on an assignment, please be sure to cite your source! This includes Large Language Models (LLMs): Please see [the next section](#generative-ai) for our policy specific to ChatGPT and other generative AI. Remember, reusing your own work from a different class is not permitted; this is self-plagiarism. If you are suspected of cheating, plagiarism, or other forms of academic dishonesty, your case will be brought to the attention of the Undergraduate Academic Conduct Committee or Graduate Council Grievance Committee and may result in an F in the course, depending on the Committee’s decision. **Your first offense will result in at least a 0 (zero) on the assignment.** If you would like more information on what constitutes as academic dishonesty, please consult [https://academicconduct.umbc.edu/](https://academicconduct.umbc.edu/).

#### LLMs/"Generative AI"
This course is centered around text generation, and we will be using GPT for a large portion of it. That said, any time that you use a large language model (LLM) for an assignment you must provide (1) the exact prompt that you used and (2) the original, unedited generation.

If you use GPT (or similar LLMs) for any other writing, you must still provide the prompt and the original generation, but you are also required to show where you edited the original generation.
This applies to prose, code, or any form of content creation. Not disclosing is an academic integrity violation. If you do disclose, your answer may receive anywhere from 0 to full credit, depending on the extent of substantive edits, achievement of learning objectives, and overall circumvention of those objectives.

Use of AI/automatic tools for grammatical assistance (such as spell-checkers or Grammarly) or small-scale predictive text (e.g., next word prediction, tab completion) is okay. Provided the use of these tools does not change the substance of your work, use of these tools may be, but is not required to be, disclosed.

------
## UMBC School Policies

### Accessibility and Disability Accommodations, Guidance and Resources
Accommodations for students with disabilities are provided for all students with a qualified disability under the Americans with Disabilities Act (ADA & ADAAA) and Section 504 of the Rehabilitation Act who request and are eligible for accommodations. The Office of Student Disability Services (SDS) is the UMBC department designated to coordinate accommodations that creates equal access for students when barriers to participation exist in University courses, programs, or activities.

If you have a documented disability and need to request academic accommodations in your courses, please refer to the SDS website at [sds.umbc.edu](http://sds.umbc.edu/) for registration information and office procedures.

SDS email: [disability@umbc.edu](mailto:disability@umbc.edu)

SDS phone: [410-455-2459](tel:410-455-2459)

If you will be using SDS approved accommodations in this class, please contact the instructor to discuss implementation of the accommodations. During remote instruction requirements due to COVID, communication and flexibility will be essential for success.

### Sexual Assault, Sexual Harassment, and Gender Based Violence and Discrimination
[UMBC Policy](https://ecr.umbc.edu/gender-discrimination-sexual-misconduct/) in addition to federal and state law (to include Title IX) prohibits discrimination and harassment on the basis of sex, sexual orientation, and gender identity in University programs and activities. Any student who is impacted by sexual harassment, sexual assault, domestic violence, dating violence, stalking, sexual exploitation, gender discrimination, pregnancy discrimination, gender-based harassment, or related retaliation should contact the University’s Title IX Coordinator to make a report and/or access support and resources. The Title IX Coordinator can be reached at [titleixcoordinator@umbc.edu](mailto:titleixcoordinator@umbc.edu) or [410-455-1717](tel:410-455-1717).

You can access support and resources even if you do not want to take any further action. You will not be forced to file a formal complaint or police report. Please be aware that the University may take action on its own if essential to protect the safety of the community.

If you are interested in making a report, please use the [Online Reporting/Referral Form](https://umbc-advocate.symplicity.com/titleix_report/index.php/pid419318?).  Please note that, if you report anonymously, the University’s ability to respond will be limited.

**Notice that Faculty and Teaching Assistants are Responsible Employees with Mandatory Reporting Obligations**

All faculty members and teaching assistants are considered Responsible Employees, per UMBC’s [Policy on Sexual Misconduct, Sexual Harassment, and Gender Discrimination](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/). Faculty and teaching assistants therefore required to report all known information regarding alleged conduct that may be a violation of the Policy to the Title IX Coordinator, even if a student discloses an experience that occurred before attending UMBC and/or an incident that only involves people not affiliated with UMBC.  Reports are required regardless of the amount of detail provided and even in instances where support has already been offered or received.

While faculty members want to encourage you to share information related to your life experiences through discussion and written work, students should understand that faculty are required to report past and present sexual harassment, sexual assault, domestic and dating violence, stalking, and gender discrimination that is shared with them to the Title IX Coordinator so that the University can inform students of their [rights, resources, and support](https://ecr.umbc.edu/rights-and-resources/).  While you are encouraged to do so, you are not obligated to respond to outreach conducted as a result of a report to the Title IX Coordinator.

If you need to speak with someone in confidence, who does not have an obligation to report to the Title IX Coordinator, UMBC has a number of [Confidential Resources](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/#confidential-resources) available to support you: 

[Retriever Integrated Health](https://health.umbc.edu/) (Main Campus): [410-455-2472](tel:410-455-2472); Monday – Friday 8:30 a.m. – 5 p.m.; For After-Hours Support, Call 988.

[Center for Counseling and Well-Being](https://shadygrove.umd.edu/student-affairs/counseling-well-being) (Shady Grove Campus): [301-738-6273](tel:301-738-6273); Monday-Thursday 10:00a.m. – 7:00 p.m. and Friday 10:00 a.m. – 2:00 p.m. (virtual) [Online Appointment Request Form](https://shadygrove.titaniumhwc.com/)

Pastoral Counseling via [The Gathering Space for Spiritual Well-Being](https://i3b.umbc.edu/spaces/the-gathering-space-for-spiritual-well-being/): [410-455-6795](410-455-6795); [i3b@umbc.edu](mailto:i3b@umbc.edu); Monday – Friday 8:00 a.m. – 10:00 p.m.

#### Other Resources

[Women’s Center](https://womenscenter.umbc.edu/) (open to students of all genders): [410-455-2714](tel:410-455-2714); [womenscenter@umbc.edu](mailto:womenscenter@umbc.edu); Monday – Thursday 9:30 a.m. – 5:00 p.m. and Friday 10:00 a.m. – 4 p.m.

[Shady Grove Student Resources](https://ecr.umbc.edu/shady-grove-title-ix-resources/), [Maryland Resources](https://ecr.umbc.edu/maryland-resources/), [National Resources](https://ecr.umbc.edu/national-resources/).

#### [Child Abuse and Neglect](https://ecr.umbc.edu/child-protection/)

Please note that Maryland law and [UMBC policy](https://education.umbc.edu/child-abuse-reporting-policy//) require that faculty report all disclosures or suspicions of child abuse or neglect to the Department of Social Services and/or the police even if the person who experienced the abuse or neglect is now over 18.

### [Pregnant and Parenting Students](https://www2.ed.gov/about/offices/list/ocr/docs/pregnancy.html)
UMBC’s [Policy on Sexual Misconduct, Sexual Harassment and Gender Discrimination](https://ecr.umbc.edu/policy-on-sexual-misconduct-sexual-harassment-and-gender-discrimination/) expressly prohibits all forms of discrimination and harassment on the basis of sex, including pregnancy. Resources for pregnant, parenting and breastfeeding students are available through the University’s [Office of Equity and Civil Rights](https://ecr.umbc.edu/students/).  Pregnant and parenting students are encouraged to contact the Title IX Coordinator to discuss plans and ensure ongoing access to their academic program with respect to a leave of absence – returning following leave, or any other accommodation that may be needed related to pregnancy, childbirth, adoption, breastfeeding, and/or the early months of parenting.

In addition, students who are pregnant and have an impairment related to their pregnancy that qualifies as disability under the ADA may be entitled to accommodations through the [Office of Student Disability Services](https://sds.umbc.edu/accommodations/registering-with-sds/).

### Religious Observances & Accommodations
UMBC [Policy](https://provost.umbc.edu/wp-content/uploads/sites/46/2022/08/Religious-Observance-Academic-Policy-2022_2023.pdf) provides that students should not be penalized because of observances of their religious beliefs, and that students shall be given an opportunity, whenever feasible, to make up within a reasonable time any academic assignment that is missed due to individual participation in religious observances. It is the responsibility of the student to inform the instructor of any intended absences or requested modifications for religious observances in advance, and as early as possible. For questions or guidance regarding religious observances and accommodations, please contact the Office of Equity and Civil Rights at [ecr@umbc.edu](mailto:ecr@umbc.edu).

### Hate, Bias, Discrimination and Harassment
UMBC values safety, cultural and ethnic diversity, social responsibility, lifelong learning, equity, and civic engagement.

Consistent with these principles, [UMBC Policy](https://ecr.umbc.edu/discrimination-and-bias/) prohibits discrimination and harassment in its educational programs and activities or with respect to employment terms and conditions based on race, creed, color, religion, sex, gender, pregnancy, ancestry, age, gender identity or expression, national origin, veterans status, marital status, sexual orientation, physical or mental disability, or genetic information.

Students (and faculty and staff) who experience discrimination, harassment, hate, or bias based upon a protected status or who have such matters reported to them should use the [online reporting/referral form](https://umbc-advocate.symplicity.com/titleix_report/index.php/pid954154?) to report discrimination, hate, or bias incidents. You may report incidents that happen to you anonymously. Please note that, if you report anonymously, the University’s ability to respond may be limited.
