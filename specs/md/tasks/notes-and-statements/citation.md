---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Citation

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: Citation
sampleBibs:
  - 909399
  - 10563633
fieldSpec:
  - 510abcu
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Check for `510u`.

    -   Ignore `510u` if it does not include a URI containing the string `wikidata.org` and skip to step 3, below.
    -   If `510u` is present with a Wikidata URI \(e.g., [http://www.wikidata.org/entity/Q107432855](http://www.wikidata.org/entity/Q107432855)\), generate a top-level citation entity with an `equivalent` reference to the Wikidata URI \(see [Citation entities](../citation_entities.md)\).
    -   Else, [output an inline citation object](#step_m53_cph_krb) in the `referred_to_by` array.
2.  When `510u` is present with a Wikidata URI, output a reference to the top-level citation entity.

    -   If subfields `510b` or `510c` are present, join them with `510a`, using a whitespace character, as the `_label` value in the reference.
    -   Else, output the string value of the top-level citation entity name as the `_label` value in the reference.
    **Note:** This example is meant to illustrate a citation reference and does not represent a complete JSON-LD document.

    `10563633`

    ```
    {
      "referred_to_by": [
        {
          "id": "https://lux.collections.yale.edu/data/text/citation1",
          "type": "LinguisticObject",
          "_label": "Edizioni italiane del XVI secolo
        }
      ]
    }
    ```

3.  When no `510u` is present with a Wikidata URI, process the values for inline citations \(MARC `510abc`\).

    **Note:** This example is meant to illustrate an inline citation and does not represent a complete JSON-LD document.

    `909399`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Abbey, J.R. Scenery 111",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311705",
              "type": "Type",
              "_label": "Citation",
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
              "content": "Citation/References Note",
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

