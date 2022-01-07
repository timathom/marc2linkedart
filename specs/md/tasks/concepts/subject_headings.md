---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: Assigned
---

# Subject and genre/form headings

Resources extracted from MARC 6XX entries.

## Processing steps and output

1.  After applying the instructions in [Creators, contributors, standalone works, simple subject/genre headings, and associated places](simple_subject_headings.md) or [Complex subject/genre headings and hierarchical associated places](complex_subject_headings.md), add an embedded reference to the concept entity within the record-level resource.

    **Note:** Genre entities should be modeled using the `classified_as` pattern.

    1.  As the \_label of the concept entity, take the value of the top-level entity label.

    2.  Process simple concept references for subject headings.

        `3`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/522b36c5-57c4-4026-9deb-ff1aeb3ef187",
              "type": "Type",
              "_label": "Paleoecology"
            }
          ]
        }
        ```

    3.  Process complex concept references for subject headings.

        `9564880`

        ```
        {
          "about": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/c5ba671b-c41d-40f5-983f-beb38b75b5b2",
              "type": "Type",
              "_label": "Death -- Religious aspects -- Christianity"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
              "type": "Type",
              "_label": "Death -- Religious aspects -- Christianity -- History -- 2nd century"
            }
          ]
        }
        ```

    4.  Process simple concept references for genre \(`655`\) headings.

        `34747`

        ```
        {
          "id": "https://lux.collections.yale.edu/data/text/c3b75623-7203-4a73-8c5b-f7d442d11dc2",
          "type": "LinguisticObject",
          "_label": "Tšhukudu",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300028051",
              "type": "Type",
              "_label": "Books",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300226816",
                  "type": "Type",
                  "_label": "Format"
                }
              ]
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/d3ce7f25-0650-4c92-be9e-01a17a4827ca",
              "type": "Type",
              "_label": "PL8690.9.M35"
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/8dbace9e-d7ee-4d0e-a5f5-3784b7aaaf80",
              "type": "Type",
              "_label": "Northern Sotho poetry",
              "classified_as": [
                {
                  "id": "http://www.wikidata.org/entity/Q483394",
                  "type": "Type",
                  "_label": "Genre"
                }
              ]
            }
          ]
        }
        ```

    5.  Process complex concept references for genre \(`655`\) headings.

        `486848`

        ```
        {
          "id": "https://lux.collections.yale.edu/data/text/810e7bed-875e-4a9b-baf3-5e8d8e5aabac",
          "type": "LinguisticObject",
          "_label": "Blue moon",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300215390",
              "type": "Type",
              "_label": "Journals",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300226816",
                  "type": "Type",
                  "_label": "Format"
                }
              ]
            },
            {
              "id": "https://lux.collections.yale.edu/data/concept/c29adf17-ad5c-4925-8201-3f4c119ebeb7",
              "type": "Type",
              "_label": "College student newspapers and periodicals -- Connecticut -- New Haven",
              "classified_as": [
                {
                  "id": "http://www.wikidata.org/entity/Q483394",
                  "type": "Type",
                  "_label": "Genre"
                }
              ]
            }
          ]
        }
        ```


**Parent topic:**[Concepts](../../concepts/concepts.md)

**Related information**  


[600 \(Subject Added Entry-Personal Name\)](../../tables/600_bib_table.md)

[610 \(Subject Added Entry-Corporate Name\)](../../tables/610_bib_table.md)

[611 \(Subject Added Entry-Meeting Name\)](../../tables/611_bib_table.md)

[630 \(Subject Added Entry-Uniform Title\)](../../tables/630_bib_table.md)

[650 \(Subject Added Entry-Topical Term\)](../../tables/650_bib_table.md)

[651 \(Subject Added Entry-Geographic Name\)](../../tables/651_bib_table.md)

[653 \(Index Term-Uncontrolled\)](../../tables/653_bib_table.md)

[655 \(Index Term-Genre/Form\)](../../tables/655_bib_table.md)

[656 \(Index Term-Occupation\)](../../tables/656_bib_table.md)

[657 \(Index Term-Function\)](../../tables/657_bib_table.md)

[662 \(Subject Added Entry-Hierarchical Place Name\)](../../tables/662_bib_table.md)

[688 \(Subject Added Entry-Type of Entity Unspecified\)](../../tables/688_bib_table.md)

[690](../../tables/690_bib_table.md)

[691](../../tables/691_bib_table.md)

[692](../../tables/692_bib_table.md)

[693](../../tables/693_bib_table.md)

[694](../../tables/694_bib_table.md)

[695](../../tables/695_bib_table.md)

