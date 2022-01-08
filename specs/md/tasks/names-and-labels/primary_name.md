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
|`LinguisticObject` `HumanMadeObject`|Repeat on both JSON-LD documents.|
|`VisualItem` `HumanMadeObject`|Repeat on both JSON-LD documents.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

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

    `9447`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/c0fd4d84-4b50-496d-a56e-ebf952f8dcf2",
      "type": "LinguisticObject",
      "_label": "韓國 의 선비 文化.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Books",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300226816",
              "type": "Type",
              "_label": "Format"
            }
          ]
        }
      ],
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
          "content": "韓國 의 선비 文化.",
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


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

