# Example #9 - XSLT-like transformation

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "remove-values",
            "@comment": "Removing all the values that are not used in the output.",
            "@specs": {
                "catalog": [{
                    "@var:cd": [{
                        "country": [],
                        "company": [],
                        "price": [{
                            "@predicate": ["@value <= 10"]
                        }],
                        "year": []
                    }]
                }]
            }
        },
        {
            "@operation": "shift-values",
            "@comment": "Shift values to their locations in the output xml. Notice use of '@@' to escape '@' symbol. Also notice use of function within a function to get the right UR XML array index. The 'price' key we shift for later use.",
            "@specs": {
                "catalog": [{
                    "@var:cd": [{
                        "title": ["html.body.table.@@@func:add(@func:extract-array-index(@var:cd), 1):tr.@@0:td.@value"],
                        "artist": ["html.body.table.@@@func:add(@func:extract-array-index(@var:cd), 1):tr.@@1:td.@value"],
                        "price": ["html.body.table.@@@func:add(@func:extract-array-index(@var:cd), 1):tr.@@2:td.@value"]
                    }]
                }]
            }
        },
        {
            "@operation": "defualt-values",
            "@comment": "Add 'h2' tag and the table attributes and heading. Also add pink background color to all the artists names for later processing together with price.",
            "@specs": {
                "html": [{
                    "body": [{
                        "h2": [{
                            "@type": "string",
                            "@value": "My CD Collection"
                        }],
                        "table": [{
                            "@attributes": [{
                                "border": [{
                                    "@type": "number",
                                    "@value": "1"
                                }]
                            }],
                            "@0:tr": [{
                                "@attributes": [{
                                    "bgcolor": [{
                                        "@type": "string",
                                        "@value": "#9acd32"
                                    }]
                                }],
                                "@0:th": [{
                                    "@type": "string",
                                    "@value": "Title"
                                }],
                                "@1:th": [{
                                    "@type": "string",
                                    "@value": "Artist"
                                }]
                            }],
                            "@var:rest-of-table-rows": [{
                                "@1:td": [{
                                    "@attributes": [{
                                        "bgcolor": [{
                                            "@type": "string",
                                            "@value": "#ff00ff"
                                        }]
                                    }]
                                }]
                            }]
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "remove-values",
            "@comment": "Remove pink bgcolor if price data cell present and remove the table data cell with price.",
            "@specs": {
                "html": [{
                    "body": [{
                        "table": [{
                            "@var:table-row": [{
                                "@1:td": [{
                                    "@attributes": [{
                                        "bgcolor": [{
                                            "@predicate": ["@func:not(@func:element-exists(html.body.table.@var:table-row.@@2:td))"]
                                        }]
                                    }]
                                }],
                                "@2:td": []
                            }]
                        }]
                    }]
                }]
            }
        },
    ]
}
```

> Ideas:
>
> remove operation for not used values and also predicate removing price if it is less or equal to 10
> shift operation for basic html structure and table rows with 'bgcolor' attribute with @value (but without @type)for object with price
> default operation for the 'h2' tag and adition of @type to attribute bgcolor
>
> I think we need some way to get the number from the combined key of xml array
>
> We NEED to use different symbol than '@' for transformations.
> there are three @ after each other on purpouse. the first two are escaped symbol of '@' going to the outout and the third one is functional. Looks ugly.
