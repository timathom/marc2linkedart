---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: Assigned
---

# Creators, contributors, standalone works, simple subject/genre headings, and associated places

Related resources that represent a single entity type.

Apply these instructions for source data fields that reference a single entity.

**Note:** `X00`, `X10`, `X11`, and `69X` entries--except for `695`--that include a subfield `t` should not be processed using this spec. See instead [Complex works](name_title_entries.md).

## Source data

```
---
name: SingleEntities
sampleBibs:
  - 3 # 650
  - 7 # 710
  - 9 # 710
  - 11 # 110
  - 19 # 111
  - 38 # 110
  - 68 # 610
  - 127 # 111
  - 162 # 610
  - 227 # 630
  - 422 # 693
  - 426 # 711
  - 607 # 611
  - 693 # 100, 700
  - 947 # 711
  - 1029 # 611
  - 8839 # 611
  - 9292 # 693
  - 4504 # 655
  - 614880 # 694
  - 838469 # 694
  - 907221 # 600
  - 1066178 # 751
  - 6017172 # 651
# Source data fields
fieldSpec:
  - 100014abcdegjqu
  - 110014abcdegu
  - 111014cdegjnqu
  - 130014adfghklmnoprst
  - 600014abcdegjqu
  - 610014abcdegu
  - 611014acdegjnqu
  - 630014adfghklmnoprst
  - 65004abcdeg
  - 651| 0|014ae
  - 655014abc
  - 690014abcdeg
  - 691014ae       
  - 692014abcdegjqu
  - 693014abcdegu
  - 694014acdegjnqu
  - 695014adfhklmnoprst
  - 700014abcdegjqu
  - 710014abcdegu
  - 711014acdegjnqu
  - 730014adfghklmnoprst
  - 751014ae
  - 830014adfghklmnoprst
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

    2.  Apply the following mapping table to create a key for matching and merging. For rows in the table with multiple subfields, join the subfields with a whitespace character.

        **Note:** `X00`, `X10`, `X11`, and `69X` entries--except for `695`--that include a subfield `t` should not be processed using this spec. See instead [Complex works](name_title_entries.md).

        |Linked Art class|MARC tag|Subfields|
        |----------------|--------|---------|
        |Person|X00|abcdgjqu|
        |Group|X10|abcdg|
        |Group|X11|acdegnqu|
        |LinguisticObject|X30|adfhklmnoprst|
        |Concept|650\|\*0\||abcdg|
        |Place|651\|\*0\||a|
        |Type|655|a|
        |Concept|690|abcdg|
        |Place|691|a|
        |Person|692|abcdgjq|
        |Group|693|abcdg|
        |Group|694|acdgnqu|
        |LinguisticObject|695|adfhklmnoprst|
        |Place|751|a|

    3.  [Normalize](../../glossary/normalization.md) and match string values.

    4.  If a field includes a `$0` with an IRI, output an `equivalent` reference.

        **Note:** The `Type` of the `equivalent` reference should match the `Type` of the top-level resource.

    5.  Process top-level concept resources.

        `3`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/concept/522b36c5-57c4-4026-9deb-ff1aeb3ef187",
          "type": "Type",
          "_label": "Paleoecology",
          "identified_by": [
            {
              "type": "Name",
              "content": "Paleoecology",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/subjects/sh85097060",
              "type": "Type"
            }
          ]
        }
        ```

    6.  Process top-level genre/form resources.

        **Note:** Top-level resources representing genre/form headings should include an additional `classified_as` for `Genre` to distinguish them from topical subject headings.

        `4504`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/concept/43427eb8-ebc3-4197-9dfd-9a55ceee894b",
          "type": "Type",
          "_label": "Photoplay editions",
          "classified_as": [
            {
              "id": "http://www.wikidata.org/entity/Q483394",
              "type": "Type",
              "_label": "Genre"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Photoplay editions",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/subjects/sh2002001432",
              "type": "Type"
            }
          ]
        }
        ```

    7.  Process top-level group \(`Organization`\) resources.

        **Note:** Top-level resources representing group entities derived from `X10` fields should include an additional `classified_as` for `Organization` to distinguish them from meeting entities derived from `X11`.

        `68`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/group/a3d54906-5375-46a0-b0df-d6be7d6ecb7f",
          "type": "Group",
          "_label": "United States. National Archives and Records Service",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300025948",
              "type": "Type",
              "_label": "Organization"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "United States. National Archives and Records Service",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/names/n79091762",
              "type": "Group"
            }
          ]
        }
        
        ```

    8.  Process top-level group \(`Meeting`\) resources.

        **Note:** Top-level resources representing group entities derived from `X11` fields should include an additional `classified_as` for `Meeting` to distinguish them from organization entities derived from `X10`.

        `8839`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/group/4583e5ce-fc9d-4e1c-aa61-a822d346dccc",
          "type": "Group",
          "_label": "Congreso de Cúcuta (1821)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300054788",
              "type": "Type",
              "_label": "Meeting"
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Congreso de Cúcuta (1821)",
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

    9.  Process top-level person resources.

        `907221`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/person/25ae094b-ee19-465b-aaf1-2ec08ce28bfd",
          "type": "Person",
          "_label": "Perizonius, Jacobus, 1651-1715",
          "identified_by": [
            {
              "type": "Name",
              "content": "Perizonius, Jacobus, 1651-1715",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/names/n88198532",
              "type": "Person"
            }
          ]
        }
        
        ```

    10. Process top-level place resources.

        `6017172`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/place/ff9095c9-db47-423d-938b-5c2e3fe9e177",
          "type": "Place",
          "_label": "Aleppo (Syria)",
          "identified_by": [
            {
              "type": "Name",
              "content": "Aleppo (Syria)",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/names/n81053997",
              "type": "Place"
            }
          ]
        }
        ```

    11. Process top-level standalone work resources.

        `227`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/text/ea02530e-580f-41a8-92ac-d9e302ec5fbe",
          "type": "LinguisticObject",
          "_label": "Munich Four-Power Agreement (1938)",
          "identified_by": [
            {
              "type": "Name",
              "content": "Munich Four-Power Agreement (1938)",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404670",
                  "type": "Type",
                  "_label": "Primary Name"
                }
              ]
            }
          ],
          "equivalent": [
            {
              "id": "http://id.loc.gov/authorities/names/n50063330",
              "type": "LinguisticObject"
            }
          ]
        }
        ```

2.  In each referring record-level resource \(`LinguisticObject`, `Set`, `VisualItem`\), add an embedded reference to the related entity.

    1.  For concept \(`Type`\) entities, see [Subject and genre/form headings](subject_headings.md).

    2.  For associated places, see [Associated places](../../concepts/associated_places.md).

    3.  For other place entities, see [Places as agents](../../concepts/places_as_agents.md) and [Places as subjects](../../concepts/places_as_subjects.md).

    4.  For person entities, see [People as agents](../../concepts/people_as_agents.md) and [People as subjects](../../concepts/people_as_subjects.md).

    5.  For group entities, see [Groups as agents](../../concepts/groups_as_agents.md) and [Groups as subjects](../../concepts/groups_as_subjects.md).

    6.  For work entities, see [Works as subjects](../name-title/works_as_subjects.md) and [Works in whole/part relationships](../name-title/works_as_whole_part.md).


**Parent topic:**[Related entities](../../tasks/related_entities.md)

