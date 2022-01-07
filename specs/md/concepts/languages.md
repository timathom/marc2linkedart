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

4.  If the language code extracted from `008[35-37]` is the same as a code extracted from `041`, deduplicate the language references in the record-level `LinguisticObject`.

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

5.  For top-level resources with a base class of `Set` \(archival records or kits\), language information should be attached to the embedded `HumanMadeObject` resource using the `carries` property.

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

