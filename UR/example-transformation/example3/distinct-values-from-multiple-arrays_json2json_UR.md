# Example #3 - Distinct values from multiple arrays

Testing:

- JSON to JSON
  
- Getting distinct values from multiple arrays  

>Query: "Get all the distinct colors of vehicles".

What order should it have?

Input:

```json
{
    "public-transport": {
        "bicycles": [{
            "title": "BMX bike",
            "colors": ["blue", "white"],
            "passenger-count": 1
        },{
            "title": "Tandem bike",
            "colors": ["white"],
            "passenger-count": 2
        },{
            "title": "Cargo e-bike",
            "colors": ["black", "brown", "orange"],
            "passenger-count": 1
        }],
        "trams": [{
            "title": "Historic tram",
            "colors": ["white", "red"],
            "passenger-count": 52
        },{
            "title": "Skoda tram",
            "colors": ["black", "yellow"],
            "passenger-count": 86
        }],
        "busses": [{
            "title": "Smol bus",
            "colors": ["yellow"],
            "passenger-count": 4
        }]
    }
}
```

Input in UR:

```json
{
    "@type": ["object"],
    "public-transport": [{
        "@type": ["object"],
        "bicycles": [{
            "@type": ["array"],
            "0": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "BMX bike"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["blue"]
                    }],
                    "1": [{
                        "@type": ["string"],
                        "@value": ["white"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["1"]
                }]
            }],
            "1": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "Tandem bike"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["white"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["2"]
                }]
            }],
            "2": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "Cargo e-bike"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["black"]
                    }],
                    "1": [{
                        "@type": ["string"],
                        "@value": ["brown"]
                    }],
                    "2": [{
                        "@type": ["string"],
                        "@value": ["orange"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["1"]
                }]
            }]
        }],
        "trams": [{
            "@type": ["array"],
            "0": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "Historic tram"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["white"]
                    }],
                    "1": [{
                        "@type": ["string"],
                        "@value": ["red"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["52"]
                }]
            }],
            "1": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "Skoda tram"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["black"]
                    }],
                    "1": [{
                        "@type": ["string"],
                        "@value": ["yellow"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["86"]
                }]
            }]
        }],
        "busses": [{
            "@type": ["array"],
            "0": [{
                "title": [{
                    "@type": ["string"],
                    "@value": "Smol bus"
                }],
                "colors": [{
                    "@type": ["array"],
                    "0": [{
                        "@type": ["string"],
                        "@value": ["yellow"]
                    }]
                }],
                "passenger-count": [{
                    "@type": ["number"],
                    "@value": ["4"]
                }]
            }]
        }]
    }]
}
```

Output in UR:

```json
{
  "@type": [
    "object"
  ],
  "colors-of-vehicles": [
    {
      "@type": [
        "array"
      ],
      "0": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "blue"
          ]
        }
      ],
      "1": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "white"
          ]
        }
      ],
      "2": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "black"
          ]
        }
      ],
      "3": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "brown"
          ]
        }
      ],
      "4": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "orange"
          ]
        }
      ],
      "5": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "red"
          ]
        }
      ],
      "6": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "yellow"
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
    "colors-of-vehicles": [
        "blue",
        "white",
        "black",
        "brown",
        "orange",
        "red",
        "yellow"
    ]
}
```

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "shift-values",
            "@comment": "We shift all the color values to new colors-of-vehicles array and leave all other props in the same place.",
            "@specs": {
                "public-transport": [{
                    "@var:transport-group": [{
                        "@var:_array-num-0": [{
                            "title": [],
                            "colors": [{
                                "@var:_array-color-num": [{
                                    "@path": ["colors-of-vehicles[]"]
                                }]
                            }],
                            "passenger-count": []
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "take-values",
            "@comment": "Now we take only the colors-of-vehicles to the output.",
            "@specs": {
                "colors-of-vehicles": []
            }
        },
    ]
}
```

> Ideas:
>
> transformation of colors to new array object, then filter out repeating values?
>
> Filtering would be not straight forward so maybe I wouldn't support it in the base solution.
