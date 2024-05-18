# Example #4 - XML attributes to JSON keys

Testing:

- XML to JSON
  
- Transformation of XML attributes to JSON keys

>Query: "Transform data to json including the attributes as keys in the quests object".

Input:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<quests>
    <quest 
        id="a24cb3e"
        multi-part="true"
    >
        <name>Lord's last words</name>
        <short-description>Finding treasure of the fleeing lord.</short-description>
        <long-description>
            One upon a time there was a bad feudal lord ...
        </long-description>
    
        <part num="1">
            <location>
                <latitude>50.3907506N</latitude>
                <longitude>14.5458556E</longitude>
            </location>
            <clue>Last he has been seen gripping on to his chest running into the woods south of the town.</clue>
        </part>
        <part num="2">
            <location>
                <latitude>50.3907506N</latitude>
                <longitude>14.5458556E</longitude>
            </location>
            <clue>Lorem ipsum coloret sudo pathusm.</clue>
        </part>
        <part num="3">
            <location>
                <latitude>50.3907506N</latitude>
                <longitude>14.5458556E</longitude>
            </location>
            <clue>Try to investigate the cave.</clue>
        </part>
    </quest>
    
    <quest 
        id="a24cb4e"
        multi-part="true"
    >
        <name>Quest number 2</name>
        <short-description>Finding quest of the number 2.</short-description>
        <long-description>
            One upon a time there was a quest ...
        </long-description>
    
        <part num="1">
            <location>
                <latitude>50.3907506N</latitude>
                <longitude>14.5458556E</longitude>
            </location>
            <clue>Lorem ipsum coloret sudo pathusm. Idre pute hletro imo.</clue>
        </part>
        <part num="2">
            <location>
                <latitude>50.3907506N</latitude>
                <longitude>14.5458556E</longitude>
            </location>
            <clue>Lorem ipsum coloret sudo pathusm.</clue>
        </part>
    </quest>
</quests>
```

Output:

```json
{
    "quests": {
        "a24cb3e": {
            "multi-part": true,
            "name": "Lord's last words",
            "short-description": "Finding treasure of the fleeing lord.",
            "long-description": "Once upon a time there was a bad feudal lord ...",
            "part": [{
                "num": 1,
                "location": {
                    "latitude": "50.3907506N",
                    "longitude": "14.5458556E"
                },
                "clue": "Last he has been spotted holding his chest running into the woods south of the town."
            },{
                "num": 2,
                "location": {
                    "latitude": "50.3907506N",
                    "longitude": "14.5458556E"
                },
                "clue": "Lorem ipsum coloret sudo pathusm."
            },{
                "num": 3,
                "location": {
                    "latitude": "50.3907506N",
                    "longitude": "14.5458556E"
                },
                "clue": "Try to investigate the cave."
            }]
        },
        "a24cb4e": {
            "multi-part": true,
            "name": "Quest number 2",
            "short-description": "Finding quest of the number 2.",
            "long-description": "Once upon a time there was a quest ...",
            "part": [{
                "num": 1,
                "location": {
                    "latitude": "50.3907506N",
                    "longitude": "14.5458556E"
                },
                "clue": "Lorem ipsum coloret sudo pathusm. Idre pute hletro imo."
            },{
                "num": 2,
                "location": {
                    "latitude": "50.3907506N",
                    "longitude": "14.5458556E"
                },
                "clue": "Lorem ipsum coloret sudo pathusm."
            }]
        }
    }
}
```
