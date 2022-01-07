---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Biography statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: BiographyStatement
sampleBibs:
  - 72947
fieldSpec:
  - 545ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the acquisition statement values \(MARC`545ab`\).

    1.  If subfield`b`is present, join the string values of`545ab`with a whitespace character.

    2.  Else, output the value of subfield`545a`.

    **Note:** This example is meant to illustrate a biography statement and does not represent a complete JSON-LD document.

    `72947`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Kamoinge Inc. is a collective of African American photographers formed in New York in 1963 to address the under-representation of black photographers in the art world.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435422",
              "type": "Type",
              "_label": "Biography Statement",
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
              "content": "Biographical or Historical Data",
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

