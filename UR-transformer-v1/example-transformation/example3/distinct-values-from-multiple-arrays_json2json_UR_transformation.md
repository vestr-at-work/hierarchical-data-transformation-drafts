# Example #3 - Distinct values from multiple arrays

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
