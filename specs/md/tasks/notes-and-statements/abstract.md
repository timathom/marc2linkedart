---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Abstract

Corresponds to the`520`note field in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: Abstract
sampleBibs:
  - 18
fieldSpec:
  - 520a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the abstract values \(MARC `520a`\).

    **Note:** This example is meant to illustrate an abstract and does not represent a complete JSON-LD document.

    `18`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "A boy grows to manhood while attempting to subdue the evil he unleashed on the world as an apprentice to the Master Wizard.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300026032",
              "type": "Type",
              "_label": "Abstract",
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
              "content": "Summary, Etc.",
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

