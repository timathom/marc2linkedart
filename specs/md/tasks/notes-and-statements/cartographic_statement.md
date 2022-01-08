---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Cartographic statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: CartographicStatement
sampleBibs:
  - 253435
fieldSpec:
  - 255abc
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the arrangement note values \(MARC `255abc`\).

    -   If two or more subfields \(`255abc`\) are present, join them with a whitespace character.
    -   Else, output the string value of `255a`, `255b`, or `255c`.
    **Note:** This example is meant to illustrate a cartographic statement and does not represent a complete JSON-LD document.

    `253435`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Scale 1:6,652,800. 105 miles to the inch ; Chamberlin trimetric proj. (W 84⁰--W 56⁰/N 12⁰--S 24⁰).",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300053163",
              "type": "Type",
              "_label": "Cartography Note",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Cartographic Mathematical Data",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

