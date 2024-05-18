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
