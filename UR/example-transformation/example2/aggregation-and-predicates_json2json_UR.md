# Example #2 - Aggregation and predicate query on arrays

Testing:

- JSON to JSON
  
- Aggregation and predicate usage on arrays

> Query: "Get number of at least partly white vehicles".

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
    "@type": ["object"],
    "partly-white-vehicle-count": [{
        "@type": ["number"],
        "@value": ["3"]
    }]
}
```

Output:

```json
{
    "partly-white-vehicle-count": 3
}
```

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "take-values",
            "@comment": "Take only the vehicles with white color present.",
            "@specs": {
                "public-transport": [{
                    "@var:transport-group": [{
                        "@var:_array-num-0": [{
                            "colors": [{
                                "@var:_array-color-num": [{
                                    "@predicate": [".@value == 'white'"]
                                }]
                            }]
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "count-values",
            "@comment": "Operation count-values counts variable matches and outputs the current number when it encounters @output:count:var:[...] tag.",
            "@specs": {
                "public-transport": [{
                    "@var:transport-group": [{
                        "@count:var:white-vehicle": []
                    }]
                }],
                "@output:count:var:white-vehicle": [{
                    "@tag": ["partly-white-vehicle-count"]
                }]
            }
        },
        {
            "@operation": "take-values",
            "@comment": "Now we have to take only the partly-white-vehicle-count to the output.",
            "@specs": {
                "partly-white-vehicle-count": []
            }
        },
    ]
}
```

> Ideas:
>
> remove/take-values operation with predicate if @var::vehicle.colors.@var::color-num.@value == "white" on vehicles.
> shift vehicle titles to some output array
> then do count operation on the array or something
