---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Places with geographic coordinates

Place entities derived from `MARC 034`.

## Source data

```
---
name: PlacesWithGeographicCoordinatets
sampleBibs:
  - 970151 # 008, 034
  - 3906934 # 008, 034
# Source data fields
fieldSpec:
  - 034defg
  - 651a
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

Geographic coordinates should be recorded as points or polygons using the [WKT syntax](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry). MARC 034 subfields representing latitude and longitude are not always clean or consistent, so care should be taken when processing the data. Sometimes, the data will be in decimal form \(e.g., `085.000000`\) and sometimes in *hdddmmss* \(hemisphere-degrees-minutes-seconds\) form.

1.  Sometimes the latitude/longitude coordinates will be repeated in each pair of subfields. First check to see whether the information is repeated or whether there are four different values.

    If `034d == 034e and 034f == 034g`, select the first nonempty occurrence of 034d and 034f.

    Else, select the first nonempty occurrence of each distinct subfield.

2.  Check the subfield values.

    1.  If the subfield contains a period \(`.`\), assume the value is in decimal form and continue processing.
    2.  Else, parse the data in *hdddmmss* form and convert it to decimal form:

        |Step|Variable|
        |----|--------|
        |Store the first character in the string.|first|
        |Store the rest of the string following `first`.|rest|
        |Store the last four characters of `rest`.|rightHand|
        |Store the substring of `rest` to the left of `rightHand`.|leftHand|
        |Clean the value of `leftHand`: <br/> 1.  Convert the value to lower case. <br/> 2.  Remove leading zeroes or occurrences of the letter *o* \(a typo for zero\).|cleanedLeftHand|
        |Concatenate the value of `cleanedLeftHand` and `rightHand` with a period \(`.`\).|decimalValue|
        |Determine the sign of `decimalValue`. <br/> -   If `first` equals `-`, `W`, or `S`, the sign is negative. <br/> -   Else, it is positive \(unsigned\).|signedDecimalValue|

3.  Construct the WKT string.

    If 034 includes four distinct subfield values, construct a WKT polygon:

    ```
    "POLYGON((" + 034d + " " + 034f + ", " + 034e + " " + 034f + ", " + 034e + " " + 034g + ", " + 034d + " " + 034g + ", " + 034d + " " + 034f + "))"
    ```

    Else, construct a WKT point:

    ```
    "POINT(" + 034d + " " + 034f + ")"
    ```

4.  Generate a top-level Place resource, identified by an IRI, with the value of the WKT coordinates.

    1.  Use the value of the WKT string as a key for matching and merging Place entities with the same coordinates.

    2.  As the `_label` and `Primary Name`of the Place entity, take the string value of the **first** `651a` subject heading in the MARC bibliographic record.

    3.  Include the string value of additional `651a` subject headings as `Name` objects in the `identified_by` array.

    4.  If a WKT string matches an existing entry, but the labels extracted from `651a` are different, do not change the existing `_label` or `Primary Name`, but add a new `Name` object to the `identified_by` array for the top-level Place entity.

    `970151`

    ```
    034 1 $a a $b 50000 $d W0611800 $e W0610600 $f N0132300 $g N0130600
    ```

    ```
    651 0 $a Kingstown (Saint Vincent and the Grenadines) $v Maps.
    ```

    ```
    651 0 $a Saint Vincent $v Maps.
    ```

    `970151`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/place1",
      "type": "Place",
      "_label": "Kingstown (Saint Vincent and the Grenadines)",
      "identified_by": [
        {
          "type": "Name",
          "content": "Kingstown (Saint Vincent and the Grenadines)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Saint Vincent"
        }
      ],
      "defined_by": "POLYGON((-61.1800 13.2300, -61.0600 13.2300, -61.0600 13.0600, -61.1800 13.0600, -61.1800 13.2300))"
    }
    ```

5.  Add an embedded reference to the Place entity within the record-level resource.

    1.  As the `_label` of the Place entity, take the value of the top-level entity `_label`.

    `970151`

    ```
    {
      "represents": [
        {
          "id": "https://lux.collections.yale.edu/data/place/place1",
          "type": "Place"
          "_label": "Kingstown (Saint Vincent and the Grenadines)"
        }
      ]
    }
    ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

