---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Groups as subjects

Entities extracted from MARC 61X fields.

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md) or [Complex subject/genre headings](../tasks/concepts/complex_subject_headings.md), add an embedded reference to the group entity within the record-level resource.

    1.  As the \_label of the group entity, take the value of the top-level entity label.

    2.  Process simple group references.

        `68`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/group/a3d54906-5375-46a0-b0df-d6be7d6ecb7f",
              "type": "Group",
              "_label": "United States. National Archives and Records Service"
            }
          ]
        }
        ```

    3.  Process concept/group references.

        `7731`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/54f5b059-a062-426a-a554-fe123c479779",
              "type": "Type",
              "_label": "Lebanon. Majlis al-Nūwāb -- Elections -- 1968"
            }
          ]
        }
        ```


**Parent topic:**[Groups](../concepts/groups.md)

