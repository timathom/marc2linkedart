---
author: timothy.thompson@yale.edu
---

# Citation entities

## Source data

```
---
name: CitationEntities
sampleBibs:
  - 10563633
fieldSpec:
  - 510abcu
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  For each MARC `510`, if subfield `u` is present and includes a URI containing the string `wikidata.org` \(e.g.,[http://www.wikidata.org/entity/Q107432855](http://www.wikidata.org/entity/Q107432855)\), generate a top-level citation entity with an `equivalent` reference to the Wikidata URI.

    1.  Use the Wikidata URI as a key for matching and merging citation entities.

    2.  Use the value of `510a` as the `_label` and `Primary Name` of the citation entity.

    `3931`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/citation1",
      "type": "LinguisticObject",
      "_label": "Edizioni italiane del XVI secolo",
      "identified_by": [
        {
          "type": "Name",
          "content": "Edizioni italiane del XVI secolo",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "equivalent": [
        {
          "id": "http://www.wikidata.org/entity/Q107444740",
          "type": "LinguisticObject"
        }
      ]
    }
    ```


**Parent topic:**[Related entities](../tasks/related_entities.md)

