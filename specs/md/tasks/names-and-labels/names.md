---
author: timothy.thompson@yale.edu
---

# Names

In Linked Art, `Name` is a resource type \(class\) that is invoked whenever a resource needs to be identified by name.

1.  Identify top-level resources by name.

    `9447`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/group/45a90f8b-c64e-4b2c-91ee-cc714361eaed",
      "type": "Group",
      "_label": "International Cultural Foundation",
      "identified_by": [
        {
          "type": "Name",
          "content": "International Cultural Foundation"
        }
      ]
    }
    ```

2.  Identify embedded resources \(for example, notes\) by name.

    `9447`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "190 p.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435430",
              "type": "Type",
              "_label": "Dimension Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Extent",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


-   **[Primary name](../../tasks/names-and-labels/primary_name.md)**  
Main title of a record-level entity.
-   **[Sorting name](../../tasks/names-and-labels/sorting_name.md)**  
Sorting title of a record-level entity. Taken from MARC`245`with initial articles removed.
-   **[Transcribed series title](../../tasks/names-and-labels/transcribed_series_title.md)**  
Transcribed series title of a record-level entity. Taken from MARC `440` or `490`.
-   **[Alternative title](../../tasks/names-and-labels/alternative_title.md)**  
Alternative title of a record-level entity. Taken from MARC `246`.

**Parent topic:**[Names and labels](../../concepts/names_and_labels.md)

