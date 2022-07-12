---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Language entities

Language entities derived from `008` and `041`.

## Source data

```
---
name: LanguageEntities
sampleBibs:
  - 97
  - 3779671
# Source data fields
fieldSpec:
  - 008[35-37]
  - 041abdefghijkmnpqrt
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

`008[35-37]` and `041` contain three-letter codes representing a language entity.

The `008[35-37]` code represents the primary language of the resource. Additional codes in `041` represent “languages associated with an item when the language code in field 008/35-37 of the record is insufficient to convey full information.”

1.  Generate and store the top-level language resource from `008[35-37]`, identified by an IRI.

    1.  Normalize whitespace to test for null values.

    2.  Match the three-letter code against the Library of Congress's [MARC List for Languages](https://id.loc.gov/vocabulary/languages.html), which is available as a [tab-delimited file](http://id.loc.gov/vocabulary/languages.tsv), and add the corresponding IRI as an `equivalent` reference, as shown below.

    3.  Use the language code as a key to match against and merge with equivalent language entities.

    `97`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/14033b5c-b596-4195-884f-5ac34d2f1174",
      "type": "Language",
      "_label": "Latin",
      "identified_by": [
        {
          "type": "Name",
          "content": "Latin"
        },
        {
          "type": "Identifier",
          "content": "lat"
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/vocabulary/languages/lat",
          "type": "Language"
        }
      ]
    }
    ```

2.  Generate and store the top-level language resource from `041`, identified by an IRI.

    1.  For each `041` subfield, extract the language code.

        In some cases, `041` language codes may be run together \(e.g., `lateng`\).

    2.  Analyze each `041` subfield value using the regular expression `.{3}` in order to split combined codes.

    3.  Normalize whitespace.

    4.  Match the three-letter code against the Library of Congress's [MARC List for Languages](https://id.loc.gov/vocabulary/languages.html), available as a [tab-delimited file](http://id.loc.gov/vocabulary/languages.tsv), and add the corresponding IRI as an `equivalent` reference, as shown below.

    5.  Use the language code as a key to match against and merge with equivalent language entities.

    `97`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/14033b5c-b596-4195-884f-5ac34d2f1174",
      "type": "Language",
      "_label": "Latin",
      "identified_by": [
        {
          "type": "Name",
          "content": "Latin"
        },
        {
          "type": "Identifier",
          "content": "lat"
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/vocabulary/languages/lat",
          "type": "Language"
        }
      ]
    }
    ```

3.  Add an embedded reference to the language entity or entities within the record-level `LinguisticObject` resource.

4.  If the language code extracted from `008[35-37]` is the same as a code extracted from `041`, deduplicate the language references in the record-level resource.

    `97`

    ```
    {
      "language": [
        {
          "id": "https://lux.collections.yale.edu/data/concept/14033b5c-b596-4195-884f-5ac34d2f1174",
          "type": "Language",
          "_label": "Latin"
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/33d2e19a-72bc-4042-8d06-04dbbf3907b3",
          "type": "Language",
          "_label": "English"
        }
      ]
    }
    ```

5.  For record-level resources with a base class of `LinguisticObject`, language information should be attached directly to the `LinguisticObject` resource.

6.  For record-level resources with a base class of `VisualItem` \(e.g., [Posters](../tasks/supertypes/posters.md) or [Prints](../tasks/supertypes/prints.md)\) that have associated language information, that information should be attached to the related `HumanMadeObject` or `DigitalObject` using the `carries` \(`HumanMadeObject`\) or `digitally_carries` \(`DigitalObject`\) property.

    `11221175`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://linked-art.library.yale.edu/node/7bcc5231-a43f-46b4-9529-0044b5235b7b",
      "type": "HumanMadeObject",
      "_label": "Jim Brown goes over the wall to flash with a million $ stash [graphic]. : the Slams",
      "identified_by": [
        {
          "type": "Identifier",
          "content": "ils:yul:mfhd:11380011",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435704",
              "type": "Type",
              "_label": "System-Assigned Number"
            }
          ],
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "carried_out_by": [
                {
                  "id": "https://linked-art.library.yale.edu/node/0ed3ecaa-4483-4e4e-a015-a6d5ca448106",
                  "type": "Group",
                  "_label": "Yale University Library"
                }
              ]
            }
          ]
        },
        {
          "type": "Identifier",
          "content": "BrSides Double Folio 2013 17",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        }
      ],
      "member_of": [
        {
          "id": "https://linked-art.library.yale.edu/node/beinecke-library",
          "type": "Set",
          "_label": "Beinecke Library"
        }
      ],
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
      ],
      "shows": [
        {
          "id": "https://linked-art.library.yale.edu/node/70cab091-3bea-4a06-b9d6-273d3cf03aba",
          "type": "VisualItem",
          "_label": "Jim Brown goes over the wall to flash with a million $ stash [graphic]. : the Slams"
        }
      ],
      "carries": [
        {
          "type": "LinguisticObject",
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/33d2e19a-72bc-4042-8d06-04dbbf3907b3",
              "type": "Language",
              "_label": "English"
            }
          ]
        }
      ]
    }
    ```

7.  For top-level resources with a base class of `Set` \(archival records or kits\), language information should be attached to the embedded `HumanMadeObject` resource using the `carries` property.

    `3779671`

    ```
    {
      "members_exemplified_by": [
        {
          "type": "HumanMadeObject",
          "_label": "شجون المسجون وفتون المفتون / 1863",
          "carries": [
            {
              "type": "LinguisticObject",
              "language": [
                {
                  "id": "https://lux.collections.yale.edu/data/concept/2b8c1ef3-fb14-4306-9d7c-d5b198acc3f8",
                  "type": "Language",
                  "_label": "Arabic"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Concepts](../concepts/concepts.md)

