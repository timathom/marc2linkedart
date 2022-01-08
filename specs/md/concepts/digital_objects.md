---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Digital object link to catalog

|Domains|Usage|
|-------|-----|
|`HumanMadeObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: DigitalObjectCatalog
sampleBibs:
  - 358058
fieldSpec:
  - 001
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Output a `DigitalObject` link to the record in QuickSearch using the BIB ID.

    1.  Concatenate the QuickSearch base URI with the BIB ID.

        `“https://search.library.yale.edu/catalog/” + 358058`

    `358058`

    ```
    {
      "subject_of": [
        {
          "type": "LinguisticObject",
          "_label": "Text of Repository Page",
          "digitally_carried_by": [
            {
              "type": "DigitalObject",
              "_label": "Repository Page",
              "access_point": [
                {
                  "id": "https://search.library.yale.edu/catalog/358058",
                  "type": "DigitalObject"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

