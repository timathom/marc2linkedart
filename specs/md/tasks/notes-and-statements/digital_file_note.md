---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Digital file note

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: DigitalFileNote
sampleBibs:
  - 756337
fieldSpec:
  - 516a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the digital file note value \(MARC `516a`\).

    **Note:** This example is meant to illustrate a digital file note and does not represent a complete JSON-LD document.

    `756337`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Dataset in DAT file format.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300266011",
              "type": "Type",
              "_label": "Digital Characteristics Note",
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
              "content": "Type of Computer File or Data Note",
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

