---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Complex works as complex subjects

Complex works may appear as facets in complex subject headings.

## Processing steps and output

1.  Apply the instructions in [Complex subject/genre headings and hierarchical associated places](../concepts/complex_subject_headings.md) and [Complex works](../concepts/name_title_entries.md) to produce the desired output.

    The `LinguisticObject` facet representing the work entity should be constructed according to [Complex works](../concepts/name_title_entries.md). However, the agent \(`Person` or `Group`\) facet should also be included as a separate facet under `influenced_by`.

2.  Join the `agent value` and the `work value` as the `complex work reference`.

    -   If the `agent value` ends with a hyphen \(`-`\) or period \(`.`\), join the two values with a whitespace character.
    -   Else, join the two values with a period and whitespace character.
3.  Join the `complex work reference` with the subdivision subfields using space-surrounded double hyphens \(`--`\) to output the `_label` and `content` values of the full precoordinated heading.

    `908059`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/complex1",
      "type": "Type",
      "_label": "Fedorov, Ivan, approximately 1510-1583. Azbuka -- Concordances",
      "identified_by": [
        {
          "type": "Name",
          "content": "Fedorov, Ivan, approximately 1510-1583. Azbuka -- Concordances",
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
            "id": "https://lux.collections.yale.edu/data/person/person1",
            "type": "Person",
            "_label": "Fedorov, Ivan, approximately 1510-1583"
          },
          {
            "id": "https://lux.collections.yale.edu/data/text/work1",
            "type": "LinguisticObject",
            "_label": "Azbuka"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/form1",
            "type": "Type",
            "_label": "Concordances"
          }
        ]
      }
    }
    
    ```


**Parent topic:**[Works as subjects](../../tasks/name-title/works_as_subjects.md)

