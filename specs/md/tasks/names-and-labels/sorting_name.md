---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Sorting name

Sorting title of a record-level entity. Taken from MARC`245`with initial articles removed.

|Domains|Usage|
|-------|-----|
|`LinguisticObject` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`VisualItem` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: SortingName
sampleBibs:
  - 3
  - 9447
fieldSpec:
  - 245abfghknps
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Determine the number of nonfiling characters from the MARC `245` second indicator value.

    -   If the second indicator is missing/corrupt or not castable as an integer, set the value to `0`.
    -   Else, extract the value of `245` second indicator as an integer.
    1.  If the value of `245` second indicator is `0`, do not generate a sorting name.

    2.  Else, using the string value of the main title, take the substring using the number of nonfiling characters extracted from `245` second indicator as offset and save the value as `sorting_name`.

2.  Assign the `sorting_name` value to the [content-level record](../../glossary/content_level_record.md).

    `1219943`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/49a9dae9-0692-4957-9870-8c49fdf3f064",
      "type": "LinguisticObject",
      "_label": "A raisin in the sun",
      "classified_as": [    
        {
          "id": "https://lux.collections.yale.edu/data/concept/77f2f78b-f595-4e8a-8165-5d6cd114d202",
          "type": "Type",
          "_label": "PS3515.A515"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "A raisin in the sun",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "raisin in the sun",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:1219943",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
      ]
    }
    ```

3.  Assign the `sorting_name` value to each [carrier-level record](../../glossary/carrier_level_record.md).

    `14358 [item]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/49a9dae9-0692-4957-9870-8c49fdf3f064-object",
      "type": "HumanMadeObject",
      "_label": "A raisin in the sun",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Books",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Object"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "A raisin in the sun",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "raisin in the sun",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:16729",
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ],
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ]
        }
      ],
      "number_of_parts": 1,
      "member_of": [
        {
          "id": "https://lux.collections.yale.edu/data/set/collection1b",
          "type": "Set",
          "_label": "Beinecke Library"
        }
      ],
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/49a9dae9-0692-4957-9870-8c49fdf3f064",
          "type": "LinguisticObject",
          "_label": "A raisin in the sun"
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

