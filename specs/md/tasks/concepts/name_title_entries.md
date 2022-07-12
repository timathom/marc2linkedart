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
---
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
            1.  Join the `1XX` subfields with a whitespace character. This is the `agent_value`.
            2.  Join the `240` subfields with a whitespace character. This is the `work_value`.
        **Note:** `1XX` fields followed by a `240` should be processed twice: once in an activity on the record-level resource \(bib\) and once in an activity on the complex work resource.

        -   When a `600`, `610`, `611`, `692`, `693`, `694`, `700`, `710`, `711`, `800`, `810`, or `811` field contains subfield `t`:
            1.  Join the `6XX`, `7XX`, or `8XX` subfields *before* subfield `t` with a whitespace character. This is the `agent_value`.
            2.  Join the `6XX`, `7XX`, or `8XX` subfields *beginning with and following* subfield `t` with a whitespace character. This is the `work_value`
        **Note:** Agents in fields with subfield `t` should be processed only in an activity on the complex work resource.

        Apply the following mapping table:

        |Linked Art class|MARC tags|Subfields|
        |----------------|---------|---------|
        |Person|100, 692, 700, 800|abcdgjqu|
        |Group|110, 693, 710, 810|abcdgu|
        |Group|111. 694, 711, 811|acdegnqu|
        |LinguisticObject|240|adfghklmnoprs|
        |LinguisticObject|600, 610, 611, 692, 693, 694, 700, 710, 711, 800, 810, 811|fhklmnoprst|

    3.  Save the `agent_value` and `work_value`.

2.  Create a key for matching and merging.

    1.  Concatenate the `agent_value` and `work_value` with a whitespace character.

    2.  [Normalize](../../glossary/normalization.md) and match the concatenated value against the entity store.

3.  Construct the top-level work entity.

    1.  If a field includes a `$0` with an IRI, output an `equivalent` reference.

        **Note:** The `Type` of the `equivalent` reference should match the `Type` of the top-level resource \(i.e., `LinguisticObject`\).

    2.  Trim punctuation from the `work_value`.

    3.  Output the `work_value` as the value of the `_label` property and as the `Primary Name`.

    4.  Output the `agent_value` using the `created_by → carried_out_by` pattern.

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

4.  If role information is present in subfield `e` of `4`, add the role classifications to the top-level work entities, as specified in [Roles](roles.md).

    **Note:** For `1XX` fields, role classifications should be added to activities in the both the record-level resource \(bib\) and the top-level work resource. For fields with subfield `t`, role classifications should be added only to activities in the top-level work resource.

    `522895` `700 0 $a Porphyry, $d approximately 234-approximately 305. $4 aut $t De abstinentia. $l Latin and Greek.`

    `522895`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://linked-art-test.library.yale.edu/node/9a9022e5-8b80-4fee-b0af-5bbafbaecafa",
      "type": "LinguisticObject",
      "_label": "Pythagorou bios. Latin and Greek.",
      "part_of": [
        {
          "id": "https://linked-art-test.library.yale.edu/node/67a69a9f-a11c-4a37-a888-fccc68387231",
          "type": "LinguisticObject",
          "_label": "Epicteti Stoici philosophi Enchiridion, unà cum Cebetis Thebani Tabula. Accessêre Arriani commentariorum de Epicteti disputationibus lib. IV. Omnia Hieron. Wolfio interprete, cum ejusdem annotationibus. Item Porphyrii philosophi Pythagorici De abstinentia ab animalibus necandis libri quatuor, ex nova versione; cui sujiciuntur notæ breviusculæ. Ejusdem liber De vita Pythagoræ: & Sententiæ ad intelligibilia ducentes: De antro nympharum quod in Odyssea describitur. Lucas Holstenius Hamburgens. Latinè vertit. Dissertationem de vita & scriptis Porphyrii, & ad vitam Pythagoræ observationes adjecit. Cum indicibus in Arrianum & Porphyrium locupletissimis"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Pythagorou bios. Latin and Greek.",
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
                "id": "https://linked-art-test.library.yale.edu/node/f5ef7668-7acf-47ef-9f24-92e9eb4c922e",
                "type": "Person",
                "_label": "Porphyry, approximately 234-approximately 305"
              }
            ],
            "classified_as": [
              {
                "id": "https://linked-art-test.library.yale.edu/node/author-role-entity",
                "type": "Type",
                "_label": "Author"
              }
            ]
          }
        ]
      }
    }
    ```

5.  If not role information \(subfield `e` or `4`\) is present, then use a default role of `Creator`, as shown in the examples.

6.  In each referring record-level resource \(`LinguisticObject`, `Set`, `VisualItem`\), add an embedded reference to the related entity.

    1.  For entities derived from the `240`, `7XX`, or `8XX` fields, add a reference using the `part_of` property: see [Works in whole/part relationships](../name-title/works_as_whole_part.md).

    2.  For entities derived from `6XX` fields, see [Works as subjects](../name-title/works_as_subjects.md) and [Complex works as complex subjects](../name-title/name-title-with-subdivisions.md).


**Parent topic:**[Works](../../concepts/works.md)

