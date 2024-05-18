# Example #9 - XSLT-like transformation

Testing:

- XML to XML
  
- Testing how transformation language handles standard XSLT transformation.

>Query: "Transform to html table with title and artist and give pink background to cd's with a price greater than 10."

Input:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<catalog>
  <cd>
    <title>Empire Burlesque</title>
    <artist>Bob Dylan</artist>
    <country>USA</country>
    <company>Columbia</company>
    <price>10.90</price>
    <year>1985</year>
  </cd>
  <cd>
    <title>Hide your heart</title>
    <artist>Bonnie Tyler</artist>
    <country>UK</country>
    <company>CBS Records</company>
    <price>9.90</price>
    <year>1988</year>
  </cd>
  <cd>
    <title>Greatest Hits</title>
    <artist>Dolly Parton</artist>
    <country>USA</country>
    <company>RCA</company>
    <price>9.90</price>
    <year>1982</year>
  </cd>
  <cd>
    <title>Still got the blues</title>
    <artist>Gary Moore</artist>
    <country>UK</country>
    <company>Virgin records</company>
    <price>10.20</price>
    <year>1990</year>
  </cd>
  <cd>
    <title>Eros</title>
    <artist>Eros Ramazzotti</artist>
    <country>EU</country>
    <company>BMG</company>
    <price>9.90</price>
    <year>1997</year>
  </cd>
  <cd>
    <title>One night only</title>
    <artist>Bee Gees</artist>
    <country>UK</country>
    <company>Polydor</company>
    <price>10.90</price>
    <year>1998</year>
  </cd>
  <cd>
    <title>Sylvias Mother</title>
    <artist>Dr.Hook</artist>
    <country>UK</country>
    <company>CBS</company>
    <price>8.10</price>
    <year>1973</year>
  </cd>
  <cd>
    <title>Maggie May</title>
    <artist>Rod Stewart</artist>
    <country>UK</country>
    <company>Pickwick</company>
    <price>8.50</price>
    <year>1990</year>
  </cd>
  <cd>
    <title>Romanza</title>
    <artist>Andrea Bocelli</artist>
    <country>EU</country>
    <company>Polydor</company>
    <price>10.80</price>
    <year>1996</year>
  </cd>
