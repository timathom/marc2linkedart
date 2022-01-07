---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
---

# Works in whole/part relationships

Record-level resources can be part of a work cluster through a relationship to a work entity.

These `part_of` relationships apply to the following source data fields:

-   `1XX` followed by `240`
-   `130`, `730`, and `830`
-   `700`, `710`, `711`, `800`, `810`, or `811` with subfield `t`.

1.  Add an embedded reference to the work entity within the record-level resource.

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


**Parent topic:**[Works](../../concepts/works.md)

