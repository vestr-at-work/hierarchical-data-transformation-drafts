# Example #7 - Parts of values to new value with new key

Testing:

- JSON to JSON
  
- Get parts of values to new value with new key

>Query: "Transform every tel number in every contact. Seperate the preselection from the tel number."

Input:

```json
{
    "contact": {
        "tel": "+420 444432421"
    },
    "department": {
        "info": {
            "contact": {
                "tel": "+420 732444111"
            }
        }
    }
}
```

Output:

```json
{
   "contact": {
        "tel": 444432421,
        "preselection": "+420"
    },
    "department": {
        "info": {
            "contact": {
                "tel": 732444111,
                "preselection": "+420"
            }
        }
    }
}
```
