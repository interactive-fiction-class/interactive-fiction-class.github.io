---
layout: default
img: scribe.png
img_link: https://parl.ai/projects/light/
caption: Automatically write descriptions for text adventure games
title: Location JSON
---

```

        {
            "name": "The Show Room Inside The Castle",
            "description": "The Show Room Inside the Castle is meant to impress as well as cause fear to whomever enters the room.  The Duke who lives here is a hunter and keeps his captures here.  Some of the thinks preserved and shown on his wall are shocking.  The preserved eyes stare back and let you know the Duke knows no mercy, be careful what you say in this room.  The floor is white like ivory and the walls are also white, but the ceiling is painted and tells a story of the Duke's conquest.",
            "background": "It took many years to build this room.  No other hunter has a room like it, even the king is jealous, those who view this room fear the Duke more than the King. Could there be a conspiracy?  Danger and intrigue live in this room.  You feel it as soon as you enter and view the walls and the ceiling, which compete for your fear and your respect.",
            "commands": [],
            "properties": {},
            "blocks": {},
            "travel_descriptions": {},
            "connections": {
                "west": "Washroom",
                "down": "Basement"
            },
            "items": {
                "Mounted Lion Head": {
                    "name": "Mounted Lion Head",
                    "description": "A large lion's head, frozen in a roar, mounted on the wall.",
                    "examine_text": "Upon closer inspection, the beast's eyes seem to stare back at you, reflecting a spark of life that was extinguished long ago. The teeth remain sharp and imposing, a reminder of the power this king of the jungle once held.",
                    "properties": {
                        "is_container": false,
                        "is_drink": false,
                        "is_food": false,
                        "is_gettable": false,
                        "is_surface": true,
                        "is_weapon": false,
                        "is_wearable": false
                    }
                },
                "Ivory Floor": {
                    "name": "Ivory Floor",
                    "description": "A smooth polished floor, gleaming white like ivory.",
                    "examine_text": "Looking closer, the floor shines in the light, reflecting your visage back at you. It's cold underfoot and slippery, as though worn smooth by generations of shoes.",
                    "properties": {
                        "is_container": false,
                        "is_drink": false,
                        "is_food": false,
                        "is_gettable": false,
                        "is_surface": true,
                        "is_weapon": false,
                        "is_wearable": false
                    }
                },
                "Mural Ceiling": {
                    "name": "Mural Ceiling",
                    "description": "A grand mural painted on the ceiling, depicting the Duke's conquests.",
                    "examine_text": "Lifting your gaze to the ceiling, colourful scenes of battle and triumph come to life, all leading to a central figure - the Duke - resplendent in armor. There is an undercurrent of menace in the portrayed scenes, an outline of a story best left untold.",
                    "properties": {
                        "is_container": false,
                        "is_drink": false,
                        "is_food": false,
                        "is_gettable": false,
                        "is_surface": true,
                        "is_weapon": false,
                        "is_wearable": false
                    }
                },
                "Antique Weaponry": {
                    "name": "Antique Weaponry",
                    "description": "Ancient weapons, presumably from the Duke's ancestors, hung carefully on the walls.",
                    "examine_text": "Upon examination, the weapons are well maintained despite their age. Edges still sharp, hilts tightly bound in leather. They carry tales of victory and defeat, depthless history in each piece.",
                    "properties": {
                        "is_container": false,
                        "is_drink": false,
                        "is_food": false,
                        "is_gettable": false,
                        "is_surface": false,
                        "is_weapon": true,
                        "is_wearable": false
                    }
                }
            },
            "characters": {
                "Duke of the Castle": {
                    "name": "Duke of the Castle",
                    "description": "The Duke is a tall, imposing figure, always dressed in rich, elaborately adorned hunting gear. His eyes, similar to those of the animals he hunts, are always watchful, cold and unyielding.",
                    "persona": "I have walked through the woods and jungles most formidable beasts willingly call home, and made them my own. The fear you sense in this room, that's mere child's play compared to my true prowess.",
                    "goal": "My ambition is to make the greatest hunting conquest known to mankind.",
                    "location": "The Show Room Inside The Castle",
                    "inventory": {
                        "Map of Old Forest": {
                            "name": "Map of Old Forest",
                            "description": "An aged parchment depicting the vast expanse of the neighboring forest.",
                            "examine_text": "Upon closer examination, you can see minute details of the forest trails, the rivers that serpentine through the dense vegetation, and the locations of significant game creatures. The map is old and fragile, with the edges burnt and tattered. Despite the wear, the ink remains steadfast, showcasing the Duke's meticulous care for this treasure.",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": false,
                                "is_wearable": false
                            },
                            "commands": []
                        },
                        "Imperious Bow": {
                            "name": "Imperious Bow",
                            "description": "An imposing bow that once belonged to the Duke.",
                            "examine_text": "The bow is made of a dark, polished wood, streaked with swirls of deep red and black, and feels firm and unyielding to the touch. The string is made of woven metallic strands which glimmer even in dim light. Ornate carvings of hunting scenes run along the length of the bow, testifying to the Duke's skill and valor.",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": true,
                                "is_wearable": false
                            },
                            "commands": []
                        },
                        "Ivory Dagger": {
                            "name": "Ivory Dagger",
                            "description": "A knife made from ivory, bearing the Duke's crest.",
                            "examine_text": "The small dagger has a blade carved cunningly from a single piece of ivory. The hilt carries the crest of the Duke\u2014a snarling beast, mouth open in a roar. Despite its size, the weapon looks deadly serious. A weapon of stature and prestige, it is as deadly as its owner.",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": true,
                                "is_wearable": false
                            },
                            "commands": []
                        }
                    }
                },
                "Lady Isolde": {
                    "name": "Lady Isolde",
                    "description": "Lady Isolde is a striking beauty, her dark curls cascading down her shoulders. Her eyes seem to hold secrets, and doubts, as she moves through the room with a grace that belies her uneasy demeanor.",
                    "persona": "I move in these high circles with the best of them, but the horrors I've seen in this room...I fear for what is to come.",
                    "goal": "To uncover and expose the Duke's cruel hunting practices.",
                    "location": "The Show Room Inside The Castle",
                    "inventory": {
                        "Golden Comb": {
                            "name": "Golden Comb",
                            "description": "A delicate Golden Comb",
                            "examine_text": "A delicate comb made of solid gold, enameled with tiny ruby stones. The handle is intricately engraved with the family crest of the Duke. It is a symbol of status, wealth, and power",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": false,
                                "is_wearable": true
                            },
                            "commands": []
                        },
                        "Ivory Fan": {
                            "name": "Ivory Fan",
                            "description": "An elegant Ivory Fan",
                            "examine_text": "An elegant Ivory fan, with a painted scene of exotic flowers. The handle is made of gold, engraved with the family crest of the Duke. It's a symbol of delicate beauty and high status in the society",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": false,
                                "is_wearable": true
                            },
                            "commands": []
                        },
                        "Secret Letter": {
                            "name": "Secret Letter",
                            "description": "A well-hidden Secret Letter",
                            "examine_text": "This is a well-hidden secret letter, with aristocratic seal of the Duke. The contents of this letter could spark a scandal, or even a rebellion. It smells of perfume and danger",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": false,
                                "is_wearable": false
                            },
                            "commands": []
                        }
                    }
                },
                "Sir Lionel": {
                    "name": "Sir Lionel",
                    "description": "Sir Lionel, a seasoned knight with a booming laugh and a jolly demeanor. His booming laughter though, does not quite reach his eyes, and a keen observer might notice his constant, vigilant watch over Lady Isolde.",
                    "persona": "I've served this castle for years, seen its rises and falls. This current Duke, though...makes me nervous. And I\u2019m not one to scare easy",
                    "goal": "To protect Lady Isolde from the Duke and his dangerous obsession.",
                    "location": "The Show Room Inside The Castle",
                    "inventory": {
                        "Iron Sword": {
                            "name": "Iron Sword",
                            "description": "A mighty sword made of iron, tarnished and well-used.",
                            "examine_text": "The blade reflects the light from the torches, revealing a series of notches that mark countless battles. The grip is worn, rubbed smooth from years of use. It feels heavy, the weight of it suggesting its deadly purpose.",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": true,
                                "is_wearable": false
                            },
                            "commands": [],
                            "location": "Washroom"
                        },
                        "Shield of the Castle": {
                            "name": "Shield of the Castle",
                            "description": "A large, circular shield bearing the crest of the castle.",
                            "examine_text": "The crest on the face of the shield depicts a tower, a symbol of the power and safety. The edge of the shield bears numerous dents and scratches, hallmarks of many a violent clash. Its weight suggests sturdiness, its cool touch a sense of unyielding defense.",
                            "properties": {
                                "is_container": false,
                                "is_drink": false,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": true,
                                "is_wearable": true
                            },
                            "commands": [],
                            "location": "Washroom"
                        },
                        "Healing Potion": {
                            "name": "Healing Potion",
                            "description": "A small, glass bottle filled with a glowing, red liquid.",
                            "examine_text": "The liquid inside the glass vial glows with an inviting warmth. Sealed tightly with a stopper, the liquid is still and calm. In the light, it emits a soothing aura. Tiny bubbles rise slowly from the bottom of the bottle, promising a speedy recovery.",
                            "properties": {
                                "is_container": false,
                                "is_drink": true,
                                "is_food": false,
                                "is_gettable": true,
                                "is_surface": false,
                                "is_weapon": false,
                                "is_wearable": false
                            },
                            "commands": [],
                            "location": "Washroom"
                        }
                    }
                }
            },
            "has_been_visited": false
        },
```