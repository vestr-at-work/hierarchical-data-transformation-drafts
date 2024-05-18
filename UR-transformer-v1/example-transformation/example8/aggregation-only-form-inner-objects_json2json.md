# Example #8 - Aggregation only from inner objects

Testing:

- JSON to JSON
  
- Tests the matching ability of the transform language

>Query: "Get the number of contacts that are not in the top level of the document."

Input:

```json
{
    "contact": {
        "tel": "+420 444432421"
    },
    "math-department": {
        "info": {
            "contact": {
                "tel": "+420 732444111"
            }
        }
    },
    "computer-science-department": {
        "info": {
            "contact": {
                "tel": "+420 001010111"
            }
        }
    }
}
```

Output:

```json
{
   "lower-level-contacts-count": 2
}
```
