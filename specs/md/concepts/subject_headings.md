---
author: [tt434, tt434, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Subject headings

Resources extracted from MARC 6XX entries.

## Source data

```
---
name: SubjectHeadings
sampleBibs:
  - 9564880
  - 13146411
fieldSpec:
  - 60004abcdegjqvxyz
  - 61004abcdegvxyz
  - 61104acdegjnquvxyz
  - 6300adfhklmnoprstvxyz
  - 65004abcdegvxyz
  - 65104abcdfghvxyz
  - 65504abcvxyz
  - 69004abcdegvxyz
  - 69104abcdfgh
  - 69204abcdegjq
  - 69304abcdeg
  - 69404acdegjnqu
  - 6950adfhklmnoprst
  - 75104abcdfgh
  - 75204abcdfghvxyz
trimPunctuation: true
```

1.  Generate and store the top-level concept resources, identified by an IRI.

2.  Create top-level concepts by normalizing and merging the string value of each complete subject heading \(6XX field plus all subfields\).

    |JSON structure|Description|
    |--------------|-----------|
    |`root → id`|Concept IRI|
    |`root → type`|Semantic type of concept. Default value: `Type`|
    |`root → _label`|Label of precoordinated subject heading, joined with double hyphens|
    |`root → equivalent → id`|Reference to IRI from `$0`, if applicable|
    |`root → equivalent → type`|Reference to resource type from `$0`, if applicable|
    |`root → identified_by → content`|Same as `root → _label`|
    |`root → created_by → influenced_by → id`|Concept IRI for facet concept|
    |`root → created_by → influenced_by → type`|Semantic type of concept facet. See the [facet type mapping](subject_headings.md#facet_types_table) below.|
    |`root → created_by → influenced_by → _label`|Facet label|

3.  Within the top-level resource for the full subject heading, model each subdivision in the heading as a facet.

4.  Generate a top-level resource for each unique facet.

    1.  Create facets by normalizing and merging the string value \(label\) of each facet resource according to the facet value mapping table below.

    2.  For each entry, join the subfields with a whitespace character.

        |MARC tag|Subfields|
        |--------|---------|
        |6XX|v|
        |6XX|x|
        |6XX|y|
        |6XX|z|
        |600|abcdgjq|
        |610|abcdg|
        |611|acdegnqu|
        |630|adfhklmnoprst|
        |650|abcdg|
        |651|abcdfgh|
        |690|abcdg|
        |691|abcdfgh|
        |692|abcdgjq|
        |693|abcdg|
        |694|acdgnqu|
        |695|adfhklmnoprst|

    3.  Determine the `type` value for each facet from the tag and subfield values in MARC according to the facet type mapping table below.

        |MARC values|Type|
        |-----------|----|
        |6XXvx|Type|
        |6XXy|Period|
        |6XXz|Place|
        |600abcdgjq|Person|
        |610abcdg|Group|
        |611acdegnqu|Group|
        |630adfhklmnoprst|LinguisticObject|
        |650abcdg|Type|
        |651abcdfgh|Place|
        |690abcdg|Type|
        |691abcdfgh|Place|
        |692abcdgjq|Person|
        |693abcdg|Group|
        |694acdegnqu|Group|
        |695adfhklmnoprst|LinguisticObject|

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
      "type": "Period",
      "_label": "2nd century",
      "identified_by": [
        {
          "type": "Name",
          "content": "2nd century"
        }
      ]
    }
    ```

5.  Join the string values of the facets with double hyphens \(`--`\) to output the `_label` and `content` values of the full precoordinated heading.

6.  Add an embedded reference to the facet resources within the top-level resource for the full heading.

    `9564880`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
      "type": "Type",
      "_label": "Death--Religious aspects--Christianity--History--2nd century",
      "identified_by": [
        {
          "type": "Name",
          "content": "Death--Religious aspects--Christianity--History--2nd century"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/concept/c54ba0ac-c106-4afe-8007-cb4a34cf0bd7",
            "type": "Type",
            "_label": "Death"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/b273c64d-a9bb-4c2e-bb3f-5c13a6825a55",
            "type": "Type",
            "_label": "Religious aspects"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/33a05e84-57bc-4f1d-a792-0de7758bd0d8",
            "type": "Type",
            "_label": "Christianity"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
            "type": "Type",
            "_label": "History"
          },
          {
            "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
            "type": "Period",
            "_label": "2nd century"
          }
        ]
      }
    }
    ```

7.  If a 6XX field in MARC includes a `$0` with an IRI, output an `equivalent` reference.

    `13146411`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/2dba70e6-3702-4bbc-953c-1fdee7460594",
      "type": "Type",
      "_label": "Earth (Planet)--Maps",
      "identified_by": [
        {
          "type": "Name",
          "content": "Earth (Planet)--Maps",
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
          "id": "http://id.loc.gov/authorities/subjects/sh2013000103",
          "type": "Type"
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/place/f0c5212e-e671-4c59-a745-581b350f191d",
            "type": "Place",
            "_label": "Earth (Planet)"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/c5974fce-ed0d-4556-a2f6-bd98965ffc50",
            "type": "Type",
            "_label": "Maps"
          }
        ]
      }
    }
    ```

8.  In each referring record-level resource \(`LinguisticObject`, `VisualItem`, or `DigitalObject`\), add an embedded reference to the Concept entity.

    |JSON structure|Description|
    |--------------|-----------|
    |`root → about → id`|Must match the `id` of the top-level resource|
    |`root → about → type`|Must match the `type` of the top-level resource|
    |`root → about → _label`|Must match the `_label` of the top-level resource|

    `9564880`

    ```
    {
      "about": [
        {
          "id": "https://lux.collections.yale.edu/data/concept/c5ba671b-c41d-40f5-983f-beb38b75b5b2",
          "type": "Type",
          "_label": "Death--Religious aspects--Christianity"
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
          "type": "Type",
          "_label": "Death--Religious aspects--Christianity--History--2nd century"
        }
      ]
    }
    ```


**Previous topic:**[856 \(Electronic Location and Access\)](../tables/856_mfhd_table.md)

