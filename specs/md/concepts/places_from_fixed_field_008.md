---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Places from fixed field 008

Place entities derived from `MARC 008`.

## Source data

```
---
name: PlacesFrom008
sampleBibs:
  - 404281 # 008, published
  - 2744420 # 008, created
  - 3906934 # 008, published
  - 11167038 # 008, located
# Source data fields
fieldSpec:
  - 008[15-17]
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

`008[15-17]` contains a two- or three-letter code representing a country- or state-level place entity.

The code represents a place of publication, production, execution, or sometimes location \(in the case of manuscript holdings\).

1.  Generate and store the top-level place resource, identified by an IRI.

    1.  Normalize whitespace to test for null values and eliminate trailing whitespace after two-letter codes.

    2.  Match the two- or three-letter code against the Library of Congress's [MARC List for Countries](https://id.loc.gov/vocabulary/countries.html), which is available as a [tab-delimited file](http://id.loc.gov/vocabulary/countries.tsv), and add the corresponding URI as an `equivalent` reference, as shown below.

    3.  Use the place name from the Library of Congress file as a key to match against and merge with equivalent place entities.

        For example, references to "France" should point to the same entity IRI, regardless of the data source in MARC. `008 850723s1984 fr a b 00100 fre d` and `650 0 $a Opera $z France.` should both result in a link to the same place entity representing France.

    `3906934`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/3dcbc9fa-ca9c-4fa1-bd0e-d25e93f461e5",
      "type": "Place",
      "_label": "France",
      "identified_by": [
        {
          "type": "Name",
          "content": "France",
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
          "id": "http://id.loc.gov/vocabulary/countries/fr",
          "type": "Place"
        }
      ]
    } 
    ```

2.  Use the supertype value of the record-level resource to determine the type of place represented by the `008[15-17]` value.

    -   If the record-level supertype is one of the following:

        -   Any `Objects` format
        -   Any `Visual Works` format
        -   `Dissertations and Theses`
        then the type of place is `creation`.

    -   If the record-level supertype is equal to `Archival and Manuscript Materials`, then the type of place is `location`.
    -   Else, the type of place is `publication`.
3.  Add an embedded reference to the place entity within the record-level resource.

    1.  As the `_label` of the place entity, take the value of the top-level entity label.

    2.  Process `creation` places.

        `2744420`

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/6694afea-e43b-4d8d-9005-03b63540e8b5",
                    "type": "Person",
                    "_label": "Wu, Shengwu"
                  }
                ],
                "classified_as": [
                  {
                    "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                    "type": "Type",
                    "_label": "creator"
                  }
                ]
              }
            ],
            "took_place_at": [
              {
                "id": "https://lux.collections.yale.edu/data/place/3dcbc9fa-ca9c-4fa1-bd0e-d25e93f461e5",
                "type": "Place",
                "_label": "France"
              }
            ]
          }
        }
        ```

    3.  Process `location` places

        `11167038`

        ```
        {
          "attributed_by": [
            {
              "type": "AttributeAssignment",
              "_label": "location",
              "assigned": {
                "id": "https://lux.collections.yale.edu/data/place/1585b6fe-6613-49fb-b254-3b911d5796bf",
                "type": "Place",
                "_label": "Connecticut"
              }
            }
          ]
        }
        ```

    4.  Process `publication` places.

        `404281`

        ```
        {
          "used_for": [
            {
              "type": "Activity",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300054686",
                  "type": "Type",
                  "_label": "Publishing"
                }
              ],
              "took_place_at": [
                {
                  "id": "https://lux.collections.yale.edu/data/place/3dcbc9fa-ca9c-4fa1-bd0e-d25e93f461e5",
                  "type": "Place",
                  "_label": "France"
                }
              ]
            }
          ]
        }
        ```


**Parent topic:**[Top-level Place entities](../concepts/top_level_place_entities.md)

