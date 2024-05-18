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
  "department": [
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
  ]
}
```

Output in UR:

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
            "number"
          ],
          "@value": [
            "444432421"
          ]
        }
      ],
      "preselection": [
        {
          "@type": [
            "string"
          ],
          "@value": [
            "+420"
          ]
        }
      ]
    }
  ],
  "department": [
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
                    "number"
                  ],
                  "@value": [
                    "732444111"
                  ]
                }
              ],
              "preselection": [
                {
                  "@type": [
                    "string"
                  ],
                  "@value": [
                    "+420"
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

> This I would not support tbh. Or we could somehow allow delegates to java functions or something to parse the values, but idk...
