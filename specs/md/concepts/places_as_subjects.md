---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Places as subjects

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md) or [Complex subject/genre headings and hierarchical associated places](../tasks/concepts/complex_subject_headings.md), add an embedded reference to the place entity within the record-level resource.

    1.  As the \_label of the place entity, take the value of the top-level entity label.

    2.  Process simple place references.

        `6017172`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/place/ff9095c9-db47-423d-938b-5c2e3fe9e177",
              "type": "Place",
              "_label": "Aleppo (Syria)"
            }
          ]
        }
        ```

    3.  Process concept/place references.

        `105`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/a87f49e0-9834-4eb6-9d92-b80b36370d16",
              "type": "Type",
              "_label": "Dissertations, Academic -- United States -- Bibliography"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/ee403f31-4429-4808-8c18-a6cc677eb89a",
              "type": "Type",
              "_label": "Asia -- Study and teaching -- United States -- Bibliography"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/90c1b0c3-a264-4117-8da5-9847c74fbf92",
              "type": "Type",
              "_label": "Asia -- Study and teaching -- United States"
            }
          ]
        }
        ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

