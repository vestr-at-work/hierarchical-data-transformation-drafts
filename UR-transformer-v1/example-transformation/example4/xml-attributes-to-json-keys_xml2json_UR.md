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
  "quests": [
    {
      "@type": [
        "object"
      ],
      "a24cb3e": [
        {
          "@type": [
            "object"
          ],
          "multi-part": [
            {
              "@type": [
                "boolean"
              ],
              "@value": [
                "True"
              ]
            }
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
                "Once upon a time there was a bad feudal lord ..."
              ]
            }
          ],
          "part": [
            {
              "@type": [
                "array"
              ],
              "0": [
                {
                  "@type": [
                    "object"
                  ],
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "1"
                      ]
                    }
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
                        "Last he has been spotted holding his chest running into the woods south of the town."
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
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "2"
                      ]
                    }
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
              "2": [
                {
                  "@type": [
                    "object"
                  ],
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "3"
                      ]
                    }
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
          ]
        }
      ],
      "a24cb4e": [
        {
          "@type": [
            "object"
          ],
          "multi-part": [
            {
              "@type": [
                "boolean"
              ],
              "@value": [
                "True"
              ]
            }
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
                "Once upon a time there was a quest ..."
              ]
            }
          ],
          "part": [
            {
              "@type": [
                "array"
              ],
              "0": [
                {
                  "@type": [
                    "object"
                  ],
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "1"
                      ]
                    }
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
              "1": [
                {
                  "@type": [
                    "object"
                  ],
                  "num": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "2"
                      ]
                    }
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
  ]
}
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

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "shift-values",
            "@comment": "First declaring the value of 'id' as a value variable then using it to create new quest object of the name of the id and then copying all the properties to it. In the second part of the transformation, we are transforming UR representation of XML array to real JSON array with a function call.",
            "@specs": {
                "quests": [{
                    "@var:quest": [{
                        "@attributes": [{
                            "id": [{
                                "@value-var:quest-id": []
                            }],
                            "multi-part": [{
                                "@path": ["quests.@value-var:quest-id.multi-part.@value"]
                            }]
                        }],
                        "name": [{
                            "@path": ["quests.@value-var:quest-id.name.@value"]
                        }],
                        "short-description": [{
                            "@path": ["quests.@value-var:quest-id.short-description.@value"]
                        }],
                        "long-description": [{
                            "@path": ["quests.@value-var:quest-id.long-description.@value"]
                        }],
                        "@var:parts": [{
                            "@attributes": [{
                                "num": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].num.@value"]
                                }],
                                "location": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].location"]
                                }],
                                "clue": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].clue.@value"]
                                }]
                            }]
                        }]
                    }]
                }]
            }
        }
    ]
}
```

> Ideas:
>
> Shift 'mutipart' attribute value to new property named after attribute value, then move the whole 'quest' object to new object called by the 'id' attribute value and then remove the @attributes objects
>
> How to transform xml "arrays" in UR to json real arrays?
> Using different symbol than '@' in the transformations, so we can take the number from the key and put the object in new array?
> Or I guess I can just add the elements to the output array and thats it. --- NO, in that case we don't know then to close the object in array. We have to make the number explicit.
> We could have some kind of helper function that would extract the array number from the variable.
> Should we let users to create their own functions?


> Notice:
> 
> "@value-var:[...]" for declaring a value of some property as a value variable for later use
> "@func:extract-array-index(@var:parts)" for calling functions (to extract xml array index in this example)
