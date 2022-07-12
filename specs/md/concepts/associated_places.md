---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Associated places

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md) or [Place hierarchies](../tasks/concepts/hierarchical_places.md), add an embedded reference to the associated place entity within the record-level resource.

    1.  The `_label` of the `attributed_by` structure should always be `associated place`.

    2.  As the \_label of the concept entity, take the value of the top-level entity label.

    3.  Process simple place references.

        `1066178`

        ```
        {
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "_label": "associated place",
              "assigned": {
                "id": "https://lux.collections.yale.edu/data/place/d6997bff-a0d4-4394-93b6-fb9e6402bc13",
                "type": "Place",
                "_label": "Gateshead, England"
              }
            }
          ]
        }
        ```

    4.  Process complex place references.

        `9564880`

        ```
        {
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "_label": "associated place",
              "assigned": {
                "id": "https://lux.collections.yale.edu/data/place/752-place",
                "type": "Place",
                "_label": "United States -- New York (State) -- New York -- Brooklyn"
              }
            }
          ]
        }
        ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

