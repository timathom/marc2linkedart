---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, ]
---

# People as agents

Entities extracted from MARC 100 and 700 fields.

As agents, people can contribute to creation activities or production activities. The table below summarizes the domains and properties used in activities involving person entities.

**Note:** The role of the person entity is derived from `$e` or `$4`. When those subfields are absent, a generic role of `creator` is assigned when 100 is the source or `contributor` when 700 is the source.

|Domains|Property path|Usage|
|-------|-------------|-----|
|`LinguisticObject` `VisualItem`|`created_by → part → carried_out_by`| |
|`HumanMadeObject → shows → VisualItem`|`produced_by → part → carried_out_by`|Include `produced_by` reference if the `HumanMadeObject` points to a `VisualItem`, but not a `LinguisticObject`.|
|`Set`|`created_by → part → carried_out_by`|Do not include agent references in nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`|`created_by → part → carried_out_by`| |

## Source data

```
---
name: PeopleAsAgents
sampleBibs:
  - 693
  - 907221
  - 7647390 # produced_by
# Source data fields
fieldSpec:
  - 100014abcdegjq
  - 700014abcdegjq
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md), add an embedded reference to the person entity within the record-level resource.

    1.  Process creation activities.

        `907221`

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/72f4b237-12f8-4854-bd96-e1094ee56bb2",
                    "type": "Person",
                    "_label": "Meijer, Th. J."
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

        `7647390`

        ```
        {
          "produced_by": {
            "type": "Production",
            "part": [
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/28a98ded-4a66-4c12-a175-20a3733428fa",
                    "type": "Person",
                    "_label": "Bunbury, Henry William, 1750-1811"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/a18e0571-0842-4f9c-86de-3229e64dc64d",
                    "type": "Person",
                    "_label": "Bartolozzi, Francesco, 1727-1815"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/ec100aa5-11c4-47af-8c42-f21af2cbea27",
                    "type": "Person",
                    "_label": "Benedetti, Michele, 1745-1810"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/644c3ba3-0320-4b41-b59b-d1fc902f5abb",
                    "type": "Person",
                    "_label": "Chapman, J. (John), active 1792-1823"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/514f84c1-8861-48b1-b3e9-5d5f00647c0b",
                    "type": "Person",
                    "_label": "Cheesman, Thomas, 1760-"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/61c133b7-ee19-45ad-a7c6-57216f7f349b",
                    "type": "Person",
                    "_label": "Coles, J."
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/e01c532d-8281-4be2-9911-7896a7c01065",
                    "type": "Person",
                    "_label": "Duterrau, Benjamin, 1767-1851"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/3082e61d-2a84-4cd8-9a85-58091df39bd5",
                    "type": "Person",
                    "_label": "Gardiner, W. N. (William Nelson), 1766-1814"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/8b303da9-5350-43be-9587-df56cd45b75f",
                    "type": "Person",
                    "_label": "Leney, William Satchwell, 1769-1831"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/d33e0bd3-5899-4dca-9b43-41465f08dd51",
                    "type": "Person",
                    "_label": "Macklin, Thomas"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/61128e1b-2b5a-42ef-800d-8777052b3c5a",
                    "type": "Person",
                    "_label": "Meadows, Robert Mitchell"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/5ce84446-6e6a-433b-8364-f1ddfbf75ea1",
                    "type": "Person",
                    "_label": "Shenner"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/12b1555a-9e61-45d3-9a4d-200f15f908e9",
                    "type": "Person",
                    "_label": "Tomkins, Peltro William, 1759-1840"
                  }
                ]
              },
              {
                "type": "Production",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/82efbe04-d078-43a7-8351-b0ef3b8b7bea",
                    "type": "Person",
                    "_label": "Vandenbergh, Ignatius Joseph, 1752-1824"
                  }
                ]
              }
            ]
          }
        }
        ```


**Parent topic:**[People](../concepts/people.md)

