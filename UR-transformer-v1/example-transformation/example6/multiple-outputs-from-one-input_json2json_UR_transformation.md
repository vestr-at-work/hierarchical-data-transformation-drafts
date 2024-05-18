# Example #6 - Multiple outputs from one input

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "shift-values",
            "@comment": "Shifting the tel number values to two locations in the output.",
            "@specs": {
                "department": [{
                    "tel": [{
                        "@path": ["department.tel.@value", "all-tel-nums[]"]
                    }]
                }],
                "person": [{
                    "@path": ["department.person.tel.@value", "all-tel-nums[]"]
                }]
            }
        }
    ]
}
```

> Ideas
>
> Just specify two output paths in the shift operation.
