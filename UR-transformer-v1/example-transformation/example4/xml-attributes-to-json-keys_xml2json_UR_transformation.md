# Example #4 - XML attributes to JSON keys

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "shift-values",
            "@comment": "First declaring the value of 'id' as a value variable then using it to create new quest object of the name of the id and then copying all the properties to it. In the second part of the transformation, we are transforming UR representation of XML array to real JSON array with a function call.",
            "@specs": {
                "quests": [{
                    "@var:quest": [{
                        "@attributes": [{
                            "id": [{
                                "@value-var:quest-id": []
                            }],
                            "multi-part": [{
                                "@path": ["quests.@value-var:quest-id.multi-part.@value"]
                            }]
                        }],
                        "name": [{
                            "@path": ["quests.@value-var:quest-id.name.@value"]
                        }],
                        "short-description": [{
                            "@path": ["quests.@value-var:quest-id.short-description.@value"]
                        }],
                        "long-description": [{
                            "@path": ["quests.@value-var:quest-id.long-description.@value"]
                        }],
                        "@var:parts": [{
                            "@attributes": [{
                                "num": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].num.@value"]
                                }],
                                "location": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].location"]
                                }],
                                "clue": [{
                                    "@path": ["quests.@value-var:quest-id.part[@func:extract-array-index(@var:parts)].clue.@value"]
                                }]
                            }]
                        }]
                    }]
                }]
            }
        }
    ]
}
```

> Ideas:
>
> Shift 'mutipart' attribute value to new property named after attribute value, then move the whole 'quest' object to new object called by the 'id' attribute value and then remove the @attributes objects
>
> How to transform xml "arrays" in UR to json real arrays?
> Using different symbol than '@' in the transformations, so we can take the number from the key and put the object in new array?
> Or I guess I can just add the elements to the output array and thats it. --- NO, in that case we don't know then to close the object in array. We have to make the number explicit.
> We could have some kind of helper function that would extract the array number from the variable.
> Should we let users to create their own functions?
----
> Notice:
>
> "@value-var:[...]" for declaring a value of some property as a value variable for later use
> "@func:extract-array-index(@var:parts)" for calling functions (to extract xml array index in this example)
