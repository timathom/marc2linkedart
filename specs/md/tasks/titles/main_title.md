---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Main title

Main title of the record-level resource, from MARC `245` and parallel `880` fields \(if applicable\).

## Source data

```
---
name: MainTitle
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

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → id`|IRI of the record-level entity||
    |`root → type`|Base class of the record-level entity| |
    |`root → _label`|Label of the record-level entity. If the main title has a non-Latin script alternative in a MARC `880` field, that alternative value should be displayed as the label.| |
    |`root → identified_by → [0]`|First item in `identified_by` array should correspond to MARC `245`| |
    |`root → identified_by → [0] → type`| |`Name`|
    |`root → identified_by → [0] → content`|String value of MARC `245` subfields| |
    |`root → identified_by → [0] → classified_as → id`|IRI of the concept used to classify the main title|[http://vocab.getty.edu/aat/300404670](http://vocab.getty.edu/aat/300404670)|
    |`root → identified_by → [0] → classified_as → type`| |`Type`|
    |`root → identified_by → [0] → classified_as → _label`|Label of the concept used to classify the main title|`Primary Name`|
    |`root → identified_by → [1]`|Second item in the `identified_by` array should correspond to MARC `880`, if applicable| |
    |`root → identified_by → [1] → type`| |`Name`|
    |`root → identified_by → [1] → content`|String value of MARC `880` subfields| |
    |`root → identified_by → [1] → classified_as → id`|IRI of the concept used to classify the non-Latin main title|[http://vocab.getty.edu/aat/300404670](http://vocab.getty.edu/aat/300404670)|
    |`root → identified_by → [1] → classified_as → type`| |`Type`|
    |`root → identified_by → [1] → classified_as → _label`|Label of the concept used to classify the non-Latin main title|`Primary Name`|
    |`root → identified_by → [1] → language → id`|IRI of the Language entity for the non-Latin main title|Currently, specific language values are not assigned. A single IRI representing an undefined \(`und`\) language should be assigned for all parallele non-Latin script values.|
    |`root → identified_by → [1] → language → type`| |`Language`|
    |`root → identified_by → [1] → language → _label`| |`und`|

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


**Parent topic:**[Titles](../../concepts/titles.md)

