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
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

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

1.  Determine the number of nonfiling characters from the MARC`245`second indicator value.

    -   If the second indicator is missing/corrupt or not castable as an integer, set the value to`0`.
    -   Else, extract the value of`245`second indicator as an integer.
    1.  Using the string value of the main title, take the substring using the number of nonfiling characters extracted from`245`second indicator as offset.

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → identified_by → [2]`|When a parallel non-Latin script`Primary Name`is present, the`Sorting Name`is the third item in the`identified_by`array.| |
    |`root → identified_by → [2] → type`| |`Name`|
    |`root → identified_by → [2] → content`|String value of MARC`245`subfields with the number of nonfiling characters as offset| |
    |`root → identified_by → [2] → classified_as → id`|IRI of the concept used to classify the sorting title|[http://vocab.getty.edu/aat/300404672](http://vocab.getty.edu/aat/300404672)|
    |`root → identified_by → [2] → classified_as → type`| |`Type`|
    |`root → identified_by → [2] → classified_as → _label`|Label of the concept used to classify the main title|`Sorting Name`|

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
        },
        {
          "type": "Name",
          "content": "Hanʼguk ŭi sŏnbi munhwa",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

