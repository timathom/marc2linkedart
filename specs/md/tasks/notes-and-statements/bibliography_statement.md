---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Bibliography statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: BibliographyStatement
sampleBibs:
  - 907221
fieldSpec:
  - 504a
trimPunctuation: false
scriptInclusion: BOTH
```

## Processing steps and output

1.  Process the bibliography statement value \(MARC`504a`\).

    **Note:** This example is meant to illustrate a bibliography statement and does not represent a complete JSON-LD document.

    `907221`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Includes bibliographical references (p. [207]-237)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300026497",
              "type": "Type",
              "_label": "Bibliography Statement",
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
              "content": "Bibliography, Etc. Note",
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

