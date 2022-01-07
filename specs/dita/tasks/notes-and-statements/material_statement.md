---
author: timothy.thompson@yale.edu
---

# Medium of performance

Corresponds to the `382` field in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: MediumOfPerformance
sampleBibs:
  - 655800
fieldSpec:
  - 382ans
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the medium of performance values \(MARC `382ans`\).

    |Subfields|Instructions|
    |---------|------------|
    |**382a**|Output the string value.|
    |**382an**|For each `382an` pair, join the following values with a whitespace character: <br/> 1.  “Number of” <br/> 2.  `382a` <br/> 3.  “performers:” <br/> 4.  `382n` + “.”|
    |**382ans**|For `382s` following one or more `382an` pairs, join the following values to the `382an` value(s) with a whitespace character: <br/> 1.  “Total number of performers:” <br/> 2.  `382s` + “.”|

    **Note:** This example is meant to illustrate a medium of performance statement and does not represent a complete JSON-LD document.

    `655800`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Number of pedal harp performers: 1. Total number of performers: 1.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435429",
              "type": "Type",
              "_label": "Material Statement",
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
              "content": "Medium of Performance Note",
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

