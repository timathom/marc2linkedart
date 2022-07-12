---
author: timothy.thompson@yale.edu
---

# Works as subjects

1.  Add an embedded reference to the work entity within the record-level resource.

    1.  As the `_label` of the work entity, take the value of the top-level entity label.

    2.  Process simple work references.

        `227`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/text/ea02530e-580f-41a8-92ac-d9e302ec5fbe",
              "type": "LinguisticObject",
              "_label": "Munich Four-Power Agreement (1938)"
            }
          ]
        }
        ```

    3.  Process complex work references.

        `72`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/text/work2",
              "type": "Type",
              "_label": "Faust. 1. Theil"
            }
          ]
        }
        ```

    4.  Process concept/work references.

        `908059`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/complex1",
              "type": "Type",
              "_label": "Fedorov, Ivan, approximately 1510-1583. Azbuka -- Concordances"
            }
          ]
        }
        ```


-   **[Complex works as complex subjects](../../tasks/name-title/name-title-with-subdivisions.md)**  


**Parent topic:**[Works](../../concepts/works.md)

