---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
---

# Works in whole/part relationships

Record-level resources can be part of a work cluster through a relationship to a work entity.

These `part_of` relationships apply to the following source data fields:

-   `1XX` followed by `240`
-   `130` and `830`
-   `800`, `810`, or `811` with subfield `t`.

Record-level resource can also contain multiple work entity parts, in which case the relationship is reversed, and the `part_of` relationship points from a component work entity back to the record-level resource that contains it.

These reverse `part_of` relationships apply to the following source data fields:

-   `700`, `710`, `711`, and `730`.

1.  For the `record-level → part_of → container` case, add an embedded `part_of` reference to the work entity within the record-level resource.

    1.  As the `_label` of the work entity, take the value of the top-level entity label.

    2.  Process simple work references.

        **Note:** Work entity derived from `130`.

        `2035`

        ```
        {
          "part_of": [
            {
              "id": "https://lux.collections.yale.edu/data/text/work3",
              "type": "LinguisticObject",
              "_label": "Jourdain de Blaye"      
            }
          ]
        }
        ```

    3.  Process complex work references.

        **Note:** Work entity derived from `100 + 240`.

        `67759`

        ```
        {
          "part_of": [
            {
              "id": "https://lux.collections.yale.edu/data/text/work1",
              "type": "LinguisticObject",
              "_label": "Afrique en marche. English"      
            }
          ]
        }
        ```

2.  For the `component → part_of → record-level` case, add an embedded `part_of` reference to the record-level resource from the component resource.

    1.  As the `_label` of the embedded record-level entity, take the value of the top-level entity label.

    2.  As the `type` of the embedded record-level entity, take the value of the record-level entity type.

    `11167715`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/text/dcbc799e-b227-4551-bf84-3583cf16cdac",
      "type": "LinguisticObject",
      "_label": "Almond trees",
      "identified_by": [
        {
          "type": "Name",
          "content": "Almond trees",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "part_of": [
        {
          "id": "https://lux.collections.yale.edu/data/text/b6c8d4c3-fe3d-4001-bb7a-d7fa83aac9c3",
          "type": "LinguisticObject",
          "_label": "Piano concerto and solo piano works [electronic resource]"
        }
      ],
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/bfda6041-031c-474e-8fdc-e21c9aeb674a",
                "type": "Person",
                "_label": "Ireland, John, 1879-1962"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/d9928fc0-fb8d-4bf4-980d-27856072334f",
                "type": "Type",
                "_label": "Creator"
              }
            ]
          }
        ]
      }
    }
    ```


**Parent topic:**[Works](../../concepts/works.md)

