---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: Assigned
---

# Complex works

This specification provides instructions for processing `1XX` entries followed by a `240` field, as well as `X00`, `X10`, `X11`, and `69X` entries--except for `695`--that include a subfield `t`. The type of these entities is `LinguisticObject`. They are considered "complex" because they include an agent \(`Person` or `Group`\) reference followed by a work \(`LinguisticObject`\) reference. The top-level work entity is a `LinguisticObject`, and the agent is included as the creator.

## Source data

```
>---
name: ComplexWorks
sampleBibs:
  - 4 # 100
  - 6 # 100
  - 11 # 710t
  - 42 # 810t
  - 47 # 800t
  - 72 # 600t
  - 98 # 700t
  - 100 # 810t
  - 101 # 700t
  - 145 # 600t
  - 174 # 800t
  - 406 # 710t
  - 997 # 811t
  - 7591 # 111
  - 1091 # 110
  - 1249 # 110
  - 1667 # 610t
  - 2921 # 610t
  - 8012 # 711t
  - 12220 # 811t
  - 15394 # 711t
  - 15844 # 611t
  - 18048 # 111
  - 27598 # 611t
  - 36117 # 692t
  - 44029 # 692t
  - 39783 # 693t
  - 496806 # 693t
fieldSpec:
  - 100014abcdegjqu
  - 110014abcdegu
  - 111014cdegjnqu  
  - 600014abcdefghjklmnopqrstu
  - 610014abcdefghklmnopqrstu
  - 611014acdefghjklmnopqrstu    
  - 692014abcdegjqu
  - 693014abcdegu
  - 694014acdegjnqu  
  - 700014abcdefghjklmnopqrstu
  - 710014abcdefghklmnopqrstu
  - 711014acdefghjklmnopqrstu 
  - 800014abcdefghjklmnopqrstu
  - 810014abcdefghklmnopqrstu
  - 811014acdefghjklmnopqrstu 
  - 24001adfghklmnoprs
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  For each unique source data value, generate and store a top-level resource identified by an IRI.

    1.  Ignore the following subfields when creating a key for matching and merging.

        |Fields|Subfields|
        |------|---------|
        |All|014|
        |All except X11 and 694|e|
        |X11 and 694|j|

    2.  Select the subfields representing the agent and the work.

        -   When a `100`, `110`, or `111` field is followed by a `240` field:
            1.  Join the `1XX` subfields with a whitespace character. This is the `agent value`.
            2.  Join the `240` subfields with a whitespace character. This is the `work value`.
        -   When a `600`, `610`, `611`, `692`, `693`, `694`, `700`, `710`, `711`, `800`, `810`, or `811` field contains subfield `t`:
            1.  Join the `6XX`, `7XX`, or `8XX` subfields *before* subfield `t` with a whitespace character. This is the `agent value`.
            2.  Join the `6XX`, `7XX`, or `8XX` subfields *beginning with and following* subfield `t` with a whitespace character. This is the `work value`
        Apply the following mapping table:

        |Linked Art class|MARC tags|Subfields|
        |----------------|---------|---------|
        |Person|100, 692, 700, 800|abcdgjqu|
        |Group|110, 693, 710, 810|abcdgu|
        |Group|111. 694, 711, 811|acdegnqu|
        |LinguisticObject|240|adfghklmnoprs|
        |LinguisticObject|600, 610, 611, 692, 693, 694, 700, 710, 711, 800, 810, 811|fhklmnoprst|

    3.  Save the `agent value` and `work value`.

2.  Create a key for matching and merging.

    1.  Concatenate the `agent value` and `work value` with a whitespace character.

    2.  [Normalize](../../glossary/normalization.md) and match the concatenated value against the entity store.

3.  Construct the top-level work entity.

    1.  If a field includes a `$0` with an IRI, output an `equivalent` reference.

        **Note:** The `Type` of the `equivalent` reference should match the `Type` of the top-level resource \(i.e., `LinguisticObject`\).

    2.  Output the `work value` as the value of the `_label` property and as the `Primary Name`.

    3.  Output the `agent value` using the `created_by → carried_out_by` pattern.

    `67759`

    ```
    100 1  $a Touré, Ahmed Sékou, $d 1922-
    240 00 $a Afrique en marche. $l English.
    ```

    `72`

    ```
    600 10 $a Goethe, Johann Wolfgang von, $d 1749-1832. $t Faust. $n 1. Theil.
    ```

    `67759`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/text/work1",
      "type": "LinguisticObject",
      "_label": "Afrique en marche. English",
      "identified_by": [
        {
          "type": "Name",
          "content": "Afrique en marche. English",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/person1",
                "type": "Person",
                "_label": "Touré, Ahmed Sékou, 1922-"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                "type": "Type",
                "_label": "Creator"
              }
            ]
          }
        ]
      }
    }
    ```

    `72`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/text/work2",
      "type": "LinguisticObject",
      "_label": "Faust. 1. Theil",
      "identified_by": [
        {
          "type": "Name",
          "content": "Faust. 1. Theil",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/2c1f46a8-74fd-424d-8df6-e57e1852b884",
                "type": "Person",
                "_label": "Goethe, Johann Wolfgang von, 1749-1832"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                "type": "Type",
                "_label": "Creator"
              }
            ]
          }
        ]
      }
    }
    ```


**Parent topic:**[Works](../../concepts/works.md)

