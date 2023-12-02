# Example #6 - Multiple outputs from one input

Testing:

- JSON to JSON
  
- Get value to multiple output fields

>Query: "Get all tel numbers to 'all-tel-nums' array and change the structure of the data (put 'person' into the 'department')"

Input:

```json
{
    "person": {
        "tel": 444432421
    },
    "department": {
        "tel": 732444111
    }
}
```

Output:

```json
{
    "all-tel-nums": [444432421, 732444111],
    "department": {
        "tel": 732444111,
        "person": {
            "tel": 444432421
        }
    }
}
```
