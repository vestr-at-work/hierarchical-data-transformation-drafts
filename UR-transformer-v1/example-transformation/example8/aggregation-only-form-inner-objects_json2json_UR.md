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

Input in UR:

```json
{
  "@type": [
    "object"
  ],
  "contact": [
    {
      "@type": [
        "object"
      ],
      "tel": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "+420 444432421"
          ]
        }
      ]
    }
  ],
  "math-department": [
    {
      "@type": [
        "object"
      ],
      "info": [
        {
          "@type": [
            "object"
          ],
          "contact": [
            {
              "@type": [
                "object"
              ],
              "tel": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "+420 732444111"
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "computer-science-department": [
    {
      "@type": [
        "object"
      ],
      "info": [
        {
          "@type": [
            "object"
          ],
          "contact": [
            {
              "@type": [
                "object"
              ],
              "tel": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "+420 001010111"
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```

Output in UR:

```json
{
  "@type": [
    "object"
  ],
  "lower-level-contacts-count": [
    {
      "@type": [
        "number"
      ],
      "@value": [
        "2"
      ]
    }
  ]
}
```

Output:

```json
{
   "lower-level-contacts-count": 2
}
```

Transformation specification:

```json
{
    "@operations": [
        {
            "@operation": "take-values",
            "@comment": "Take only department tel numbers.",
            "@specs": {
                "@var:department": [{
                    "info": [{
                        "contact": [{
                            "tel": []
                        }]
                    }]
                }]
            }
        },
        {
            "@operation": "count-values",
            "@comment": "Operation count-values counts variable matches and outputs the current number when it encounters @output:count:var:[...] tag.",
            "@specs": {
                "@var:department": [{
                    "info": [{
                        "contact": [{
                            "tel": [{
                                "@count:var:lower-level-contact": []
                            }]
                        }]
                    }]
                }],
                "@output:count:var:lower-level-contact": [{
                    "@tag": ["lower-level-contacts-count"]
                }]
            }
        },
        {
            "@operation": "take-values",
            "@comment": "Now we have to take only the lower-level-contacts-count to the output.",
            "@specs": {
                "lower-level-contacts-count": []
            }
        },
    ]
}
```

> Ideas:
>
> First shift the lower-level-contacts to some new array using two key-variables to ommit the higher-level-contact and then use some new sum operation on the array.
