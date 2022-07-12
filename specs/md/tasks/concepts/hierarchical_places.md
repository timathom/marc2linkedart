---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: Assigned
---

# Place hierarchies

Place entities represented as a hierarchy.

Apply these instructions for field `752` \(hierarchical place name\) and for geographic subdivisions \(`6XXz`\) when there is a sequence of two or more.

`752` entries and sequences of two or more geographic subdivisions represent a chain of places defined by `part_of` relationships.

The actual entity represented is the last \(i.e., most specific\) subdivision in the heading or sequence. Preceding subdivisions should be linked in reverse order from the last geographic element in the hierarchy.

## Source data

```
---
name: HierarchicalPlaces
sampleBibs:
  - 35599
  - 3802854
# Source data fields
fieldSpec:
  - 6XXz
  - 752014abcdefgh
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Generate and store a top-level place resource for the last subdivision, identified by an IRI.

    1.  Ignore subfields `014e` when creating a key for matching and merging.

    2.  As the value of the matching key, use the current and preceding subdivision values.

    3.  Join subdivision values with space-separated double hyphens \(`--`\).

        `35599`

        ```
        752  $a United States $b New York (State) $d New York $f Brooklyn.
        ```

        -   Matching key for last \(most specific\) subdivision: `united states -- new york state -- new york -- brooklyn`
        -   Matching key for preceding \(third\) subdivision: `united states -- new york state -- new york`
        -   Matching key for preceding \(second\) subdivision: `united states -- new york state`
        -   Matching key for preceding \(first\) subdivision: `united states`
    4.  If a field includes a `$0` with an IRI, output an `equivalent` reference.

        **Note:** The `Type` of the `equivalent` reference should match the `Type` of the top-level resource.

2.  Working back from the last subdivision, generate and store a top-level place resource for each preceding geographic subdivision, identified by IRIs.

3.  Link the place entities using the `part_of` property.

4.  As the `_label` and `Primary Name` of each place entity, use the value of the respective subdivision.

5.  Construct the chain of place entities for `752` entries.

    `35599`

    ```
    752  $a United States $b New York (State) $d New York $f Brooklyn.
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/752-place",
      "type": "Place",
      "_label": "Brooklyn",
      "identified_by": [
        {
          "type": "Name",
          "content": "Brooklyn",
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
          "id": "https://lux.collections.yale.edu/data/place/752-place-3",
            "type": "Place",
            "_label": "New York"
        }
      ]
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/752-place-3",
      "type": "Place",
      "_label": "New York",
      "identified_by": [
        {
          "type": "Name",
          "content": "New York",
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
          "id": "https://lux.collections.yale.edu/data/place/752-place-2",
          "type": "Place",
          "_label": "New York (State)"
        }
      ]
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/752-place-2",
      "type": "Place",
      "_label": "New York (State)",
      "identified_by": [
        {
          "type": "Name",
          "content": "New York (State)",
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
          "id": "https://lux.collections.yale.edu/data/place/752-place-1",
          "type": "Place",
          "_label": "United States"
        }
      ]
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/752-place-1",
      "type": "Place",
      "_label": "United States",
      "identified_by": [
        {
          "type": "Name",
          "content": "United States",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```

6.  In each referring record-level resource \(`LinguisticObject`, `Set`, `VisualItem`\), add an embedded reference to the most specific `752` entity.

    1.  See [Associated places](../../concepts/associated_places.md) for instructions related to `752`.

7.  Construct the chain of place entities for sequences of two or more `6XXz` subdivisions.

    `3802854`

    ```
    650 0 $a Folk songs, Romanian $z Romania $z Loviștea Region $v Texts.
    ```

    `3802854`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/70db3ab1-33fa-4123-8217-2d8c85576aa9",
      "type": "Type",
      "_label": "Folk songs, Romanian -- Romania -- Loviștea Region -- Texts",
      "identified_by": [
        {
          "type": "Name",
          "content": "Folk songs, Romanian -- Romania -- Loviștea Region -- Texts",
           "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/concept/75bb7d9f-2d42-4219-8790-62eacbf10f7a",
            "type": "Type",
            "_label": "Folk songs, Romanian"
          },     
          {
            "id": "https://lux.collections.yale.edu/data/place/23e3171a-f151-4c54-aee3-afb13109da61",
            "type": "Place",
            "_label": "Loviștea Region"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/f27fdcfa-e945-4a86-a623-57c418c8780d",
            "type": "Type",
            "_label": "Texts"
          }
        ]
      }
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/23e3171a-f151-4c54-aee3-afb13109da61",
      "type": "Place",
      "_label": "Loviștea Region",
      "identified_by": [
        {
          "type": "Name",
          "content": "Loviștea Region",
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
          "id": "https://lux.collections.yale.edu/data/place/8659a573-f14f-4cc9-ab3d-41b56ddb9d78",
          "type": "Place",
          "_label": "Romania"
        }
      ]
    }
    ```

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/place/8659a573-f14f-4cc9-ab3d-41b56ddb9d78",
      "type": "Place",
      "_label": "Romania",
      "identified_by": [
        {
          "type": "Name",
          "content": "Romania",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Top-level Place entities](../../concepts/top_level_place_entities.md)

