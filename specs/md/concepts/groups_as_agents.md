---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, ]
---

# Groups as agents

Entities extracted from MARC 11X and 71X fields.

As agents, groups can contribute to creation activities or production activities. The table below summarizes the domain and properties used in activities involving group entities.

**Note:** The role of the group entity is derived from `$e` or `$4` for MARC 110 and 710 and from `$j` or `$4` for MARC 111 and 711. When those subfields are absent, a generic role of `creator` is assigned when 11X is the source or `contributor` when 71X is the source.

|Domains|Property path|Usage|
|-------|-------------|-----|
|`LinguisticObject` `VisualItem`|`created_by → part → carried_out_by`| |
|`HumanMadeObject`|`produced_by → part → carried_out_by`| |
|`Set`|`created_by → part → carried_out_by`|Do not include agent references in nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`|`created_by → part → carried_out_by`| |

## Source data

```
---
name: GroupsAsAgents
sampleBibs:
  - 7 # 710
  - 9 # 710
  - 11 # 110
  - 19 # 111
  - 38 # 110
  - 127 # 111
  - 426 # 711
  - 947 # 711
  - 5132502 # produced_by
# Source data fields
fieldSpec:
  - 11001abcdeg
  - 11101acdegjnqu
  - 71001abcdeg
  - 71101acdegjnqu
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md), add an embedded reference to the group entity within the record-level resource.

    1.  Process creation activities.

        `127`

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/group/1bd89c27-47b9-40f0-8023-568af073edbd",
                    "type": "Group",
                    "_label": "International Congress for Logic, Methodology, and Philosophy of Science (3d : 1967 : Amsterdam)"
                  }
                ],
                "classified_as": [
                  {
                    "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                    "type": "Type",
                    "_label": "creator"
                  }
                ]
              }
            ]
          }
        }
        ```

    2.  Process production activities \(domain: `HumanMadeObject → shows → VisualItem`\).

        `5132502`

        ```
        {
          "produced_by": {
            "type": "Production",
            "part": [
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/group/545215f9-7d4a-4d4e-904e-ec6acf6e78da",
                    "type": "Group",
                    "_label": "United States. Bureau of Alcohol, Tobacco, and Firearm"
                  }
                ]
              }
            ]
          }
        }
        ```


**Parent topic:**[Groups](../concepts/groups.md)

