---
layout: default
img: zork.jpg
caption: You are likely to be eaten by a Grue
title: Text Adventure Lecture Notes 
active_tab: lectures
readings:
-
   title: Interactive fiction
   authors: Wikipedia
   type: online
   id: wikipedia-interactive-fiction
   year: 2020
   url: https://en.wikipedia.org/wiki/Interactive_fiction
-
   title: Twisty Little Passages&colon; An Approach to Interactive Fiction
   authors: Nick Montfort
   type: book
   publisher: The MIT Press
   id: twisty-little-passages
   year: 2003
   url: https://www.amazon.com/Twisty-Little-Passages-Approach-Interactive-ebook/dp/B005363IMS/
---


# Text Adventure Lecture Notes

This course is going to focus on using techniques from artificial intelligence in order to create [Interactive fiction](https://en.wikipedia.org/wiki/Interactive_fiction). 
One kind of interactive fiction are [text adventure games](https://en.wikipedia.org/wiki/Adventure_game), which are computer game that pre-dated the advent of computer graphics.  The interface for text adventure games was text-only.  The players could input text command to navigate the environment, and manipulate objects in it. Game would describe what happens via text output.  Here is an example of the the game play in classic game Zork (lines that begin with a > are the player's input):

```
South of House
You are facing the south side of a white house.  There is no door here, and all the windows are barred.

>examine house
The house is a beautiful colonial house which is painted white.  It is clear that the owners must have been extremely wealthy.

>go east
Behind House
You are behind the white house.  In one corner of the house there is a small window which is slightly ajar.

>open window
With great effort, you open the window far enough to allow entry.

>climb through window
You can't see any such thing.

>enter house
Kitchen
You are in the kitchen of the white house.  A table seems to have been used recently for the preparation of food.  A passage leads to the west and a dark staircase can be seen leading upward.  To the east is a small window which is open.
On the table is an elongated brown sack, smelling of hot peppers.
A bottle is sitting on the table.
The glass bottle contains:
 A quantity of water

>open sack
You open the brown sack, revealing a clove of garlic and a lunch.

>eat lunch
(first taking the lunch)
Thank you very much.  It really hit the spot.
```

[Zork](https://en.wikipedia.org/wiki/Zork) was developed between 1977 and 1979, and it was first commercially sold in 1980 by Infocom.  It sold 378,000 copies by 1986. 



## Artifical Intelligence


Microsoft Research has a project called [Textworld](https://www.youtube.com/watch?v=WVIIigrPUJs), which uses text-based games for artifical intelligence research, because:

> Text-based games are great tools for AI research because to succeed at a text-based game an AI needs to understand language, perform common-sense reasoning, deal with a combinatorial action space and overcome common reinforcement learning problems like partial observability and rewards sparsity. These skills are ultimately key skills needed for artificial general intelligence.

<!--
Another potential innovative claim is that Game World are a great thing to study, since they have a defined semantics and are a closed-world system so it is easier to ground language into their semantics.  Here’s another quote from the Textworld video:

"In Textworld you can quickly and easily generate a large distribution of training games while controlling for various aspects of the game such as the quest complexity, the vocabulary, the action and state space, the reward density, and the amount of information provided to agents."
I love tasks 1 and 2!  

For collecting the data, you could potentially use crowdsourcing.  Facebook instrumented ParlAI to collect conversations on MTurk.  They used it in several papers including this one: [Learning to Speak and Act in a Fantasy Text Adventure Game](https://arxiv.org/abs/1903.03094).
-->


# Excerpts from Relevant Wikipedia Articles

Interactive fiction is software simulating environments in which players use text commands to control characters and influence the environment. Works of interactive fiction can be understood as literary narratives or as a form of computer game.  The most common types of interactive fiction computer games are [text adventures](https://en.wikipedia.org/wiki/Adventure_game), a type of adventure game where the entire interface can be "text-only".   The term interactive fiction can also be used to refer to digital versions of literary works that are not read in a linear fashion, where the reader is instead given choices at different points in the text; these decisions determine the flow and outcome of the story. The most famous example of this form of printed fiction is the [Choose Your Own Adventure book series](https://en.wikipedia.org/wiki/Choose_Your_Own_Adventure).

## Text adventures

Text adventures are one of the oldest types of computer games. The player uses text input to control the game, and the game state is relayed to the player via text output.   Zork I is one of the most famous text adventure games. It was first commercially sold in 1980 by Infocom, and it sold sold 378,000 copies by 1986. 


### The players 

Input is usually provided by the player in the form of simple sentences such as "get key" or "go east", which are interpreted by a text parser. Parsers may vary in sophistication; the first text adventure parsers could only handle two-word sentences in the form of verb-noun pairs. Later parsers, such as those built on ZIL (Zork Implementation Language), could understand complete sentences. Later parsers could handle increasing levels of complexity parsing sentences such as "open the red box with the green key then go north". This level of complexity is the standard for works of interactive fiction today.

Despite their lack of graphics, text adventures include a physical dimension where players move between rooms or locations. The intrictate connection between locations were often maze-like, and thus players would often create their own map of the game by drawing a graph of the locations on paper. 


### Writing style

Interactive fiction features two distinct modes of writing: the player input and the game output. Player input is expected to be in simple command form (in linguistics sentences in command form are called _imperative sentences_). A typical command could be:

> PULL Lever

The responses from the game are usually written from a [second-person point of view](https://en.wikipedia.org/wiki/Narration#Second-person), in present tense.  
This is because, unlike in most works of fiction, the main character is closely associated with the player, and the events are seen to be happening as the player plays.

A typical response might look something like this, the response to "look in tea chest" at the start of Curses:

"That was the first place you tried, hours and hours ago now, and there's nothing there but that boring old book. You pick it up anyway, bored as you are."[7]

Some IF works dispense with second-person narrative entirely, opting for a first-person perspective ('I') or even placing the player in the position of an observer, rather than a direct participant.

### History

#### 1960s and 70s


The software programs ELIZA (1964–1966) and SHRDLU (1968–1970) were examples of early interactive natural language understanding.  Both programs used natural language processing (NLP) to take input from their user and respond in a virtual and conversational manner. ELIZA simulated a psychotherapist that appeared to provide human-like responses to the user's input, while SHRDLU employed an artificial intelligence that could move virtual objects around an environment and respond to questions asked about the environment's shape. The development of effective natural language processing is an important part of interactive fiction development.

The first text adventure game was Colossal Cave Adventure, written around 1975 by Will Crowther, a programmer and an amateur caver.  He wrote a text based cave exploration game that featured a sort of guide/narrator who talked in full sentences and who understood simple two-word commands that came close to natural English.  Crowther's original version was an accurate simulation of part of a real cave called Colossal Cave, but ut also included fantasy elements (such as axe-wielding dwarves and a magic bridge). The popularity of Adventure led to the wide success of interactive fiction during the late 1970s, when home computers had no graphics capability. 

The largest company producing works of interactive fiction was Infocom which was formed in the late 1970s/early 1980s. Infocom created the Zork series and many other titles, among them Trinity, The Hitchhiker's Guide to the Galaxy and A Mind Forever Voyaging.

In order to make its games easy to port to many computer systems, Infocom developed the Z-machine, a custom virtual machine that could be implemented on a large number of platforms, and took standardized "story files" as input.   Infocom was responsible for developing the interactive style that would be emulated by many later interpreters. The Infocom parser was widely regarded as the best of its era. It accepted complex, complete sentence commands like "put the blue book on the writing desk" at a time when most of its competitors parsers were restricted to simple two-word verb-noun combinations such as "put book". The parser was actively upgraded with new features like undo and error correction, and later games would 'understand' multiple sentence input: 'pick up the gem and put it in my bag. take the newspaper clipping out of my bag then burn it with the book of matches'.

### 1980s 

Interactive fiction became a standard product for many software companies. By 1982 Softline wrote that "the demands of the market are weighted heavily toward hi-res graphics" in games like Sierra's The Wizard and the Princess and its imitators. Such graphic adventures became the dominant form of the genre on computers with graphics, like the Apple II.[17] By 1982 Adventure International began releasing versions of its games with graphics.[17] The company went bankrupt in 1985. Synapse Software and Acornsoft were also closed in 1985. Leaving Infocom as the leading company producing text-only adventure games on the Apple II with sophisticated parsers and writing, and still advertising its lack of graphics as a virtue.[17] The company was bought by Activision in 1986 after the failure of Cornerstone, Infocom's database software program, and stopped producing text adventures a few years later. Soon after Telaium/Trillium also closed.

By the mid-1980s, the video game consoles were much higher performance than the computer systems that text adventure games were originally developed on.  Video game consoles allowed for the addition of graphics and sound to games, and video games eclipsed the popularity of text adventure games.


### Modern era

After the decline of the commercial interactive fiction market in the 1990s, an online community eventually formed around the medium. In 1987, the Usenet newsgroup rec.arts.int-fiction was created, and was soon followed by rec.games.int-fiction. By custom, the topic of rec.arts.int-fiction is interactive fiction authorship and programming, while rec.games.int-fiction encompasses topics related to playing interactive fiction games, such as hint requests and game reviews. As of late 2011, discussions between writers have mostly moved from rec.arts.int-fiction to the Interactive Fiction Community Forum.

One of the most important early developments was the reverse-engineering of Infocom's Z-Code format and Z-Machine virtual machine in 1987 by a group of enthusiasts called the InfoTaskForce and the subsequent development of an interpreter for Z-Code story files. As a result, it became possible to play Infocom's work on modern computers.

For years, amateurs with the IF community produced interactive fiction works of relatively limited scope using the Adventure Game Toolkit and similar tools.

The breakthrough that allowed the interactive fiction community to truly prosper, however, was the creation and distribution of two sophisticated development systems. In 1987, Michael J. Roberts released TADS, a programming language designed to produce works of interactive fiction. In 1993, Graham Nelson released Inform, a programming language and set of libraries which compiled to a Z-Code story file. Each of these systems allowed anyone with sufficient time and dedication to create a game, and caused a growth boom in the online interactive fiction community.

Despite the lack of commercial support, the availability of high quality tools allowed enthusiasts of the genre to develop new high quality games. Competitions such as the annual Interactive Fiction Competition for short works, the Spring Thing for longer works, and the XYZZY Awards, further helped to improve the quality and complexity of the games. Modern games go much further than the original "Adventure" style, improving upon Infocom games, which relied extensively on puzzle solving, and to a lesser extent on communication with non-player characters, to include experimentation with writing and story-telling techniques.

While the majority of modern interactive fiction that is developed is distributed for free, there are some commercial endeavors. In 1998, Michael Berlyn, a former Implementor at Infocom, started a new game company, Cascade Mountain Publishing, whose goals were to publish interactive fiction. Despite the Interactive Fiction community providing social and financial backing Cascade Mountain Publishing went out of business in 2000.

Other commercial endeavours include Peter Nepstad's 1893: A World's Fair Mystery, several games by Howard Sherman published as Malinche Entertainment, The General Coffee Company's Future Boy!, Cypher, a graphically enhanced cyberpunk game and various titles by Textfyre.[23] Emily Short was commissioned to develop the game City of Secrets but the project fell through and she ended up releasing it herself.[24]

[icon]  
This section needs expansion. You can help by adding to it. (May 2019)



# Notes and highlights for "Twisty Little Passages: An Approach to Interactive Fiction" by Nick Montfort

Nick Montfort is a professor of digital media at Massachusetts Institute of Technology



Text adventure games were a significant part of early computing. Text adventure games were the first best-sellers on PCs during the early 1980s.  

Interactive fiction is the broader term for the type of computer program exemplified by the text adventure games.  Works of interactive fiction are unique programs, best understood in terms of their two essential components:
1. __The parser__ is the component that analyzes natural language input in an interactive fiction work 
2. __The world model__ The setting of an interactive fiction is a simulated world, which in practice is represented computationally in some sort of data structure or collection of objects.

It is this simulated world that distinguishes a work of interactive fiction from a conversational character or from an expert system that employs natural language understanding.

The world model is typically implemented in the interactive fiction program as some type of graph or tree with associated procedures.

It represents the physical environment of the interactive fiction and the things in that environment, including characters, any physical objects in the setting that can be manipulated or further examined in any way, and the player character.

It also represents, and simulates, the physical laws of that "setting".

The parser is that part of the program that accepts natural language input from the interactor and analyzes it.

("Parser" is used as a term for all components of the program that handle natural language input, including some components that are distinguished from parsers in natural language processing.)

In the case of Adventure's "two-word" parser, which only accepts input of the form "verb" or "verb noun," determining the grammatical structure of the input is trivial.

More complex sentences are accepted by other interactive fiction works.

Such input can be compared to recognized structures by the parser, considering those objects that might possibly be referred to, and the likeliest match can then be accepted. Since the input text only needs to be interpreted in relation to the simulated world and the range of actions possible within that world, this analysis is tractable. 

Outtside interactive fiction, even "go west" might mean any of several things (it could be, e.g., a suggestion that a young person explore new options, a cheer for an all-star team, or a euphemism for death), but in the specific domain of interactive fiction such input can be understood reliably and unambiguously.

Z-machine machine interactive fiction

In an interactive fiction work, the interactor directs a character (the "player character") in the interactive fiction world to enact an understanding of that world.

The interactor's useful writing generally consists of contributions tions such as go north, jump off the or eat a peach. But such texts are actually ally understood, within the specific domain of the interactive fiction world, by the work's parser. They are then translated, if possible, into actions.

Not all interactive fiction works, and not even all classic works in the form, are text adventures. The third work from Infocom, Marc Blank's Deadline, is not a text adventure but a detective mystery,

Galatea by Emily Short (a conversation-based work set in a single room of a museum).

Finally, since an IF work is a computer program with a world model and parser, it is important to consider its nature as software. A particular work may have been developed using an object-oriented methodology or using a functional programming language. Works

Literary riddles and this type of interactive fiction are related in four important

ways: Both have a systematic world, are something to be solved, present challenge and appropriate and join the literary and the puzzling.

the world of particular riddles: "The riddle can reveal in a brief flash an excluded cosmos, a non-world or topsy-turvy world lurking just beneath or within our properly ordered and familiar one"

This concept of the world also describes the relationship between the riddler (who creates this world) and the riddlee (who must explore it to figure out how it works):

Riddlers, like poets, imitate God by creating their own cosmos; they re-create through words, making familiar objects into something completely new, re-arranging the parts of pieces of things to produce duce creatures with strange combinations of arms, legs, eyes and mouths. In this transformed world, a distorted mirror of the real world, the riddler is in control, but the reader has the ability to break the code and solve the mystery. (Wehlau 1997, 99-100)

the concept of the world as it relates to the riddle is applicable to interactive fiction

since the systematic but unusual nature of the riddle's world is presented for explicit understanding and solution by the riddlee.

Without understanding the workings of the riddle's world, however, the solution cannot be reached and the experience of the riddle remains incomplete.

In most interactive fiction, puzzles (sorts of challenges or obstacles) are part of the world the player character moves through. In order to complete the IF work, the interactor must figure out how to meet these challenges.

The solutions

may be arrived at through the player character's senses or by having ing the player character manipulate things in the surroundings and then observe the results to determine the workings of the world.

most interactive fiction, tion, is generally held by players to not have replay value

much as one cannot simply "replay" a riddle to which one knows the answer

Once one learns to play a board game, on the other hand, the knowledge edge gained from one game hardly ruins the experience of the next one.

May Swenson. Sold as a children's book, Poems to Solve

an excellent riddle should be "not merely obscure, but at the same time stimulating to the curiosity."

a work of interactive fiction should motivate the interactor to continue to figure ure out its world just as the riddle should compel further thought and further ther work toward a solution, which is consistent with Adam Cadre's (2002a) advice to authors: "The player should always have a pretty compelling reason to type something other than QUIT."

the nature of interactive fiction as computer program, simulated world, generator of narrative, and game means that it has many other ancestors. The idea that devices could generate texts using procedures was realized many centuries earlier.

literary machines, to describe them.

forebear is the fantasy role-playing playing game Dungeons and Dragons, a framework for a theatrical interaction, tion, for the exploration of simulated spaces, and for puzzle solving.

Within computing, three earlier types of systems were particularly influential

in the development of interactive fiction: computer games, early conversational systems such as ELIZA/DOCTOR, and more sophisticated cated artificial intelligence systems, exemplified by the natural language processing program SHRDLU.

The I Ching is a formal system for generating different literary texts, for instance.

It incorporates rates chance and provides

explicit procedures for how to assemble fragments into a final text;

The literary machine in Western culture-as a physical machine, as well as a procedural way of generating texts-seems to have been devised in 1274 C.E. by the Catholic alchemist, mystic, and philosopher Ramon Llull

"In 1726 Johnathan Swift published a description of a wonderful machine, made of equal

parts of irony, sarcasm, and mockery, that would automatically write books on all the arts and sciences"

Tristan Tzara the man from nowhere proposed to create a poem on the spot by pulling words out of a hat. A riot ensued wrecked the theatre" (Burroughs 2003, 90). Romanian-born Tzara, who was a founder of Dada

is credited with being the originator of the

"cut-up" technique of random recombination of text.

"Everything one looks at is false," Tzara wrote in the "Dada Manifesto," the first of seven that he wrote. "I do not consider the relative result more important than the choice between cake and cherries after dinner"

Brion Gysin (1982) followed in that anti-tradition three decades

later, without at first realizing it:

While cutting a mount for a drawing in room 25, I sliced through a pile of newspapers with my Stanley blade and thought of what I had said to Burroughs some six months earlier about the necessity for turning painters' techniques directly onto writing. I picked up the raw words and began to piece together texts. (51)

Oulipo

The group was dedicated not to the creation of literature, but to the creation of methods or ways of creating literature-hence

The literary machine, a form of potential literature, was certainly a proper object of Oulipian study.

The group's formulations included algorithms to

be applied to an existing text (e.g.,Jean Lescure's N + 7 rule for replacing each noun with the seventh enth noun after it in a dictionary

and constraints on the authorship of a text (e.g., the text must be a palindrome; letters and numbers must read the same forward and backward).

"rats who construct the labyrinth from which they propose to escape"

One physical device for generating texts was Queneau's 1961 Cent mille milliard de poemes (100, 000, 000, 000, 000 Poems), which took the form of a book with ten sonnets (each of the usual fourteen lines) bound one in front of the other and with each line cut so that it could be "turned," like a page, separately. Any one of ten lines could thus be selected for each position.

Hence there are 10" possible ble poems in the book, which would take (by Queneau's calculation) more than 190 million years to read.

Queneau also devised the first Choose Your Own Adventure type of story, his 1967 "Un conte a votre facon"

translated as "A story as you like it" and "Yours for the telling").This

short work has twenty-one possible sible text segments; the reader is asked to make a choice after the first one is read, and after each subsequent one, up to one of the possible endings. Warren Motte explains that it was "inspired by the presentation of the instructions given to computers, and by programmed teaching" (1997, 156). The juvenile fiction series named Choose Your Own Adventure,

of similar inspiration, began in 1979 with Edward Packard's The Cave fTime-too

"Louis Milic, an English professor at Cleveland State University, may have created the first computer poetry. In 1963, Milic programmed a computer to generate ate absurd English sentences"

This effort had been anticipated by an attempt in England to generate (amusing and nonsensical) physics essays in the 1950s (141).

some of what followed included attempts at machine generation eration of stories (Meehan 1980), a thread of computational and literary endeavor that differs from the creation of interactive systems.

When computer programmers and a few poets first produced machine poems based on much the same principle as that of Tristan Tzara ... they did not see themselves as the odious speculators in Swift's Academy of

Lagado, nor as poets in the Dada tradition. Mostly, they were light-hearted experimenters, trying to discover the word-manipulation possibilities of a new machine. (137)

DUNGEONS AND DRAGON S

D&D is an open-ended game in which the players assume the roles of characters in a story and can have those characters attempt any action whatsoever. The game is controlled by a gamesmaster, who uses tables, dice, and personal judgment to decide on the effect of a character's

efforts.

This "gamesmaster" is called the dungeon master. The players say what their characters, the "player

characters," do within the "world" of the campaign. Dice are rolled to assign ability points to player characters initially, and dice are employed to help determine the outcome of combat and other encounters. ters. Over the course of many adventures, the members of a party advance in level and become more powerful-and the dungeon master devises new challenges for them.

Dice,

are frequently used in a typical game. The twenty-sided die and other dice of unusual shape have become iconic. Dice are used to introduce unpredictability; based on the roll of a die, events may transpire that were not anticipated, foiling even the dungeon master's plans.

Beginning around 1950 computer war games were also developed in the United States, serving, as one early writer on computer games explained, "to simulate activity ranging from ... tactical action to a large fall-scale war." One was the 1955 HUTSPIEL, which ran on an analog computer and was for two players, Red and Blue, representing the USSR and NATO; this may have been the first two-player computer game.

1972, by Mike Mayfield. That was also the year Gregory Yob wrote Hunt the Wumpus (Nelson 2001b, 344), notable for having a world that was not a simple grid but a dodecahedron. This feature of Hunt the Wumpus inspired the irregular worlds of interactive fiction; different rooms, from the very beginning, could be interconnected

by the designer in any way.

The idea of computer conversation was developed along with the general-purpose purpose digital computer; Turing (1950) presented it quite clearly in his influential paper "Computing Machinery and Intelligence," in which he established the well-known, if sometimes misapplied," Turing Test." He gave the example of a parlor game in which a person of one gender tries to imitate tate a person of the other, and then suggested a similar game in which a computer would imitate a human in conversation. The question "Can machines think?" could then be replaced by one that was easier to answer: "Are there

imaginable digital computers which would do well in the imitation tation game?" (Turing 1950, 54-55). In formulating this test, Turing highlighted lighted the importance of conversational ability to our perception of intelligence, at a time when computers almost exclusively processed numbers bers rather than language.

One of many important early conversational programs was Baseball, which could answer questions like "Who did the Red Sox lose to on July 5?"

"How many games did theYankees play in July?" by searching ing through a store of this information, represented in English (Green et al. 1963, 211). A more sophisticated system was SIR (Semantic Information Retrieval), which was "capable of `understanding' statements dealing with set relations, part-whole relations, ownership, and certain special relations" and which maintained a dynamic model of its knowledge in a special format, using word associations (Raphael 1968, 33-44). While SIR worked well, Terry Winograd (1972) noted that "the types of complex information it could use were highly limited, and could not be easily

expanded"

ELIZA is a language analysis program that can run many different ferent scripts and have different sorts of conversations; the most famous script by far was called DOCTOR, which Weizenbaum (1976) explained was "designed to permit it to play (I should really say parody) the role of a Rogerian psychotherapist engaged in an initial interview with a patient"

The system, running this script, became known as the first computer

conversationalist, the first chatterbot. To simplify ELIZA's procedure-but not to simplify very much-the program would first search for keywords in input. If some were found, the program would transform the input according ing to a rule and print out the transformed sentence. If none were found, it would provide a default (usually noncommittal) output. Here is a bit of a conversation with ELIZA/DOCTOR, with the computer's reply in all capital letters:

Men

Although ELIZA was later used to do more sophisticated types of natural language understanding (Weizenbaum 1967; Winograd 1972, 38), Weizenbaum (1976) made it clear that it in no way offered a general solution tion to the problem of natural language understanding.

Nevertheless, users were quite affected by it. Weizenbaum wrote that he "was startled to see how quickly and how very deeply people conversing with DOCTOR became emotionally involved with the computer" (6). Janet Murray (1997) described him as being "so disconcerted by his achievement that he wrote a book warning of the dangers of attributing human thought to machines" (71).

Some psychiatrists thought ELIZA/DOCTOR should be used in therapy; apy; people took contradictory positions on big questions in artificial intelligence gence based on ELIZA/DOCTOR; and the program inspired its own branch of computer literature based on conversation with fictional characters ters U. Murray 1997, 214-247;

Terry Winograd's SHRDLU, which he programmed in LISP at the MIT Artificial Intelligence Laboratory during ing 1968-1970

This program (named after the second row of keys on a Linotype machine; see Winograd 1999)) carried on a dialog with the user via teletype, also displaying an image of a tabletop with blocks on it. It could respond to natural language commands in real time,

It would move the simulated blocks around if asked to; it could also answer questions about them.

SHRDLU used its knowledge of the simulated world to help it parse input. It represented its knowledge as procedures.

SHRDLU had eleven different ferent components. There was a module for generating replies to the user, for instance, and one for simulating the blocks world (Winograd 1972). Here is a short excerpt from a much longer SHRDLU sample transcript:

SHRDLU was able to understand almost any input just about anything that a human could understand-as long as it pertained to the blocks world.

Here is one description of a location in Adventure:

YOU ARE AT A COMPLEX JUNCTION. A LOW HANDS AND KNEES PASSAGE FROM

THE NORTH JOINS A HIGHER CRAWL FROM THE EAST TO MAKE A WALKING PASSAGE GOING WEST. THERE IS ALSO A LARGE ROOM ABOVE. THE AIR IS DAMP HERE.

Crowther, departing from the realistic simulation of caving, placed five treasures sures within as an incentive to explore the cave.The interactor also has to figure ure out how to get past a snake to have the player character move deeper into the cave. The player character is harassed at times by attacking dwarves and by a pirate who pilfers treasure.

There was a single maze in this first version, one that was essentially impossible to get through without making a map. The

Some of these were the aspects that made Adventure a "computer version" of Dungeons and Dragons (Crowther 1994, 1). It imitated that role-playing game not by having dice-driven combat bat based on ability and experience points, or by allowing the interactor to take the role of a particular fantasy character, but by providing opportunities for creative problem solving and by providing a challenge

I've certainly never claimed Adventure used any sort of Al (such as understanding natural language). To the contrary, I usually

take care to emphasise that Adventure's language parser was extremely primitive tive even for the state of the art at the time.

Adventure, with its primitive but effective way of understanding language, that endures and that became widespread. It also became the archetype of the text adventure and of interactive active fiction.

The two mazes provide one of the most popular expressions to originate nate with Adventure.

(The magic word "XYZZY," with its frequent mention in computing culture

The pirate's maze offers rooms that are all uniformly described as "a maze of twisty little passages, all alike."

To figure out which room is which, the player character must drop objects to mark the different rooms. The rooms, once all alike, can then be differentiated based on their contents and mapping ping of the usual sort is possible.

a work

of interactive fiction can itself be seen as a maze of twisty little textual passages-some alike, some different; ent; some produced by the computer, some typed by the interactor-that is to be traversed.

Adventure may not have been much of an artificial intelligence system, but it was, as Crowther (1994) described it, "a thing that gave you the illusion sion anyway that you'd typed in English commands and it did what you said" (2). Understanding the interactor

and doing what was specified within a simulated ulated world made the program SHRDLU-like;

the part that was an illusion of understanding-and was convincing-was following the tradition of ELIZA/DOCTOR.

These two programs were its most direct predecessors on the computer (McGath 1984, 11-14), though they did not directly give birth to interactive fiction.While Adventure used natural language (or at least a subset of English, as far as input was concered) and was intended for people who were not programmers,

across the surface of his desk, like relics from a party, lay dozens of roughly drawn maps. They consisted of circles, inside of which were scrawled names such as Dirty Passage, Hall of Mists, Hall of the Mountain King ... Webs of lines connected the circles, and each line was labeled, some with points of the compass, some with the words up and down. Here and there on the maps were notations-"water here," "oil here," and "damn that pirate!"

Making such maps was an essential part of solving Adventure and would remain essential to interacting with most other

works of interactive fiction.

For those who had access to mainframe computer time, writing one's own Adventure-like program seems to have been almost as popular an activity as was playing Adventure. Thus, Adventure became the model for computing gaming overall; Nelson (2001b) writes that "for the five years to 1982 almost every game created was another `Advent"'

Zork became the second widely known interactive fiction work.

The potential narratives of a successful traversal of Zork involve the adventurer turer wandering through an outdoor area, a house, and then a vast complex called the Great Underground Empire.To succeed the interactor must direct the adventurer to collect treasures, almost all of which are

located underground. ground. A handful of living opponents thwart the adventurer: the troll, who stays put in a single room and serves as an obstacle; the vampire bat, who can carry off the adventurer; the cyclops, who can dine on the adventurer; and the thief, who wanders around the underground areas stealing items the adventurer either is holding or has already seen. To get through the mazes, detailed mapmaking (or else extraordinary luck, or cheating) is required. Riddle-like challenges require the interactor to understand the nature of a disguised object in order to use it properly; in some cases machinery must be manipulated in order to determine its purpose.

Some puzzles, such as the Bank of Zork and the Royal Puzzle, are elaborate and extremely hard.

A few require that the interactor "guess the verb" and perform an action that would not be obvious from the commands available

in Adventure. If a magic word from Adventure is typed in Zork, a hollow voice says "Cretin."

The structural innovations in Zork's world also reflect a technological subculture. To prevail the adventurer must use vehicles, riding in a balloon and a boat. This player character also must command a robot in order to get through one section of the work.

The puzzles that offered riddle-like systems, called "problems" by the Implementors, often involve recognizing various technological artifacts, real and imagined, for what they are. In many cases, once the technology is recognized, ognized, the way in which objects are

supposed to be used becomes obvious.

A clear example is provided in the coal mine section of Zork's IF world. Here, the player character finds a machine that might, in another place, be used for doing laundry; a tiny slot is noticable in the top of it. What this machine does, and how to turn it on, is unclear. The solution is to put some coal found nearby into the machine, and then turn the machine on using the screwdriver. This results in the coal being compressed with great force. (The switch is described as having the right dimensions to be turned with a screwdriver of the appropriate type-of course, a flathead screwdriver. One of these can be found near FCD #3.) To figure out how to turn on the machine, one need only recognize which ordinary tool is needed, based on a literal description. To figure out

what the machine does, the interactor can act as scientist and put anything inside, then observe the results.

Understanding that useful machinery is found in this IF world, and using the process of experimentation and observation in order to learn what this machinery does, allows the player character to prevail

The diamond-making machine is not a profound riddle, but it was a step toward systematic IF worlds of greater power.

Zork did sport several advances that were used to good effect. These were in both essential components: the parser, which translates player-typed text into actions, and the world model, which simulates a narrative and puzzle-filled world to the degree required for an enjoyable interaction. The parser, "fairly stupid" as it might be, was a substantial upgrade from that of Adventure, which only accepts commands of one or two

words.

When there was only one appropriate object for a requested action, the parser would assume the interactor wished to use that object; otherwise, it would ask a question to disambiguate the command

1979).This worked particularly well in the case of actions like digging, which required tools. When a command was issued to dig with an inappropriate tool (e.g., diq in the sand with the screwdriver), the parser would generate a reply of the form "Digging with the screwdriver is slow and tedious." Since "the hands" were designated as tools, the parser, upon receiving the simple command mand diq, would assume-in the absence of any other tool-that "the hands" were to be used. It would then generate a response that-although unanticipated-was particularly apt and pleasing to the Implementors: "Digging with the hands is slow and tedious"

The parser folded prepositions into the different supported actions, so that "look at" and "look under" were considered as if they were separate verbs and were translated lated into different actions

Direct and indirect objects were recognized, and some verbs were allowed to take multiple tiple direct objects. The world model was enhanced to implement actors, who could perform form actions in much the sane way that the adventurer could, and could also be commanded by the interactor.

The robot, who lacked many of the adventurer's abilities but who could be commanded to solve a puzzle, was the first actor implemented. Although not the most charming character in interactive fiction

golem of Jewish folklore.

Frankenstein's monster.)

After the player character ter had asked the robot to read something, for instance, it would reply "My vision is not sufficiently acute to do that."

If commanded to eat, it somehow speaks the reply "I am sorry but that is difficult for a being with no mouth."

This robot, although an uninteresting conversational partner, did first allow the player character to direct another entity to accomplish tasks on his or her behalf.

This opened up new

possibilities for puzzles, and also brought on interesting narrative implications, to be explored later in works like Planetfall.

Vehicles were another new part of the world. They were implemented as if they were mobile rooms, contained in the top-level rooms of the dungeon geon (Lebling, Blank, and Anderson 1979).

The boat and the balloon were the vehicles placed in Zork.

Containment: Objects may have contents.

Weight: Objects have weight.A

Position: An object may be in, on, or under another object. (Lebling, Blank, and Anderson 1979)

Had interactive fiction only accepted two-word inputs instead of being pushed by the Zork parser advances toward accepting text that is more like normal English, there is little chance that the appeal of interactive fiction would have lasted beyond the era of command-line home computing.

Pointing and clicking would simply be

good enough when compared to a verb-noun command. Instead, Zork took the first step toward a more symmetrical metrical interaction between interactor and IF work, an exchange more like English conversation-one

The thief, who appears randomly to steal treasures the adventurer is holding, is certainly the most memorable character in Zork. This is attributed variously ously to the better writing associated with the thief or to his nature as an IF daemon or bot

In fact the thief is important to the development opment of interactive fiction because he functions as a true villain, not simply ply an obstacle or opponent.

"Zork was ... the first adventure whose non-player characters had personality.

The thief was a gentleman gone wrong, with good manners, a cynical sense of humour and the willingness to slit your throat in a moment." That the thief has a true personality may be an overstatement.

Here is a selection of many brief descriptive outputs regarding the thief from Zork:

Someone carrying a large bag is casually leaning against one of the walls here. He does not speak, but it is clear from his aspect that the bag will be taken only over his dead body. Your opponent, determining discretion to be the better part of valor, decides to terminate this little contretemps. With a rueful nod of his head, he steps backward into the gloom and disappears.

A `lean and hungry' gentleman just wandered through. Finding nothing ing of value, he left disgruntled. A seedy-looking individual with a large bag just wandered through the room. On the way, he quietly abstracted all valuables from the room and from your possession, mumbling something about, "Do unto others before ..." The other occupant just left carrying his large bag.You may not have noticed that he robbed you blind first. The thief, a man of good breeding, refrains from attacking a helpless opponent. The thief, forgetting his essentially genteel upbringing cuts your throat. The thief, who is essentially a pragmatist, dispatches you as a threat

his livelihood.

Writing about Adventure, Mary Ann Buckles (1985) noted that "[Vladimir] Propp believed villainy to be the most important function in the folktales he examined ... In my view, the lack of true villainy constitutes one of the main structural and ideational differences between folktales and Adventure"

creating the MUD, or Multiple User Dungeon, discussed in chapter 8.

The thirty-five canonical interactive fiction works developed at and published by Infocoin

Arthur: The Quest For Excalibur by Bob Bates (1989) Young Arthur must find the pilfered sword-in-stone.

Bureaucracy by Douglas Adams (1987) Absurd red tape and procedural challenges are joined with Adams's wit.

Hitchhiker's Guide To The Galaxy by Douglas Adams and Steve Meretzky (1984) Arthur Dent explores space in his bathrobe.A clever reworking of Adams's book.

Plundered Hearts by Amy Briggs (1987) A romance-novel adventure with pirates, swords, and a female player character.

Language understanding was limited, too, but the terse descriptions and two-word parser allowed this limited sort of interactive fiction to fit into 16k of memory;

obedient `puppet.'

Adams (2002) described his software development process and how feedback from testers was important to it: I'd set my theme, I'd set my locations, and I'd start putting items

in and putting in puzzles. I'd get the game about two thirds done and then I would stop. The next one third of the game literally came from the people I gave to play the game. I'd watch how they played the game, I'd watch what they tried to do with the items that I never thought they might try to do.

In order to deploy their games across different platforms, Berez and Blank specified and programmed a virtual machine called the Z-machine. This software ware computer could be implemented on many different platforms, including

The Z-machine served as the interpreter for Infocom story files. To create the story files themselves-the code that the Z-machine ran-a compiler piler was programmed by Blank to convert high-level, more English-like instructions into executable form.

high-level language that was used was an Infocom original, based on the Lisp-like language MDL, which had been used to write the mainframe Zork. The new language was called ZIL, Zork Implementation Language. Here is the ZIL for the living room in Zork I: <ROOM LIVING-ROOM (LOC

This same concept is what enables Java programs to work across different platforms by running in Java virtual machines.

Interactive fiction had, before 1983, generally presupposed a single heroic character whom the interactor would control.

pipes. This can be called the `charming' or `peter" statue' `sculpture"pan"boy"pipe' or `pipes'. Objects often have more than 10 nouns attached."The original Zork I had a 600-word vocabulary. Trinity could understand stand 2,120 different words. The clarity of Trinity was not the only possibility for advances in interactive fiction. Complicating communication could also be effective, as another Infocom work released in the same year revealed.

Z

The interactor tor can type English input such as go to the barn rather than e or east. This more topological, landmark-based way of navigating

early Adventure did not even recognize a simple, full English sentence such as go to the barn.

Because of the improved movement scheme, mapmaking is not necessary,


## Post from the IF Archive

When I was looking through the [Interactive Fiction Archive](https://ifarchive.info/indexes/if-archive.html), I found this post in the usenet group rec.arts.int-fiction from 1992.  It discusses the idea of a program that could automatically generate an adventure, which is pretty much what we're aiming to do in this course.  A response to the post says it won't be possible for another 20-50 years, which places us in the right predicted timeline.  

```
Path: gmd.de!jvnc.net!rutgers!ub!acsu.buffalo.edu!goetz
From: goetz@acsu.buffalo.edu (Phil Goetz)
Newsgroups: rec.arts.int-fiction
Subject: Re: Adventure generators (skippable)
Message-ID: <Bwv8yu.ACp@acsu.buffalo.edu>
Date: 29 Oct 92 04:40:05 GMT
References: <appelo.720194795@dutiag> <BwsqpC.Bpw@mentor.cc.purdue.edu>
Sender: nntp@acsu.buffalo.edu
Organization: State University of New York at Buffalo/Comp Sci
Lines: 37
Nntp-Posting-Host: dubhe.cs.buffalo.edu

In article <BwsqpC.Bpw@mentor.cc.purdue.edu> morpheus@sage.cc.purdue.edu (Morpheus Nosferatu) writes:
>Has anyone ever worked on, or even heard of, an adventure generator?
>
>I'm not talking about an adventure design language like TADS or Alan,
>but rather a stand-alone adventure generator that produces complete
>adventures, where the user need only give a minimal degree of input,
>such as the level of complexity, type of adventure (mystery, treasure
>hunt, etc.), size of adventure, and so forth?
>...
>But as anyone ever heard of someone trying to come up with a generator
>whigh would produce infocom-style text adventures?  I can just imagine
>what kind of limitations it would have, but I'm curious to know if
>anyone has tried this, and if so what degree of success they've had.

No.  I know some IF guys (David Graves?) are working on programs
that are supposed to be story generators, that can create a new story on
the fly given the user's actions.  But A) the stuff they are talking about
is not, in my opinion, as sophisticated as an Infocom adventure, and
B) I doubt they're going to have much success anyway, since the problem
is too hard at present.

The generator you speak of is not written, not being written, and not
anywhere on the horizon.  In 50 years, maybe.  In 20, definitely not.
The problem of writing interesting stories, which adhere to someone's
definition of a plot (with goal explanations, conflict, resolution,
comlication, climax, etc., all occuring at appropriate intervals)
is very hard, and I don't expect a solution soon.
But the problem of writing clever puzzles involves much greater
creativity, and I have seen NO evidence that ANYBODY has a clue in
these creativity issues; the most you will find in the field are a
few vague theories of creativity.

This problem is what Stuart Shapiro calls "AI-complete":  Solving it
would be equivalent to solving all the other problems of AI.

Phil
goetz@cs.buffalo.edu
``` 


## Recommended readings

<table>
   {% for publication in page.readings %}
    <tr>
      <td>
  {% if publication.url %}
    <a href="{{ publication.url }}">{{ publication.title }}.</a>
        {% else %}
    {{ publication.title }}.
  {% endif %}
  {{ publication.authors }}.
  {% if publication.publisher %} {{ publication.publisher }}. {% endif %}
  {{ publication.venue }}  {{ publication.year }}.

  {% if publication.abstract %}
  <!-- abstract button -->
  <a data-toggle="modal" href="#{{publication.id}}-abstract" class="label label-success">Abstract</a>
  <!-- /.abstract button -->
  <!-- abstract content -->
  <div id="{{publication.id}}-abstract" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="{{publication.id}}">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <h4 class="modal-title" id="{{publication.id}}">{{publication.title}}</h4>
        </div><!-- /.modal-header -->
        <div class="modal-body">
        {{publication.abstract}}
        </div><!-- /.modal-body -->
  </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
  </div><!-- /.abstract-content -->
  {% endif %}
    {% if publication.bibtex %}
  <!-- bibtex button -->
  <a data-toggle="modal" href="#{{publication.id}}-bibtex" class="label label-default">BibTex</a>
  <!-- /.bibtex button -->
  <!-- bibtex content -->
  <div id="{{publication.id}}-bibtex" class="modal fade" tabindex="-1" role="dialog" aria-labelledby="{{publication.id}}">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <h4 class="modal-title" id="{{publication.id}}">{{publication.title}}</h4>
        </div><!-- /.modal-header -->
        <div class="modal-body">
     <pre>{{publication.bibtex}}
           </pre>
        </div><!-- /.modal-body -->
  </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
  </div><!-- /.bibtex-content -->
  {% endif %}
</td></tr>
  {% endfor %}
</table>

