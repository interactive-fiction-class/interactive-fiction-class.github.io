---
title: CIS 700 - Resources
layout: default
img: play-if-card.png
active_tab: resources 
---

# Resources

## Story Datasets
| Dataset  | Papers | Paper Code | Hugging Face Link | Leaderboard|
| ----------- | ----------- | ----------- | ----------- |--------------------|
[FanFiction Archive](https://archive.org/details/fanfictiondotnet_repack) - fanfiction.net| [Beyond Canonical Texts: A Computational Analysis of Fanfiction](https://www.aclweb.org/anthology/D16-1218.pdf) and [Harry Potter and the Action Prediction Challenge from Natural Language](https://www.aclweb.org/anthology/N19-1218.pdf)|http://github.com/smilli/fanfiction|||
|[Deep Dungeons and Dragons (DDD) Corpus](http://groups.inf.ed.ac.uk/cup/ddd/) - roleplayerguild.com |[Deep Dungeons and Dragons: Learning Character-Action Interactions from Role-Playing Game Transcripts](https://www.aclweb.org/anthology/N18-2111.pdf)||||
|[ROCStories](https://cs.rochester.edu/nlp/rocstories/) - 5-sentence crowdsourced stories for Story Cloze Test| [A Corpus and Cloze Evaluation for Deeper Understanding of Commonsense Stories](https://aclanthology.org/N16-1098) and [LSDSem 2017 Shared Task: The Story Cloze Test](http://cs.rochester.edu/~nasrinm/files/Papers/lsdsem17-shared-task.pdf)|||https://competitions.codalab.org/competitions/15333 https://paperswithcode.com/sota/question-answering-on-story-cloze-test|
|[CaTeRS](https://cs.rochester.edu/nlp/rocstories/CaTeRS/) - Causal and temporal relations using ROC Stories|[CaTeRS: Causal and Temporal Relation Scheme for Semantic Annotation of Event Structures](https://aclanthology.org/W16-1007/)
|[Scifi TV Plots](https://github.com/rajammanabrolu/StoryRealization) - science fiction shows on fandom.com| [Story Realization: Expanding Plot Events into Sentences](https://aaai.org/ojs/index.php/AAAI/article/view/6232) |https://github.com/rajammanabrolu/StoryRealization| https://huggingface.co/datasets/lara-martin/Scifi_TV_Shows |
|[WritingPrompts](http://www.reddit.com/r/WritingPrompts/) -  r/WritingPrompts| [Hierarchical Neural Story Generation](https://aclanthology.org/P18-1082) |https://github.com/pytorch/fairseq|https://huggingface.co/datasets/rewardsignal/reddit_writing_prompts||
|[Lit Bank](https://github.com/dbamman/litbank) - Project Gutenberg |[An Annotated Dataset of Literary Entities](http://people.ischool.berkeley.edu/~dbamman/pubs/pdf/naacl2019_literary_entities.pdf) and [Literary Event Detection](http://people.ischool.berkeley.edu/~dbamman/pubs/pdf/acl2019_literary_events.pdf)|https://github.com/dbamman/litbank||
|[STORIUM (Machine-in-the-Loop Story Generation)](https://storium.cs.umass.edu/) - storium.com (gamified storytelling) | [STORIUM: A Dataset and Evaluation Platform for Machine-in-the-Loop Story Generation](https://aclanthology.org/2020.emnlp-main.525/) | https://github.com/dojoteef/storium-gpt2 ||
|[ESTER](https://vnpeng.net/bibliography/han2021ester/) - tagged events from news articles from the TempEval3(TE3) workshop| [ESTER: A Machine Reading Comprehension Dataset for Event Semantic Relation Reasoning](https://arxiv.org/abs/2104.08350)| https://github.com/PlusLabNLP/ESTER ||https://eventqa.github.io/|
|[CMU Movie Summary Corpus](http://www.cs.cmu.edu/~ark/personas/) - Wikipedia movie summaries| [Learning Latent Personas of Film Characters](https://aclanthology.org/P13-1035.pdf) |||
|[The Children’s Book Test](https://research.fb.com/downloads/babi/) - kids' books from Project Gutenberg | [The Goldilocks Principle: Reading Children’s Books with Explicit Memory Representations](https://arxiv.org/abs/1511.02301) |https://github.com/facebookarchive/bAbI-tasks||
|[Cornell Movie Dialog](https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html) - movie scripts and metadata| [Chameleons in Imagined Conversations: A New Approach to Understanding Coordination of Linguistic Style in Dialogs](https://aclanthology.org/W11-0609/) |https://convokit.cornell.edu/documentation/movie.html|https://huggingface.co/datasets/cornell_movie_dialog|
|[ScriptWriter](https://github.com/DaoD/ScriptWriter) - from GraphMovie, which no longer exists (descriptions of movie plots)| [ScriptWriter: Narrative-Guided Script Generation](https://aclanthology.org/2020.acl-main.765/) |https://github.com/DaoD/ScriptWriter||
|[NarrativeQA](https://github.com/deepmind/narrativeqa) - movie scripts from various sources and Project Gutenberg books|[The NarrativeQA Reading Comprehension Challenge](https://aclanthology.org/Q18-1023/)|https://github.com/deepmind/narrativeqa|https://huggingface.co/datasets/narrativeqa|https://paperswithcode.com/sota/question-answering-on-narrativeqa|
|[MCTest](https://mattr1.github.io/mctest/) - 150-300 word stories written by crowdworkers |[MCTest: A Challenge Dataset for the Open-Domain Machine Comprehension of Text](https://aclanthology.org/D13-1020/) | |https://huggingface.co/datasets/sagnikrayc/mctest| https://paperswithcode.com/dataset/mctest|
|InSentive - authored stories from BookCorpus |[Inspiration through Observation: Demonstrating the Influence of Automatically Generated Text on Creative Writing](https://roemmele.github.io/publications/Inspiration_through_Observation__Demonstrating_the_Influence_of_Automatically_Generated_Text_on_Creative_Writing.pdf)|https://github.com/roemmele/InSentive
|[dScryb](https://dscryb.com/) - human-written scene descriptions ||||

## Mixed Visual + Textual Datasets
| Dataset  | Papers | Paper Code | Hugging Face Link 
| ----------- | ----------- | ----------- | ----------- |
|[BookCorpus](https://yknzhu.wixsite.com/mbweb) |[Aligning Books and Movies: Towards Story-Like Visual Explanations by Watching Movies and Reading Books](https://www.computer.org/csdl/proceedings-article/iccv/2015/8391a019/12OmNro0HYa) and [Skip-thought vectors](http://papers.neurips.cc/paper/5950-skip-thought-vectors.pdf)| https://github.com/ryankiros/skip-thoughts |https://huggingface.co/datasets/bookcorpus||
|[COIN: A Large-Scale Dataset for Comprehensive Instructional video analysis](https://coin-dataset.github.io)|[COIN: A Large-scale Dataset for Comprehensive Instructional Video Analysis](https://openaccess.thecvf.com/content_CVPR_2019/papers/Tang_COIN_A_Large-Scale_Dataset_for_Comprehensive_Instructional_Video_Analysis_CVPR_2019_paper.pdf)|https://github.com/coin-dataset|
|[WikiHow](https://www.wikihow.com/) |[WikiHow: A Large Scale Text Summarization Dataset](https://arxiv.org/abs/1810.09305)|https://github.com/mahnazkoupaee/WikiHow-Dataset|https://huggingface.co/datasets/wikihow|
|[VIST](http://visionandlanguage.net/VIST/dataset.html) |[Visual Storytelling](https://aclanthology.org/N16-1147/)||
|[MovieGraphs](http://moviegraphs.cs.toronto.edu/) |[MovieGraphs: Towards Understanding Human-Centric Situations from Videos](https://ieeexplore.ieee.org/document/8578993)|

## Cloze Tests
| Test  | Papers |Leaderboard|
| ----------- | ----------- | --------------------|
|Narrative Cloze Test|[Unsupervised Learning of Narrative Event Chains](https://aclanthology.org/P08-1090/)
|[Story Cloze Test](https://cs.rochester.edu/nlp/rocstories/)| [A Corpus and Cloze Evaluation for Deeper Understanding of Commonsense Stories](https://aclanthology.org/N16-1098) and [LSDSem 2017 Shared Task: The Story Cloze Test](http://cs.rochester.edu/~nasrinm/files/Papers/lsdsem17-shared-task.pdf)|https://competitions.codalab.org/competitions/15333 https://paperswithcode.com/sota/question-answering-on-story-cloze-test|
|[BookTest](https://ibm.ent.box.com/v/booktest-v1) - Cloze Test using Project Gutenberg|[Embracing Data Abundance](https://openreview.net/pdf?id=H1U4mhVFe)|
|[Who-did-What](https://tticnlp.github.io/who_did_what/) - Cloze Test using LDC English Gigaword newswire corpus |[Who did What: A Large-Scale Person-Centered Cloze Dataset](https://aclanthology.org/D16-1241/)|https://tticnlp.github.io/who_did_what/leaderBoard.html|

## Data Scrapers & Processors

* [Archive of Our Own Scraper](https://github.com/radiolarian/AO3Scraper)
* [Fanfiction Scraper](https://github.com/smilli/fanfiction)
* Process your own book data: [BookNLP](https://github.com/booknlp/booknlp)

## IF Environments

| Environment  | Papers | Paper Code |
| ----------- | ----------- | ----------- |
| [LIGHT](https://parl.ai/projects/light/) | [Learning to Speak and Act in a Fantasy Text Adventure Game](https://aclanthology.org/D19-1062.pdf)|https://github.com/facebookresearch/ParlAI|
| [Jericho](https://github.com/JerichoWorld/JerichoWorld)|[Modeling Worlds in Text](https://openreview.net/forum?id=Y1YtS9MZA75) and [Interactive Fiction Games: A Colossal Adventure](https://ojs.aaai.org/index.php/AAAI/article/view/6297)|https://github.com/JerichoWorld/JerichoWorld|
| [TextWorld](https://github.com/Microsoft/TextWorld) | [TextWorld: A Learning Environment for Text-based Games](https://www.microsoft.com/en-us/research/project/textworld/)|https://github.com/Microsoft/TextWorld|

## Planning Systems

| Planner/Code  | Papers |
| ----------- | ----------- |
| [Glaive](https://www.cs.uky.edu/~sgware/projects/glaive/) | [Glaive: a state-space narrative planner supporting intentionality and conflict](https://ojs.aaai.org/index.php/AIIDE/article/view/12712) |
| [StoryAssembler](https://github.com/LudoNarrative/StoryAssembler) | [StoryAssembler: An Engine for Generating Dynamic Choice-Driven Narratives](https://dl.acm.org/doi/10.1145/3337722.3337732)|
| [Belief and Intentional PDDL](https://github.com/qed-lab/belief-intention-compilation)| [Using Domain Compilation to Add Belief to Narrative Planners](https://ojs.aaai.org//index.php/AIIDE/article/view/7405)|
|[STRIPS Planner for Python](https://github.com/abdulapopoola/STRIPS-Planner)||

## Character Modeling

* [Versu](https://versu.com/)
* [Character Relations](https://github.com/dbamman/characterRelations)

## Knowledge Bases

| Knowledge Base | Papers | Hugging Face Link|
| ----------- | ----------- | ----------- |
| [VerbNet](https://uvi.colorado.edu/uvi_search)|[VerbNet: A Broad-Coverage, Comprehensive Verb Lexicon](http://verbs.colorado.edu/~kipper/Papers/dissertation.pdf)||
| [FrameNet](https://framenet.icsi.berkeley.edu/fndrupal/)|[FrameNet II: Extended Theory and Practice](https://framenet2.icsi.berkeley.edu/docs/r1.7/book.pdf)|
| [WordNet](https://wordnet.princeton.edu/)|[WordNet: An Electronic Lexical Database](https://mitpress.mit.edu/books/wordnet)|
| [ConceptNet](https://conceptnet.io/)|[ConceptNet 5.5: An Open Multilingual Graph of General Knowledge](https://arxiv.org/abs/1612.03975)|https://huggingface.co/datasets/conceptnet5
| [ATOMIC](https://homes.cs.washington.edu/~msap/atomic/)|[ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning](https://homes.cs.washington.edu/~msap/pdfs/sap2019atomic.pdf)|https://huggingface.co/datasets/atomic
| [GLUCOSE](https://github.com/ElementalCognition/glucose) |[GLUCOSE: GeneraLized and COntextualized Story Explanations](https://aclanthology.org/2020.emnlp-main.370/)| https://huggingface.co/datasets/glucose
| [Power and Agency in modern films](https://homes.cs.washington.edu/~msap/movie-bias/)|[Connotation Frames of Power and Agency in Modern Films](https://homes.cs.washington.edu/~msap/pdfs/sap2017connotation.pdf)
| [Eraser](https://www.eraserbenchmark.com/) - Movie Rationales|[ERASER: A Benchmark to Evaluate Rationalized NLP Models](https://aclanthology.org/2020.acl-main.408/)|https://huggingface.co/datasets/movie_rationales
| [ECIpedia](https://github.com/jgordon/ecipedia-usc)||
| [The NOC List](https://github.com/prosecconetwork/The-NOC-List)|[Round Up The Usual Suspects: Knowledge-Based Metaphor Generation](https://aclanthology.org/W16-1105/)|
| [NULEX](https://www.qrg.northwestern.edu/Resources/nulex.html) - combines WordNet, VerbNet, and Wiktionary|[NULEX: An Open-License Broad Coverage Lexicon](https://aclanthology.org/P11-2063/)
| [CausalBank](https://nlp.jhu.edu/causalbank/)|[Guided Generation of Cause and Effect](https://www.ijcai.org/proceedings/2020/0502.pdf)


## Other Code

| Task | Papers | 
| ----------- | ----------- | 
| [Plot-guided Coherence Evaluation](https://github.com/PlusLabNLP/Plot-guided-Coherence-Evaluation) | [Plot-guided Adversarial Example Construction for Evaluating Open-domain Story Generation](https://aclanthology.org/2021.naacl-main.343/)|
| [Story Gen BART](https://github.com/PlusLabNLP/story-gen-BART) | [Content Planning for Neural Story Generation with Aristotelian Rescoring](https://aclanthology.org/2020.emnlp-main.351/)|
| [EnGen: Text generation with entities as context](https://github.com/eaclark07/engen) | [Neural text generation in stories using entity representations as context](https://aclanthology.org/N18-1204.pdf)|
| [Choose Your Own Adventure Evaluation](https://github.com/eaclark07/cyoa)|[Choose Your Own Adventure: Paired Suggestions in Collaborative Writing for Evaluating Story Generation Models](https://aclanthology.org/2021.naacl-main.279/)|
| [Sentence Mover's Similarity](https://github.com/eaclark07/sms) |[Sentence Mover’s Similarity: Automatic Evaluation for Multi-Sentence Texts](https://aclanthology.org/P19-1264/)|
| [AI Dungeon 2](https://github.com/Latitude-Archives/AIDungeon)||
| [COMET](https://github.com/atcbosselut/comet-commonsense) - uses ATOMIC and ConceptNet | [COMET: Commonsense Transformers for Automatic Knowledge Graph Construction](https://aclanthology.org/P19-1470/)|
| [Plan-And-Write Automatic Storytelling](https://bitbucket.org/VioletPeng/language-model/src/master/) | [Plan-and-Write: Towards Better Automatic Storytelling ](https://ojs.aaai.org/index.php/AAAI/article/view/4726)|
| [ASTER (Automated Story-Telling using Event Representations)](https://github.com/lara-martin/ASTER) |[Event Representations for Automated Story Generation with Deep Neural Nets](https://dl.acm.org/doi/abs/10.5555/3504035.3504141)|

### Libraries & Toolkits
* [Hugging Face](https://huggingface.co/) - Hugging Face provides state-of-the-art general-purpose neural language model architectures like BERT, GPT-2, and others.
* [Hugging Face Transformer Library](https://github.com/huggingface/transformers)
* [AllenNLP](https://allennlp.org) - Deep learning for NLP with state of the art models
* [Spacy](https://spacy.io) - Industrial-Strength Natural Language Processing in Python
* [NLTK - Natural Language Toolkit](https://www.nltk.org/) - Basic NLP tools for Python & interfacing with some external models
* [Stanford NLP](https://nlp.stanford.edu/software/)

## Tutorials 

* [How To Make Custom AI-Generated Text With GPT-2](https://minimaxir.com/2019/09/howto-gpt2/) by [Max Woolf](https://minimaxir.com)
* [BERT End to End (Fine-tuning + Predicting) in 5 minutes](https://colab.research.google.com/github/tensorflow/tpu/blob/master/tools/colab/bert_finetuning_with_cloud_tpus.ipynb)
* [How to use Google Speech to Text API to transcribe long audio files](https://towardsdatascience.com/how-to-use-google-speech-to-text-api-to-transcribe-long-audio-files-1c886f4eb3e9)
* [Video Tutorial - Beginners Guide To Coding An Illustrated Text Adventure Game (with Adventuron Classroom)](https://adventuron.blogspot.com/2019/07/video-tutorial-beginners-guide-to.html) by Chris Ainsley

## Extras

### Noteable IF Games in Research
* [Save the Date](http://paperdino.com/save-the-date/) by [Chris Cornell (Montolli)](http://paperdino.com/)
* [The Icebound Concordance](https://www.ice-bound.com/) by [Aaron Reed](http://aaronareed.net/) and [Jacob Garbe](http://www.jacobgarbe.com/)
* [Prom Week](https://promweek.soe.ucsc.edu/)
* [Façade](https://www.playablstudios.com/facade)

### Inspiration

* [Actual Play Podcasts](https://www.polygon.com/podcasts/2018/9/26/17860176/best-dungeons-dragons-dd-podcasts-tabletop-gaming) - both of our favorite is The Adventure Zone
* [Giant list of Actual Play Podcasts](https://tabletopbellhop.com/actual-play-podcasts/)
* Play games with friends on [Roll 20](https://roll20.net/)
* [chooseyourstory.com](http://chooseyourstory.com)
* [AI Dungeon](https://play.aidungeon.io)
* Try some games on [Itch.io](https://itch.io/games/tag-interactive-fiction/tag-text-based) to figure out what you like and don't like in an IF game
* [Interactive Fiction Database](https://ifdb.org/)
* [Interactive Fiction Wiki](https://www.ifwiki.org/)

### Other Courses

* Nick Montfort's [Interactive Narrative](https://nickm.com/classes/interactive_narrative/2019_fall/) course at MIT

### Content Generation for TRPGs and IF

* [Print graph paper](http://print-graph-paper.com) - just blank graph paper!
* [Random Generators for Tabletop Games](https://donjon.bin.sh)
* [TesselationPlot for RPG Maps](https://community.wolfram.com/groups/-/m/t/1794056)
* [RPG Map Editor 2](https://deepnight.net/tools/rpg-map/)
* [RPGgen](https://www.rpggen.dev/) - a collection of generators

### Other Languages for Writing Interactive Fiction

* [Adventuron Classroom](https://adventuron.io/classroom/)
* [Tracery](http://tracery.io/) ([repo](https://github.com/galaxykate/tracery/tree/tracery2))
* [ink](https://www.inklestudios.com/ink/) ([repo](https://github.com/inkle/ink))
* [Twine](https://twinery.org/) ([repo](https://github.com/tweecode/twine))
* [Inform 7](http://inform7.com/)
* [ADRIFT](https://www.adrift.co/)
* [TADS](http://www.tads.org/)
* [Quest](http://textadventures.co.uk/quest/)
* [Storychoices](http://wiki.failbettergames.com/)
* [Varytale](http://www.varytale.com/home.php)
