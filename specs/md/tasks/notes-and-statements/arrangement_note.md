---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Arrangement note

Corresponds to the `351` note field in MARC.

|Domains|Usage|
|-------|-----|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: ArrangementNote
sampleBibs:
  - 12656596
fieldSpec:
  - 351ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the arrangement note values \(MARC `351ab`\).

    -   If both subfields `351ab` are present, join them with a whitespace character.
    -   Else, output the string value of `351a` or `351b`.
    **Note:** This example is meant to illustrate an arrangement note and does not represent a complete JSON-LD document.

    `12656596`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Arranged alphabetically.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300444118",
              "type": "Type",
              "_label": "Contents Organization/Arrangement Note",
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
              "content": "Organization and Arrangement of Materials",
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

