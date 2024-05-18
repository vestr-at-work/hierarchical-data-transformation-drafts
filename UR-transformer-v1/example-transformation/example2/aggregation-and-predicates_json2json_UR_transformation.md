# Example #2 - Aggregation and predicate query on arrays

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
