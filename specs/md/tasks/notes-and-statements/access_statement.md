---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Access statement

Statement indicating whether a resource is available online or in the library.

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`Set → members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: AccessStatement
sampleBibs:
  - 3
  - 6546882
fieldSpec:
  - mfhd852b
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  For MFHDs with an `852b` value of `yulint` or `yulintx`, output an access statement with a `content` value of `Online`.

    `6546882`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Online",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
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

2.  For all other MFHD locations, output an access statement with a `content` value of `In the Library`.

    `3`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "In the Library",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
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

