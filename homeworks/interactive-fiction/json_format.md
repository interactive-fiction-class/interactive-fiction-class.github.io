---
layout: default
img: scribe.png
img_link: https://parl.ai/projects/light/
caption: Automatically write descriptions for text adventure games
title: JSON format
---

# JSON format

Here's a description of the JSON format used in our `text_adventure_game` in the `to_json` and `from_json` functions that are used to load and save games. 

### Game class

```
{
    "player": The name of the player character,
    "start_at": The name of the starting location for th player,
    "game_history": a list of all the player's commands and the game's outputs,
    "game_over": a boolean that indicates whether the game is over
    "game_over_description": a string that describes the end of the game,
    "characters": a list of all the characters in the game, including the player characer and non-player characters.  Characters are represented with their own JSON data structure,
    "locations": a list of all of the locations in the game.  Locations are represented with their own JSON data structure,
    "actions": a list of the names of special actions that specific to this game.
}
```

### Character class


Characters are defined by a JSON dictionary with the following keys and values:
```
{
    "name": the name of the character (assumed to be unique),
    "description": a 1-2 sentence physical description of the character.
    "persona": a 1-2 sentence description of the character's persona, written in the first person,
    "location": the name of the game location where the character currently is located,
    "inventory": a dictionary of items in the character's inventory. The keys are the name of the item, the values are an item JSON,
    "properties", a dictionary of character properties. These key value pairs can be things like "is_dead": boolean, "character_type": "human" or "ghost", "is_conscious": boolean, "emotional_state": string like "sad" or suspicious",
    "commands": a list of special commands associated with this character (typically an empty list)
}
```

Here's an example for the *ghost* character in Action Castle:
```
{
    "name": "ghost",
    "description": "A ghost with bony, claw-like fingers and who is wearing a crown.",
    "commands": [],
    "properties": {
        "character_type": "ghost",
        "is_dead": true,
        "is_banished": false
    },
    "persona": "I was murdered by the guard. I will haunt this castle until banished. If you linger before my apparition, I will plunge my ghostly hand inside you and stop your heart",
    "inventory": {
        "crown": {
            "name": "crown",
            "description": "a crown",
            "commands": [
                "wear crown"
            ],
            "properties": {
                "is_gettable": true,
                "is_container": false,
                "is_drink": false,
                "is_food": false,
                "is_surface": false,
                "is_weapon": false,
                "is_wearable": true
            },
            "examine_text": "A CROWN FIT FOR A KING.",
            "owner": "ghost"
        }
    },
    "location": "Dungeon"
}
```

### Item class

Items contain the following fields:

```
{
  "name": the name of the item (assumed to be unique),
  "description": a short phrase describing the item,
  "examine_text": a longer description of the item that is displayed if the player looks closely at the item,
  "commands": a list of special commands that can be used with this item,
  "properties": a dictionary of the item's properties. Keys include: is_container, is_drink, is_food, is_gettable, is_surface, is_weapon, is_wearable.  Each of which has an appropriate boolean value.
  "location" or "owner": the name of the location of the object, or the character that has the item in their inventory. 
}
```

Here's an example of the *candle* item from Action Castle:
```
{
    "name": "candle",
    "description": "a strange candle",
    "commands": [
        "light candle",
        "read runes"
    ],
    "properties": {
        "is_gettable": true,
        "is_lightable": true,
        "is_lit": false,
        "is_container": false,
        "is_drink": false,
        "is_food": false,
        "is_surface": false,
        "is_weapon": false,
        "is_wearable": false
    },
    "examine_text": "THE CANDLE IS COVERED IN STARGE RUNES.",
    "location": "Great Feasting Hall"
}
```

### Location class


```
{
    "name": the name of the location (assumed to be unique),
    "description": a description of the location, 
    "travel_descriptions": 
    "connections": The exits from this location are stroed in a dictionary with keys being directions and values being the names of the connecetd location.  Directions can be cardinal directions or relative directions,
    "travel_descriptions": a dictionary of optional descriptions of the travel from this location to a connected location.  The keys are the same as for connections, and the values are the description of travel,
    "blocks": a dictionary of any blocked directions. Keys are zero or more of the dicrections from connections, and values are they type of block.
    "items": a dictionary of items in this location.  The keys are the name of the item, the values are an item JSON,
    "characters": a dictionary of items in this location.  The keys are the name of the character, the values are a character JSON,
    "has_been_visited": a boolean value indicating whether the player has been to this location,
    "commands": a list of special commands at this location (typically empty)
    "properties": a dictionary of properties of this location (typically empty)
},
```

Here's the *drawbridge* location from Action Castle:

```
{
    "name": "Drawbridge",
    "description": "You are standing on one side of a drawbridge leading to ACTION CASTLE.",    
    "connections": {
        "west": "Winding Path",
        "east": "Courtyard"
    },
    "travel_descriptions": {
        "west": "",
        "east": ""
    },
    "blocks": {
        "east": {
            "_type": "Troll_Block"
        }
    },
    "items": {},
    "characters": {
        "troll": "troll"
    },
    "has_been_visited": false,
    "commands": [],
    "properties": {},

}
```

Here's the full [JSON file for Action Castle](action_castle.json).
