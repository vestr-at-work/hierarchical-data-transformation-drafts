# Example #1 - Basic predicate query

Testing:

- JSON to JSON
  
- Predicates on integer values

> Query: "Get title and group of all vehicles with passenger count greater than 1".

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
    "result": [{
        "title": "Tandem bike",
        "group": "bicycles"
    },{
        "title": "Historic tram",
        "group": "trams"
    },{
        "title": "Skoda tram",
        "group": "trams"
    },{
        "title": "Smol bus",
        "group": "busses"
    }]
}
```