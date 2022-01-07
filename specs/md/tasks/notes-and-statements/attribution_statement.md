---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed, Deployed]
---

# Attribution statement

Corresponds to the`245c`statement of responsibility in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

**Note:** The attribution statement is mirrored in parallel non-Latin script values, when present.

## Source data

```
---
name: AttributionStatement
sampleBibs:
  - 7778409
fieldSpec:
  - 2456c
  - 8806c
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Process the attribution statement values \(MARC`245c`and parallel`880c`, if applicable\).

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → referred_to_by → [0] → type`| |`LinguisticObject`|
    |`root → referred_to_by → [0] → content`|String value of MARC`245c`subfield| |
    |`root → referred_to_by → [0] → classified_as → [0] → id`|IRI of the concept used to classify the statement|[http://vocab.getty.edu/aat/300056109](http://vocab.getty.edu/aat/300056109)|
    |`root → referred_to_by → [0] → classified_as → [0] → type`| |`Type`|
    |`root → referred_to_by → [0] → classified_as → [0] → _label`|Label of the concept used to classify the statement|`Attribution Statement`|
    |`root → referred_to_by → [0] → classified_as → [0] → classified_as → id`|IRI of the concept used to classify the kind of statement|[http://vocab.getty.edu/aat/300418049](http://vocab.getty.edu/aat/300418049)|
    |`root → referred_to_by → [0] → classified_as → [0] → classified_as → type`| |`Type`|
    |`root → referred_to_by → [0] → classified_as → [0] → classified_as → _label`| |`Brief Text`|
    |`root → referred_to_by → [0] → classified_as → [1] → id`|IRI of the concept used to classify the statement|[http://vocab.getty.edu/aat/300404333](http://vocab.getty.edu/aat/300404333)|
    |`root → referred_to_by → [0] → classified_as → [1] → type`| |`Type`|
    |`root → referred_to_by → [0] → classified_as → [0] → _label`|Label of the concept used to classify the statement|`Transcribed`|
    |`root → referred_to_by → [1]`|Following item in the`referred_to_by`array should correspond to MARC`880`, if applicable|[http://vocab.getty.edu/aat/300418049](http://vocab.getty.edu/aat/300418049)|
    |`root → referred_to_by → [1] → language → id`|IRI of the Language entity for the non-Latin statement|Currently, specific language values are not assigned. A single IRI representing an undefined \(`und`\) language should be assigned for all parallel non-Latin script values.|
    |`root → referred_to_by → [1] → language → type`| |`Language`|
    |`root → referred_to_by → [1] → language → _label`| |`und`|

    **Note:** This example is meant to illustrate the attribution statement and does not represent a complete JSON-LD document.

    `7778409`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3",
      "type": "LinguisticObject",
      "_label": "麗澤論說集錄 : [十卷]",
      "referred_to_by": [
      {
          "type": "LinguisticObject",
          "content": "[Lü Zuqian zhuan ; Lü Zujian ji]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300056109",
              "type": "Type",
              "_label": "Attribution Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            },
            {
              "id": "http://vocab.getty.edu/aat/300404333",
              "type": "Type",
              "_label": "Transcribed"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Attribution",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        },
        {
          "type": "LinguisticObject",
          "content": "[呂祖謙撰 ; 呂祖儉輯]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300056109",
              "type": "Type",
              "_label": "Attribution Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            },
            {
              "id": "http://vocab.getty.edu/aat/300404333",
              "type": "Type",
              "_label": "Transcribed"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Attribution",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
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


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

