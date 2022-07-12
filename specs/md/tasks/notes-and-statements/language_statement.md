---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Language statement

Textual information on the language or notation system used to convey the content of the described materials.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Include language information on related `HumanMadeObject` or `DigitalObject`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: LanguageStatement
sampleBibs:
  - 1001852
fieldSpec:
  - 546ab
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the language statement values \(MARC `546ab`\).

    -   If both subfields \(`546ab`\) are present, join them with a whitespace character.
    -   Else, output the string value of `546a`.
2.  For top-level resources with a base class of `LinguisticObject`:

    **Note:** This example is meant to illustrate a language statement and does not represent a complete JSON-LD document.

    `1001852`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Syriac; Hebrew alphabet.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435433",
              "type": "Type",
              "_label": "Language Statement",
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
              "content": "Language Note",
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

3.  For record-level resources with a base class of `VisualItem` \(e.g., [Posters](../supertypes/posters.md) or [Prints](../supertypes/prints.md)\) that have associated language information, that information should be attached to the related `HumanMadeObject` or `DigitalObject` using the `carries` \(`HumanMadeObject`\) or `digitally_carries` \(`DigitalObject`\) property.

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://linked-art.library.yale.edu/node/abc123",
      "type": "HumanMadeObject",
      "_label": "[Example]",
      "member_of": [
        {
          "id": "https://linked-art.library.yale.edu/node/9d83b3ef-e184-4a46-a2b3-db895d9948bc",
          "type": "Set",
          "_label": "Yale University Library"
        }
      ],
      "shows": [
        {
          "id": "https://linked-art.library.yale.edu/node/xyz456",
          "type": "VisualItem",
          "_label": "[Example]"
        }
      ],
      "carries": [
        {
          "type": "LinguisticObject",
          "referred_to_by": [
            {
              "type": "LinguisticObject",
              "content": "In English and Portuguese",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435433",
                  "type": "Type",
                  "_label": "Language Statement",
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
                  "content": "Language Note",
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
      ]
    }
    ```

4.  For top-level resources with a base class of `Set` \(archival records or kits\), language information should be attached to the embedded `HumanMadeObject` resource using the `carries` property.

    `11167038`

    ```
    {
      "members_exemplified_by": [
        {
          "type": "HumanMadeObject",
          "carries": [
            {
              "type": "LinguisticObject",
              "referred_to_by": [
                {
                  "type": "LinguisticObject",
                  "content": "In unidentified cipher.",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300435433",
                      "type": "Type",
                      "_label": "Language Statement",
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
                      "content": "Language Note",
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
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

