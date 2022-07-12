---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed]
---

# Classification numbers

Resources extracted from MARC 050 and 090 entries.

## Source data

```
---
name: ClassificationNumbers
sampleBibs:
  - 4
  - 11 # 050 and 090
  - 236
  - 907498
  - 4824458
  - 15589961
# Source data fields
fieldSpec:
  - 050a
  - 090a
trimPunctuation: true
stripPunctuation:
  - true
  - preserve:
    - period
scriptInclusion: NONE
```

1.  For each unique `050a` or `090a` value, generate and store a top-level concept resource, identified by an IRI.

2.  Create a key for matching.

    1.  Replace any punctuation characters that are *not* a period \(`.`\) with a whitespace character.

    2.  [Normalize](../../glossary/normalization.md) and match/merge each unique string value.

    3.  After normalizing, use an appropriate regular expression to test the value of `050a` or `090a` to see whether it is an LC classification number.

        `[a-z]+[0-9]+([.][a-z]+[0-9]+)?`

    4.  For values that match the test, add a `classified_as` for `Library of Congress classification`, as in the example below.

    5.  For now, skip any values that do not match the regular expression.

    1.  `907498`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
          "type": "Type",
          "_label": "PT3818",
          "identified_by": [
            {
              "type": "Identifier",
              "content": "PT3818"
            }
          ],
          "classified_as": [
            {
              "id": "http://www.wikidata.org/entity/Q621080",
              "type": "Type",
              "_label": "Library of Congress classification"
            }
          ]
        }
        ```

    2.  `907498`

        ```
        {
          "@context": "https://linked.art/ns/v1/linked-art.json",
          "id": "https://lux.collections.yale.edu/data/concept/f0c0c4d0-532d-4438-a26f-15c261fb4f6c",
          "type": "Type",
          "_label": "PT3818",
          "identified_by": [
            {
              "type": "Identifier",
              "content": "PT3818"
            }
          ],
          "classified_as": [
            {
              "id": "http://www.wikidata.org/entity/Q621080",
              "type": "Type",
              "_label": "Library of Congress classification"
            }
          ]
        }
        ```

3.  In the referring record-level resource \(`LinguisticObject`, `Set`, `VisualItem`\), add an embedded reference for each concept entity.

    1.  If there is more than concept entity, sort them by their string values in alphanumeric order.

    **Note:** The embedded reference should follow the classification of the resource in the same `classified_as` array.

    `11`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/8697aefe-8ffa-4f73-bf3d-f4883a5c26dd",
      "type": "LinguisticObject",
      "_label": "Governmental accounting, auditing, and financial reporting",
      "classified_as": [    
        {
          "id": "https://lux.collections.yale.edu/data/concept/090-1",
          "type": "Type",
          "_label": "HJ9771"
        },
        {
          "id": "https://lux.collections.yale.edu/data/concept/e372cfe2-988e-41c7-ab4a-30dea4dce28b",
          "type": "Type",
          "_label": "HJ9773"
        }    
      ]
    }
    ```


**Parent topic:**[Concepts](../../concepts/concepts.md)

**Related information**  


[050 \(Library of Congress Call Number\)](../../tables/050_bib_table.md)

[090](../../tables/090_bib_table.md)

