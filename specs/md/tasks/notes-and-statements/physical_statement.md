---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Physical statement

|Domains|Usage|
|-------|-----|
|`HumanMadeObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: PhysicalStatement
sampleBibs:
  - 25079
  - 3811379
fieldSpec:
  - 3003acef
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the physical statement values \(MARC `3003acef`\).

    1.  Do not trim punctuation from subfields.

    2.  Join fields `300acef` with a whitespace character.

    3.  If subfield `3` is present, but does not appear first in the subfield sequence, prefix the statement with the value of subfield `3`.

    4.  Test the value of `3` to see whether it ends with a colon.

    5.  If no colon is present, concatenate the value with a colon \(`:`\).

    6.  Else, output the value of subfield `3`.

        ```
        300  $3 Copy 1: $a 1 album (32 photographic prints) : $b b & w ; $c 13.4 x 20.6 cm.
        300  $3 Copy 2: $a 1 album (39 photographic prints) : $b b & w ; $c 13.4 x 20.6 cm.
        ```

        **Note:** This example is meant to illustrate a physical statement and does not represent a complete JSON-LD document.

        `3811379`

        ```
        {
          "referred_to_by": [        
            {
              "type": "LinguisticObject",
              "content": "Copy 1: 1 album (32 photographic prints) ; 13.4 x 20.6 cm",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435452",
                  "type": "Type",
                  "_label": "Physical Statement",
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
                  "content": "Physical Description",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300404669",
                      "type": "Type",
                      "_label": "Display Title"
                    }
                  ]
                }
              ]
            },
            {
              "type": "LinguisticObject",
              "content": "Copy 2: 1 album (39 photographic prints) ; 13.4 x 20.6 cm",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435452",
                  "type": "Type",
                  "_label": "Physical Statement"
                }
              ],
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Physical Description",
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

