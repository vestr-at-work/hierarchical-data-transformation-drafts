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

Input in UR:

```json
{
  "quests": [
    {
      "@type": [
        "object"
      ],
      "@0:quest": [
        {
          "@attributes": [
            {
              "id": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "a24cb3e"
                  ]
                }
              ],
              "multi-part": [
                {
                  "@type": [
                    "boolean"
                  ],
                  "@value": [
                    "true"
                  ]
                }
              ]
            }
          ],
          "@type": [
            "object"
          ],
          "name": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Lord's last words"
              ]
            }
          ],
          "short-description": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Finding treasure of the fleeing lord."
              ]
            }
          ],
          "long-description": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "\n            One upon a time there was a bad feudal lord ...\n        "
              ]
            }
          ],
          "@0:part": [
            {
              "@attributes": [
                {
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "1"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "location": [
                {
                  "@type": [
                    "object"
                  ],
                  "latitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "50.3907506N"
                      ]
                    }
                  ],
                  "longitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "14.5458556E"
                      ]
                    }
                  ]
                }
              ],
              "clue": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "Last he has been seen gripping on to his chest running into the woods south of the town."
                  ]
                }
              ]
            }
          ],
          "@1:part": [
            {
              "@attributes": [
                {
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "2"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "location": [
                {
                  "@type": [
                    "object"
                  ],
                  "latitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "50.3907506N"
                      ]
                    }
                  ],
                  "longitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "14.5458556E"
                      ]
                    }
                  ]
                }
              ],
              "clue": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "Lorem ipsum coloret sudo pathusm."
                  ]
                }
              ]
            }
          ],
          "@2:part": [
            {
              "@attributes": [
                {
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "3"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "location": [
                {
                  "@type": [
                    "object"
                  ],
                  "latitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "50.3907506N"
                      ]
                    }
                  ],
                  "longitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "14.5458556E"
                      ]
                    }
                  ]
                }
              ],
              "clue": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "Try to investigate the cave."
                  ]
                }
              ]
            }
          ]
        }
      ],
      "@1:quest": [
        {
          "@attributes": [
            {
              "id": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "a24cb4e"
                  ]
                }
              ],
              "multi-part": [
                {
                  "@type": [
                    "boolean"
                  ],
                  "@value": [
                    "true"
                  ]
                }
              ]
            }
          ],
          "@type": [
            "object"
          ],
          "name": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Quest number 2"
              ]
            }
          ],
          "short-description": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Finding quest of the number 2."
              ]
            }
          ],
          "long-description": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "\n            One upon a time there was a quest ...\n        "
              ]
            }
          ],
          "@0:part": [
            {
              "@attributes": [
                {
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "1"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "location": [
                {
                  "@type": [
                    "object"
                  ],
                  "latitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "50.3907506N"
                      ]
                    }
                  ],
                  "longitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "14.5458556E"
                      ]
                    }
                  ]
                }
              ],
              "clue": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "Lorem ipsum coloret sudo pathusm. Idre pute hletro imo."
                  ]
                }
              ]
            }
          ],
          "@1:part": [
            {
              "@attributes": [
                {
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "2"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "location": [
                {
                  "@type": [
                    "object"
                  ],
                  "latitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "50.3907506N"
                      ]
                    }
                  ],
                  "longitude": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "14.5458556E"
                      ]
                    }
                  ]
                }
              ],
              "clue": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "Lorem ipsum coloret sudo pathusm."
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```

Output in UR:

```json
{
  "@type": [
    "object"
  ],
  "@rows": [
    {
      "0": [
        {
          "@type": [
            "object"
          ],
          "quest-part-id": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "a24cb3e:1"
              ]
            }
          ],
          "latitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "50.3907506N"
              ]
            }
          ],
          "longitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "14.5458556E"
              ]
            }
          ]
        }
      ],
      "1": [
        {
          "@type": [
            "object"
          ],
          "quest-part-id": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "a24cb3e:2"
              ]
            }
          ],
          "latitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "50.3907506N"
              ]
            }
          ],
          "longitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "14.5458556E"
              ]
            }
          ]
        }
      ],
      "2": [
        {
          "@type": [
            "object"
          ],
          "quest-part-id": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "a24cb3e:3"
              ]
            }
          ],
          "latitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "50.3907506N"
              ]
            }
          ],
          "longitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "14.5458556E"
              ]
            }
          ]
        }
      ],
      "3": [
        {
          "@type": [
            "object"
          ],
          "quest-part-id": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "a24cb4e:1"
              ]
            }
          ],
          "latitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "50.3907506N"
              ]
            }
          ],
          "longitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "14.5458556E"
              ]
            }
          ]
        }
      ],
      "4": [
        {
          "@type": [
            "object"
          ],
          "quest-part-id": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "a24cb4e:2"
              ]
            }
          ],
          "latitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "50.3907506N"
              ]
            }
          ],
          "longitude": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "14.5458556E"
              ]
            }
          ]
        }
      ]
    }
  ]
}
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

> Ideas:
>
> First shift quest-id, part-num, latitude and longitude to new array of numbered row objects, then combine quest-id and part-num into quest-part-id and then remove quest-id and part-num properties.
>
> This we will probably not be able to do, but we can shift the values into four columns 'quest-id', 'part-num', 'latitude', 'longitude'
>
> We have another problem tho, how to put the quest-id into all the appropriate row objects, when these object do not yet exist when parsing guest-id and we dont know how many of them there will be...
