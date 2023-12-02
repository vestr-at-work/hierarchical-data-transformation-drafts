# Example #5 - Composite new values

Testing:

- XML to CSV
  
- Composition of multiple XML attributes into new values in CSV (used as ID)

>Query: "Get the coordinates of every path and identify it with distinct quest-part-id and save it in CSV"

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

```csv
quest-part-id,latitude,longitude
a24cb3e:1,50.3907506N,14.5458556E
a24cb3e:2,50.3907506N,14.5458556E
a24cb3e:3,50.3907506N,14.5458556E
a24cb4e:1,50.3907506N,14.5458556E
a24cb4e:2,50.3907506N,14.5458556E
```
