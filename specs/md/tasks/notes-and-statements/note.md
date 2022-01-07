---
author: timothy.thompson@yale.edu
keyword: Assigned
---

# Note

|Domains|Usage|
|-------|-----|
|`LinguisticObject`| |
|`VisualItem`| |
|`DigitalObject`| |

## Source data

```
---
name: Note
sampleBibs:
  - 2
  - 2814209
fieldSpec:
  - 500a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  For each `500a` note, output its value as a `Note` resource.

    `2`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/968652fc-4e7b-479b-a5b9-f8c0cd68bcb8",
      "type": "LinguisticObject",
      "_label": "Die Streitkräfte der NATO auf dem Territorium der BRD",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300028051",
          "type": "Type",
          "_label": "Books",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435443",
              "type": "Type",
              "_label": "Type of Work"
            }
          ]
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/61d2655b-095d-4864-9d62-e04e55042baf",
          "type": "Type",
          "_label": "UA646.5.G4"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Die Streitkräfte der NATO auf dem Territorium der BRD",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Streitkräfte der NATO auf dem Territorium der BRD",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Includes index.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300027200",
              "type": "Type",
              "_label": "Note",
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
              "content": "Note",
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


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

