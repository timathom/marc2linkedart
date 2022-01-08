---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Places with geographic coordinates

Place entities derived from `MARC 034`.

## Source data

```
---
name: PlacesWithGeo
sampleBibs:
  - 970151 # 008, 034
  - 3906934 # 008, 034
  - 5123661 # 034 with duplicate values
# Source data fields
fieldSpec:
  - 034defg
  - 651a
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

Geographic coordinates should be recorded as points or polygons using the [WKT syntax](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry). MARC 034 subfields representing latitude and longitude are not always clean or consistent, so care should be taken when processing the data. Sometimes, the data will be in decimal form \(e.g., `085.000000`\) and sometimes in *hdddmmss* \(hemisphere-degrees-minutes-seconds\) form.

1.  Processing each `034` field separately and generate a separate top-level place resource for each.

    Sometimes the latitude/longitude coordinates will be repeated in each pair of subfields. First check to see whether the information is repeated or whether there are four different values.

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

4.  Generate a top-level place resource, identified by an IRI, with the value of the WKT coordinates.

    1.  Use the value of the WKT string as a key for matching and merging Place entities with the same coordinates.

5.  The `_label` and `Primary Name` of the place entity should be taken from `650z` or `651a`.

    1.  If `651` is present, take the string value of the **first** `651a` subfield in the MARC bibliographic record.

    2.  Include the string value of additional `651a` subject headings as `Name` objects in the `identified_by` array.

    3.  If a WKT string matches an existing entry, but the labels extracted from `651a` are different, do not change the existing `_label` or `Primary Name`, but add a new `Name` object to the `identified_by` array for the top-level Place entity.

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

    4.  If `651` is not present, but `650z` is present, take the value of the **first** `650z`.

        **Note:** Because `650z` may be subdivided by additional `$z` subfields, all `$z` values should be joined with space-surrounded double hyphens \(`--`\).

    5.  Include additional `650z` values as `Name` objects in the `identified_by` array.

        **Note:** Values should be deduplicated before inclusion.

    6.  If a WKT string matches an existing entry, but the labels extracted from `650z` are different, do not change the existing `_label` or `Primary Name`, but add a new `Name` object to the `identified_by` array for the top-level Place entity.

        `2644090`

        ```
        034 0 $a a $d E1135000 $e E1143000 $f N0224000 $g N0221000
        ```

        ```
        650 0 $a Atmospheric temperature $z China $z Hong Kong $x Observations $v Periodicals.
        ```

        ```
        650 0 $a Humidity $z China $z Hong Kong $x Observations $v Periodicals.
        ```

        `2644090`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/place/place1",
          "type": "Place",
          "_label": "China -- Hong Kong",
          "identified_by": [
            {
              "type": "Name",
              "content": "China -- Hong Kong",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "defined_by": "POLYGON((113.5000 22.4000, 114.3000 22.4000, 114.3000 22.1000, 113.5000 22.1000, 113.5000 22.4000))"
        }
        ```

    7.  If neither `650z` or `651a` are present, skip processing of the `034` coordinates.

6.  Add an embedded reference to the place entity within the record-level resource.

    1.  As the `_label` of the place entity, take the value of the top-level entity label.

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

