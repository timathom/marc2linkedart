---
author: timothy.thompson@yale.edu
---

# Top-level Group entities

Group entities extracted from both subject \(6XX\) and agent \(11X and 71X\) fields.

## Source data

```
---
name: GroupEntities
sampleBibs:
  - 7 # 710
  - 9 # 710
  - 11 # 110
  - 19 # 111
  - 38 # 110
  - 68 # 610
  - 127 # 111
  - 162 # 610
  - 422 # 693
  - 426 # 711
  - 607 # 611
  - 947 # 711
  - 1029 # 611  
  - 9292 # 693
  - 614880 # 694
  - 838469 # 694
# Source data fields
fieldSpec:
  - 11001abcdg
  - 11101cdgjnqu
  - 61001abcdgvxyz
  - 61101acdegnquvxyz
  - 69301abcdgvxyz
  - 69401acdegnquvxyz
  - 71001abcdg
  - 71101acdegnquvxyz       
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Generate and store the top-level person resources, each identified by an IRI.

    1.  Join all subfields except for those listed below to create a key for matching and merging.

        |Fields|Subfields|
        |------|---------|
        |All|04|
        |All except 111, 611, 711|e|
        |111, 611, 711|j|

    2.  Normalize and match string values.

    3.  If a source data field in MARC includes a subfield`0`or`1`with an IRI, output an`equivalent`reference.

    `7`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/group/ffd90912-408f-4416-a5b8-b66dde22a224",
      "type": "Group",
      "_label": "University of Virginia",
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
          "content": "University of Virginia"
        }
      ],
      "equivalent": [
        {
          "id": "http://id.loc.gov/authorities/names/n79053979",
          "type": "Group",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300025948",
              "type": "Type",
              "_label": "Organization"
            }
          ]
        }  
      ]
    }
    ```


-   **[Groups as agents](../concepts/groups_as_agents.md)**  
Entities extracted from MARC 11X and 71X fields.
-   **[Groups as subjects](../concepts/groups_as_subjects.md)**  
Entities extracted from MARC 61X fields.

**Parent topic:**[Groups](../concepts/groups.md)

