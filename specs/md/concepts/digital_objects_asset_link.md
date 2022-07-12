---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Digital object link to asset

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` of `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: DigitalObjectAsset
sampleBibs:
  - 358058
fieldSpec:  
  - 856|4*|uy
  - mfhd856uyz
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Process `856` links in both bib and MFHD records.

2.  Output a `DigitalObject` link to a related digital asset using the URI recorded in `856u`.

3.  If `856y` is present, add it to the embedded reference using `identified_by`.

    `358058`

    ```
    {
      "subject_of": [
        {
          "type": "LinguisticObject",
          "_label": "Text of Digital Asset Page",
          "digitally_carried_by": [
            {
              "type": "DigitalObject",
              "_label": "Digital Asset Page",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Full text",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300404669",
                      "type": "Type",
                      "_label": "Display Title"
                    }
                  ]
                }
              ],
              "access_point": [
                {
                  "id": "https://example.org/digital-asset1",
                  "type": "DigitalObject"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

4.  If `856z` is present, add it to the embedded reference using `referred_to_by`.

    `13264701 [MFHD]`

    ```
    {
      "subject_of": [
        {
          "type": "LinguisticObject",
          "_label": "Text of Digital Asset Page",
          "digitally_carried_by": [
            {
              "type": "DigitalObject",
              "_label": "Digital Asset Page",
              "referred_to_by": [
                {
                  "type": "LinguisticObject",
                  "content": "Click here for circulation status or to request this volume of George Steevens's collection of Hogarth prints.",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300027200",
                      "type": "Type",
                      "_label": "Note",
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
                      "content": "Note",
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
              ],
              "access_point": [
                {
                  "id": "http://hdl.handle.net/10079/bibid/9559002",
                  "type": "DigitalObject"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

5.  If `856|40|` and the record-level resource is a `DigitalObject`:

    ```
    {
      "access_point": [
        {
          "id": "http://hdl.handle.net/example2",
          "type": "DigitalObject"
        }
      ]
    }
    ```


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

