# Example #1 - Basic predicate query

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