</catalog>
```

Input in UR:

```json
{
  "catalog": [
    {
      "@type": [
        "object"
      ],
      "@0:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Empire Burlesque"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Bob Dylan"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "USA"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Columbia"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "10.90"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1985"
              ]
            }
          ]
        }
      ],
      "@1:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Hide your heart"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Bonnie Tyler"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "UK"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "CBS Records"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "9.90"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1988"
              ]
            }
          ]
        }
      ],
      "@2:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Greatest Hits"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Dolly Parton"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "USA"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "RCA"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "9.90"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1982"
              ]
            }
          ]
        }
      ],
      "@3:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Still got the blues"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Gary Moore"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "UK"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Virgin records"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "10.20"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1990"
              ]
            }
          ]
        }
      ],
      "@4:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Eros"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Eros Ramazzotti"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "EU"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "BMG"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "9.90"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1997"
              ]
            }
          ]
        }
      ],
      "@5:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "One night only"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Bee Gees"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "UK"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Polydor"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "10.90"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1998"
              ]
            }
          ]
        }
      ],
      "@6:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Sylvias Mother"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Dr.Hook"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "UK"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "CBS"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "8.10"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1973"
              ]
            }
          ]
        }
      ],
      "@7:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Maggie May"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Rod Stewart"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "UK"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Pickwick"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "8.50"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1990"
              ]
            }
          ]
        }
      ],
      "@8:cd": [
        {
          "@type": [
            "object"
          ],
          "title": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Romanza"
              ]
            }
          ],
          "artist": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Andrea Bocelli"
              ]
            }
          ],
          "country": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "EU"
              ]
            }
          ],
          "company": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "Polydor"
              ]
            }
          ],
          "price": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "10.80"
              ]
            }
          ],
          "year": [
            {
              "@type": [
                "number"
              ],
              "@value": [
                "1996"
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
  "html": [
    {
      "@type": [
        "object"
      ],
      "body": [
        {
          "@type": [
            "object"
          ],
          "h2": [
            {
              "@type": [
                "string"
              ],
              "@value": [
                "My CD Collection"
              ]
            }
          ],
          "table": [
            {
              "@attributes": [
                {
                  "border": [
                    {
                      "@type": [
                        "number"
                      ],
                      "@value": [
                        "1"
                      ]
                    }
                  ]
                }
              ],
              "@type": [
                "object"
              ],
              "@0:tr": [
                {
                  "@attributes": [
                    {
                      "bgcolor": [
                        {
                          "@type": [
                            "string"
                          ],
                          "@value": [
                            "#9acd32"
                          ]
                        }
                      ]
                    }
                  ],
                  "@type": [
                    "object"
                  ],
                  "@0:th": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Title"
                      ]
                    }
                  ],
                  "@1:th": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Artist"
                      ]
                    }
                  ]
                }
              ],
              "@1:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Empire Burlesque"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@attributes": [
                        {
                          "bgcolor": [
                            {
                              "@type": [
                                "string"
                              ],
                              "@value": [
                                "#ff00ff"
                              ]
                            }
                          ]
                        }
                      ],
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Bob Dylan"
                      ]
                    }
                  ]
                }
              ],
              "@2:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Hide your heart"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Bonnie Tyler"
                      ]
                    }
                  ]
                }
              ],
              "@3:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Greatest Hits"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Dolly Parton"
                      ]
                    }
                  ]
                }
              ],
              "@4:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Still got the blues"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@attributes": [
                        {
                          "bgcolor": [
                            {
                              "@type": [
                                "string"
                              ],
                              "@value": [
                                "#ff00ff"
                              ]
                            }
                          ]
                        }
                      ],
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Gary Moore"
                      ]
                    }
                  ]
                }
              ],
              "@5:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Eros"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Eros Ramazzotti"
                      ]
                    }
                  ]
                }
              ],
              "@6:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "One night only"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@attributes": [
                        {
                          "bgcolor": [
                            {
                              "@type": [
                                "string"
                              ],
                              "@value": [
                                "#ff00ff"
                              ]
                            }
                          ]
                        }
                      ],
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Bee Gees"
                      ]
                    }
                  ]
                }
              ],
              "@7:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Sylvias Mother"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Dr.Hook"
                      ]
                    }
                  ]
                }
              ],
              "@8:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Maggie May"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Rod Stewart"
                      ]
                    }
                  ]
                }
              ],
              "@9:tr": [
                {
                  "@type": [
                    "object"
                  ],
                  "@0:td": [
                    {
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Romanza"
                      ]
                    }
                  ],
                  "@1:td": [
                    {
                      "@attributes": [
                        {
                          "bgcolor": [
                            {
                              "@type": [
                                "string"
                              ],
                              "@value": [
                                "#ff00ff"
                              ]
                            }
                          ]
                        }
                      ],
                      "@type": [
                        "string"
                      ],
                      "@value": [
                        "Andrea Bocelli"
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
  ]
}
```

Output:

```xml
<html>
   <body>
      <h2>My CD Collection</h2>
      <table border="1">
         <tr bgcolor="#9acd32">
            <th>Title</th>
            <th>Artist</th>
         </tr>
         <tr>
            <td>Empire Burlesque</td>
            <td bgcolor="#ff00ff">Bob Dylan</td>
         </tr>
         <tr>
            <td>Hide your heart</td>
            <td>Bonnie Tyler</td>
         </tr>
         <tr>
            <td>Greatest Hits</td>
            <td>Dolly Parton</td>
         </tr>
         <tr>
            <td>Still got the blues</td>
            <td bgcolor="#ff00ff">Gary Moore</td>
         </tr>
         <tr>
            <td>Eros</td>
            <td>Eros Ramazzotti</td>
         </tr>
         <tr>
            <td>One night only</td>
            <td bgcolor="#ff00ff">Bee Gees</td>
         </tr>
         <tr>
            <td>Sylvias Mother</td>
            <td>Dr.Hook</td>
         </tr>
         <tr>
            <td>Maggie May</td>
            <td>Rod Stewart</td>
         </tr>
         <tr>
            <td>Romanza</td>
            <td bgcolor="#ff00ff">Andrea Bocelli</td>
         </tr>
      </table>
   </body>
</html>
```

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
