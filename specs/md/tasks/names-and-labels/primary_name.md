---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Primary name

Main title of a record-level entity.

|Domains|Usage|
|-------|-----|
|`LinguisticObject` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`VisualItem` `HumanMadeObject` `DigitalObject`|Repeat on both JSON-LD documents.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

**Note:** The primary name is mirrored in parallel non-Latin script titles, when present.

## Source data

```
---
name: PrimaryName
sampleBibs:
  - 3
  - 9447
fieldSpec:
  - 2456abfghknps
  - 8806abfghknps
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Process the main title values \(MARC `245` and parallel `880`, if applicable\).

    1.  Join the string value of MARC `245` subfields `abfghknps` \(excluding `$6`\) with a whitespace character.

    2.  If applicable, join the string value of parallel MARC `880` subfields `abfghknps` \(excluding `$6`\) with a whitespace character.

    3.  Save the values as `primary_name` or `parallel_primary_name` \(if applicable\).

2.  Assign the `primary_name` and `parallel_primary_name` values to the [content-level record](../../glossary/content_level_record.md).

    `9447`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "LinguisticObject",
      "_label": "韓國 의 선비 文化",
      "identified_by": [
        {
          "type": "Name",
          "content": "Hanʼguk ŭi sŏnbi munhwa",
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
          "content": "韓國 의 선비 文化",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ]
    }
    ```

3.  Assign the `primary_name` and `parallel_primary_name` values to each [carrier-level record](../../glossary/carrier_level_record.md).

    `16729 [MFHD]`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "HumanMadeObject",
      "_label": "韓國 의 선비 文化",
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
        },
        {
          "type": "Identifier",
          "content": "DS904.U66",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Hanʼguk ŭi sŏnbi munhwa",
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
          "content": "韓國 의 선비 文化",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ]
    }
    ```

4.  If the carrier-level record represents a [bound-with resource](../../glossary/bound-with_resource.md), use the call number as the `primary_name` of the carrier-level record.

5.  Concatenate the call number with the following phrase in square brackets using a whitespace character: `[multiple objects bound in a single volume]`.

    `7001117`

    ```
    {
      "identified_by": [
        {
          "type": "Name",
          "content": "Ip Si578 1 [multiple objects bound in a single volume]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

