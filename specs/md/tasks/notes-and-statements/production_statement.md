---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Production statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: ProductionStatement
sampleBibs:
  - 3643333
fieldSpec:
  - 260abcefg
  - 264abc
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  For each `26X` field, process the production statement values and generate a `Production Statement` within the `referred_to_by` array.

    1.  Do not trim punctuation from subfields.

    2.  Join subfields with a whitespace character.

    **Note:** This example is meant to illustrate a production statement and does not represent a complete JSON-LD document.

    `3643333`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "New York : Alfred A. Knopf, 1993, c1970",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435436",
              "type": "Type",
              "_label": "Production Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

