# Example #8 - Aggregation only from inner objects

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "take-values",
            "@comment": "Take only department tel numbers.",
            "@specs": {
                "@var:department": [{
                    "info": [{
                        "contact": [{
                            "tel": []
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "count-values",
            "@comment": "Operation count-values counts variable matches and outputs the current number when it encounters @output:count:var:[...] tag.",
            "@specs": {
                "@var:department": [{
                    "info": [{
                        "contact": [{
                            "tel": [{
                                "@count:var:lower-level-contact": []
                            }]
                        }]
                    }]
                }],
                "@output:count:var:lower-level-contact": [{
                    "@tag": ["lower-level-contacts-count"]
                }]
            }
        },
        {
            "@operation": "take-values",
            "@comment": "Now we have to take only the lower-level-contacts-count to the output.",
            "@specs": {
                "lower-level-contacts-count": []
            }
        },
    ]
}
```

> Ideas:
>
> First shift the lower-level-contacts to some new array using two key-variables to ommit the higher-level-contact and then use some new sum operation on the array.
