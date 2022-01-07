---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: []
---

# Repository collections

|Domains|Usage|
|-------|-----|
|`HumanMadeObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`DigitalObject`| |
|`Set → members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: RepositoryCollections
sampleBibs:
  - 6546882
fieldSpec: mfhd852b
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Create a top-level resource for each repository collection.

    At present, only three collections are defined:

    -   Yale University Library
    -   Yale Center for British Art
    -   Yale University Art Gallery
    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/set/collection1",
      "type": "Set",
      "_label": "Yale University Library",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300025976",
          "type": "Type",
          "_label": "Collection"
        }
      ],
      "created_by": {
        "type": "Creation",
        "carried_out_by": [
          {
            "type": "Group",
            "_label": "Yale University Library"
          }
        ]
      },
      "identified_by": [
        {
          "type": "Name",
          "content": "Holdings of Yale University Library"
        }
      ]
    }
    ```

2.  Add an embedded reference to the `Set` within the corresponding object resource.

    1.  Use the Voyager location code lookup table to identify MFHD `852b` codes that match YCBA or YUAG locations.

        This includes any location code that corresponds to the display label “Yale Center for British Art” or “Yale University Art Gallery”.

        ```
        [
          {
            "LOCATION_MAP_FACET": "Yale Center for British Art",
            "ORBIS_LOCATION_CODE": "bacrb"
          },
          {
            "LOCATION_MAP_FACET": "Yale University Art Gallery",
            "ORBIS_LOCATION_CODE": "yuagcm"
          }
        ]
        ```

        ```
        {
          "member_of": [
            {
              "id": "https://lux.collections.yale.edu/data/set/collection2",
              "type": "Set",
              "_label": "Yale Center for British Art"
            }
          ]
        }
        ```

    2.  For all other locations, add a reference to the YUL collection.

        `6546882`

        ```
        {
          "member_of": [
            {
              "id": "https://lux.collections.yale.edu/data/set/collection1",
              "type": "Set",
              "_label": "Yale University Library"
            }
          ]
        }
        ```


**Parent topic:**[Sets](../concepts/related_sets.md)

