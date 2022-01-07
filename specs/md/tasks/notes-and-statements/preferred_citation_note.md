---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Preferred citation note

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: Abstract
sampleBibs:
  - 72947
fieldSpec:
  - 524a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the preferred citation note values \(MARC`524a`\).

    **Note:** This example is meant to illustrate a preferred citation note and does not represent a complete JSON-LD document.

    `72947`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Kamoinge Inc., Kamoinge Workshop Portfolio No. 1. James Weldon Johnson Collection in the Yale Collection of American Literature, Beinecke Rare Book and Manuscript Library.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311705",
              "type": "Type",
              "_label": "Preferred Citation Note",
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
              "content": "Preferred Citation of Described Materials Note",
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

