---
author: timothy.thompson@yale.edu
keyword: Assigned
---

# Local note

Corresponds to the`590`Local Note field at YUL.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|

## Source data

```
---
name: LocalNote
sampleBibs:
  - 17
  - 1149734
fieldSpec:
  - 5906ab
  - 8806ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the local note values \(MARC `590ab`\).

    -   If both subfields \(`590ab`\) are present, join them with a whitespace character.
    -   Else, output the string value of `590a`.
    **Note:** These examples are meant to illustrate local notes and do not represent complete JSON-LD documents.

    `17`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/1d4af671-316c-45c4-8a3b-d97354456de2",
      "type": "LinguisticObject",
      "_label": "Witchcraft",
      "classified_as": [  
        {
          "id": "https://lux.collections.yale.edu/data/concept/84784fdc-22f4-42b8-9342-b0ad6329c3a2",
          "type": "Type",
          "_label": "GR530"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Witchcraft",
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
          "content": "Witchcraft",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "BEIN Kosinski 135: Paperbound. From the Katherina von Fraunhofer-Kosinski Collection of Jerzy Kosinski.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300027200",
              "type": "Type",
              "_label": "Note",
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
              "content": "Local Note",
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

