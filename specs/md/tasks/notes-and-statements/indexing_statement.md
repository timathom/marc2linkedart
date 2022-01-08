---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Indexing statement

Cumulative Index/Finding Aids Note

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: IndexingStatement
sampleBibs:
  - 8010777
fieldSpec:
  - 555abc
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the indexing statement values \(MARC `555abc`\).

    -   If two or more subfields \(`555abc`\) are present, join them with a whitespace character.
    -   Else, output the string value of `555a` or `555b`.
    **Note:** This example is meant to illustrate an indexing statement and does not represent a complete JSON-LD document.

    `8010777`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Finding aid available in the archives : folder level control.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300054640",
              "type": "Type",
              "_label": "Indexes Note",
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
              "content": "Cumulative Index/Finding Aids Note",
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

