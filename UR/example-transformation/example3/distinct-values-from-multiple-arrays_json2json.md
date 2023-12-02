# Example #3 - Distinct values from multiple arrays

Testing:

- JSON to JSON
  
- Getting distinct values from multiple arrays  

>Query: "Get all the distinct colors of vehicles".

What order should it have?

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

Output:

```json
{
    "colors-of-vehicles": [
        "blue",
        "white",
        "black",
        "brown",
        "orange",
        "red",
        "yellow"
    ]
}
```
