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

Input in UR:

```json
{
  "@type": [
    "object"
  ],
  "person": [
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
      ]
    }
  ],
  "department": [
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
  "all-tel-nums": [
    {
      "@type": [
        "array"
      ],
      "0": [
        {
          "@type": [
            "number"
          ],
          "@value": [
            "444432421"
          ]
        }
      ],
      "1": [
        {
          "@type": [
            "number"
          ],
          "@value": [
            "732444111"
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
      "person": [
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
    "all-tel-nums": [444432421, 732444111],
    "department": {
        "tel": 732444111,
        "person": {
            "tel": 444432421
        }
    }
}
```

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
