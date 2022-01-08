---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Edition statement

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
  - 250ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the production statement values.

    1.  Do not trim punctuation from subfields.

    2.  Join subfields with a whitespace character.

    **Note:** This example is meant to illustrate a physical statement and does not represent a complete JSON-LD document.

    `3643333`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "1st Knopf ed.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435435",
              "type": "Type",
              "_label": "Edition Statement",
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

