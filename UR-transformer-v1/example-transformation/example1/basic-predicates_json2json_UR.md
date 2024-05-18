# Example #1 - Basic predicate query

Testing:

- JSON to JSON
  
- Predicates on integer values

> Query: "Get title and group of all vehicles with passenger count greater than 1".

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

Output UR:

```json
{
    "@type": ["object"],
    "result": [{
        "@type": ["array"],
        "0": [{
            "title": [{
                "@type": ["string"],
                "@value": ["Tandem bike"]
            }],
            "group": [{
                "@type": ["string"],
                "@value": ["bicycles"]
            }]
        }],
        "1": [{
            "title": [{
                "@type": ["string"],
                "@value": ["Historic tram"]
            }],
            "group": [{
                "@type": ["string"],
                "@value": ["trams"]
            }]
        }],
        "2": [{
            "title": [{
                "@type": ["string"],
                "@value": ["Skoda tram"]
            }],
            "group": [{
                "@type": ["string"],
                "@value": ["trams"]
            }]
        }],
        "3": [{
            "title": [{
                "@type": ["string"],
                "@value": ["Smol bus"]
            }],
            "group": [{
                "@type": ["string"],
                "@value": ["busses"]
            }]
        }]
    }]
}
```

Output:

```json
{
    "result": [{
        "title": "Tandem bike",
        "group": "bicycles"
    },{
        "title": "Historic tram",
        "group": "trams"
    },{
        "title": "Skoda tram",
        "group": "trams"
    },{
        "title": "Smol bus",
        "group": "busses"
    }]
}
```

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "take-values",
            "@comment": "Take the title if the 'passanger-count' is greater than 1.",
            "@specs": {
                "public-transport": [{
                    "@var:transport-group": [{
                        "@var:_array-num-0": [{
                            "title": [{
                                "@predicate": ["..passenger-count.@value > 1"]
                            }]
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "shift-values",
            "@comment": "Shift title to new object array and create in that same object new variable key named 'group' with the value of the variable '@var:transport-group' as a value in the output.",
            "@specs": {
                "public-transport": [{
                    "@var:transport-group": [{
                        "@var:_array-num-0": [{
                            "title": [{
                                "@path": ["result.[].title"]
                            }],
                            "@var::transport-group": [{
                                "@path": ["result.[].group"]
                            }]
                        }]
                    }]
                }]
            }
        }
    ]
}
```

> Notice:
> Wildcards (as in wildcards "*" in JOLT) are named variables and can be referenced via @var::name-of-the-variable.

> We have to allow to do this kind of operation (creating of a new key within 'shift-values' operation), because after the shift there would be no information with the name of the 'transport-group'. Theoreticaly we could make new operation with the key creation before 'shift-values'. Would that be more clear?
