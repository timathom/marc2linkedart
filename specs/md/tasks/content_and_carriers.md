---
author: timothy.thompson@yale.edu
---

# Content and carriers

In Linked Art, record-level entities are divided into two categories:

-   Conceptual entities, which represent the intellectual content of a resource:

    -   `DigitalObject`

    -   `LinguisticObject`

    -   `Set`

    -   `VisualItem`

-   Carrier entities, which carry that content in a particular form:

    -   `DigitalObject`

    -   `HumanMadeObject`


**Note:** For supertypes under the `Datasets` and `Software and Electronic Media` content types, a single `DigitalObject` resource should be generated, representing both content and carrier in a single resource.

Resources with a base class of `LinguisticObject` or `VisualItem` must follow the content/carrier model. In MARC-based systems, this model corresponds roughly to the distinction between bibliographic records and holdings records.

For each record-level resource with a base class of `LinguisticObject` or `VisualItem` \(the *content* level\), one or more resources with a base class of `HumanMadeObject` or `DigitalObject` \(the *carrier* level\) must be generated.

**Note:** `DigitalObject` carriers should be generated when the MFHD `852b` has a value of `yulint` or `yulintx`.

These `HumanMadeObject` or `DigitalObject` resources must point to the `LinguisticObject` or `VisualItem` resource that they instantiate and where the supertype and any subjects, etc., are assigned.

The following diagram \(by Rob Sanderson\) provides a high-level overview of the Linked Art model.

![](../resources/img/base-model-classes.png)

## Processing steps and output

1.  For each MARC bibliographic record, determine the supertype of the resource and generate a JSON-LD document with a `type` value corresponding to the base class of the supertype.

    **Note:** For supertypes with two possible base classes \(such as [Globes](supertypes/globes.md)\), apply the [order of preference](../concepts/record_level_entities.md#) for base classes.

    **Note:** This example is meant to illustrate the base class/supertype association and does not represent a complete JSON-LD document.

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3",
      "type": "LinguisticObject",
      "_label": "麗澤論說集錄 : [十卷]",
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
        }
      ]
    }
    ```

2.  For each MARC holdings record attached to a bibliographic record:

    -   If the base class derived from the supertype is `LinguisticObject` or `VisualItem`:
        -   If the MFHD `852b` is `yulint` or `yulintx`, generate a JSON-LD document with a base class of `DigitalObject`.
        -   Else, generate a JSON-LD document with a base class of `HumanMadeObject`.
    -   If the base class derived from the supertype is `Set`, generate an embedded `Set → members_exemplified_by → HumanMadeObject` resource to record carrier-level information.
    -   If the base class derived from the supertype is `DigitalObject`, do not generate a separate carrier-level resource. Record both content- and carrier-level information in a single JSON-LD document, with `DigitalObject` as base class.
3.  If the supertype of the resource corresponding to the bibliographic record has a base class of `LinguisticObject` or `VisualItem`, then `HumanMadeObject` carriers must point to the content-level resource using the `carries` property for `LinguisticObject` resources or the `shows` property for `VisualItem` resources. For `DigitalObject` carriers, the corresponding properties are `digitally_carries` and `digitally_shows`.

4.  If the supertype of the resource corresponding to the bibliographic record has a base class of `Set` \(for archival records or kits\), then the `HumanMadeObject` carrier is **not** modeled as a separate resource, but rather embedded within the `Set` resource using the property `members_exemplified_by`.


**Note:** These examples are meant to illustrate the content/carrier distinction and do not necessarily represent complete JSON-LD documents.

1.  `Set → members_exemplified_by → HumanMadeObject` \[`3779671`\]

    ```
    {
      "id": "https://lux.collections.yale.edu/data/set/00046754-f28f-4b56-a611-056341335226",
      "type": "Set",
      "_label": "شجون المسجون وفتون المفتون / 1863",
      "members_exemplified_by": [
        {
          "type": "HumanMadeObject",
          "_label": "شجون المسجون وفتون المفتون / 1863",
          "identified_by": [
            {
              "type": "Identifier",
              "content": "Arabic MSS 480 (lsfbeir)",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300311706",
                  "type": "Type",
                  "_label": "Call Number"
                }
              ]
            }
          ],
          "referred_to_by": [
            {
              "type": "LinguisticObject",
              "content": "At the Library",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300133046",
                  "type": "Type",
                  "_label": "Access Statement",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300418049",
                      "type": "Type",
                      "_label": "Brief Text"
                    }
                  ]
                }
              ]
            },
            {
              "type": "LinguisticObject",
              "content": "Purchased from Oskar Rescher in August 1959 on plain fund.",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435438",
                  "type": "Type",
                  "_label": "Provenance Statement",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300418049",
                      "type": "Type",
                      "_label": "Brief Text"
                    }
                  ]
                }
              ]
            },
            {
              "type": "LinguisticObject",
              "content": "leaves 119 verso-176 ; 24.5 x 18 cm",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435452",
                  "type": "Type",
                  "_label": "Physical Statement",
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
                  "content": "Physical Description",
                  "classified_as": [
                    {
                      "id": "http://vocab.getty.edu/aat/300404669",
                      "type": "Type",
                      "_label": "Display Title"
                    }
                  ]
                }
              ]
            },
            {
              "type": "LinguisticObject",
              "content": "Purchased from Oskar Rescher in August 1959 on plain fund.",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300435438",
                  "type": "Type",
                  "_label": "Provenance Statement"
                }
              ],
              "identified_by": [
                {
                  "type": "Name",
                  "content": "Ownership and Custodial History",
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
          ],
          "subject_of": [
            {
              "type": "LinguisticObject",
              "_label": "Text of Repository Page",
              "digitally_carried_by": [
                {
                  "type": "DigitalObject",
                  "_label": "Repository Page",
                  "access_point": [
                    {
                      "id": "https://search.library.yale.edu/catalog/3779671",
                      "type": "DigitalObject"
                    }
                  ]
                }
              ]
            }
          ],
          "member_of": [
            {
              "id": "https://lux.collections.yale.edu/data/set/e8647339-0041-4eeb-bd83-079f931e9e06",
              "type": "Set",
              "_label": "Special Collections (YUL)"
            }
          ],
          "carries": [
            {
              "type": "LinguisticObject",
              "language": [
                {
                  "id": "https://lux.collections.yale.edu/data/concept/2b8c1ef3-fb14-4306-9d7c-d5b198acc3f8",
                  "type": "Language",
                  "_label": "Arabic"
                }
              ]
            }
          ]
        }
      ]
    }
    ```

2.  `HumanMadeObject → carries → LinguisticObject` \[`7778409`\]

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/object/8e0bdbff-ebb1-4f9b-b98b-e97d64a01ff9",
      "type": "HumanMadeObject",
      "_label": "麗澤論說集錄 : [十卷]",
      "carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3",
          "type": "LinguisticObject",
          "_label": "麗澤論說集錄 : [十卷]"
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "BL1840 .L84 2003 [Library Shelving Facility (LSF)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Li ze lun shuo ji lu : [shi juan]",
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
          "content": "\u9e97\u6fa4\u8ad6\u8aaa\u96c6\u9304 : [\u5341\u5377]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "At the Library",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        },
        {
          "type": "LinguisticObject",
          "content": "5 v. ; 33 cm",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435452",
              "type": "Type",
              "_label": "Physical Statement",
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
              "content": "Physical Description",
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
      ],
      "subject_of": [
        {
          "type": "LinguisticObject",
          "_label": "Text of Repository Page",
          "digitally_carried_by": [
            {
              "type": "DigitalObject",
              "_label": "Repository Page",
              "access_point": [
                {
                  "id": "https://search.library.yale.edu/catalog/7778409",
                  "type": "DigitalObject"
                }
              ]
            }
          ]
        }
      ],
      "member_of": [
        {
          "id": "https://lux.collections.yale.edu/data/set/ef3a133a-f7b4-4548-bfa0-019d5da7b1c1",
          "type": "Set",
          "_label": "General Collection (YUL)"
        }
      ]
    }
    ```

3.  `HumanMadeObject → shows → VisualItem` \[`9777342`\]

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/object/000564c6-1615-47e6-b379-192e16a3e14a",
      "type": "HumanMadeObject",
      "_label": "Lessons for shaving!!! [graphic]",
      "shows": [
        {
          "id": "https://lux.collections.yale.edu/data/visual/fd3d836b-1cd1-47d9-a38e-002ce325601b",
          "type": "VisualItem",
          "_label": "Lessons for shaving!!! [graphic]"
        }
      ],
      "identified_by": [
        {
          "type": "Identifier",
          "content": "796.04.16.02++ [Lewis Walpole Library]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Lessons for shaving!!! [graphic]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "At the Library",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300133046",
              "type": "Type",
              "_label": "Access Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        },
        {
          "type": "LinguisticObject",
          "content": "1 print : etching on wove paper, hand-colored ; plate mark 34.8 x 48 cm, on sheet 38 x 50 cm",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435452",
              "type": "Type",
              "_label": "Physical Statement",
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
              "content": "Physical Description",
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
      ],
      "subject_of": [
        {
          "type": "LinguisticObject",
          "_label": "Text of Repository Page",
          "digitally_carried_by": [
            {
              "type": "DigitalObject",
              "_label": "Repository Page",
              "access_point": [
                {
                  "id": "https://search.library.yale.edu/catalog/9777342",
                  "type": "DigitalObject"
                }
              ]
            }
          ]
        }
      ],
      "member_of": [
        {
          "id": "https://lux.collections.yale.edu/data/set/e8647339-0041-4eeb-bd83-079f931e9e06",
          "type": "Set",
          "_label": "Special Collections (YUL)"
        }
      ],
      "produced_by": {
        "type": "Production",
        "part": [
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/6a4346f3-b238-47d4-a6d0-980c21c0a307",
                "type": "Person",
                "_label": "Woodward, G. M. (George Moutard), approximately 1760-1809"
              }
            ]
          }
        ]
      }
    }
    ```

4.  `DigitalObject → digitally_carries → LinguisticObject` \[`6546882`\]

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/object/e161c7e7-7a78-4976-8774-0de867c3222d",
      "type": "DigitalObject",
      "_label": "ZYX and his fairy, or, The soul in search of peace [electronic resource]",
      "digitally_carries": [
        {
          "id": "https://lux.collections.yale.edu/data/text/7210e343-ce9d-4853-8454-a7c4e88644db",
          "type": "LinguisticObject",
          "_label": "ZYX and his fairy, or, The soul in search of peace [electronic resource]"
        }
      ]
    }
    
    ```

5.  `DigitalObject → digitally_shows → VisualItem` \[`12237283`\]

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/object/ed9af261-e373-40fa-8248-48afb62eb3c2",
      "type": "DigitalObject",
      "_label": "Sarah Malcolm [graphic] : executed in Fleet Street, March the 7th 1733 for robbing [the] chambers of Mrs. Lydia Duncomb in [the] Temple, & murdering her, Eliz. Harrison, & Ann Price",
      "digitally_shows": [
        {
          "id": "https://lux.collections.yale.edu/data/visual/8cf565ab-f2ad-4af2-9840-c18f36d6fe08",
          "type": "VisualItem",
          "_label": "Sarah Malcolm [graphic] : executed in Fleet Street, March the 7th 1733 for robbing [the] chambers of Mrs. Lydia Duncomb in [the] Temple, & murdering her, Eliz. Harrison, & Ann Price"
        }
      ]
    }
    ```

6.  Standalone `DigitalObject` \[`12244893`\]

    ```
    {
      "id": "https://lux.collections.yale.edu/data/digital/0283cba8-169b-4950-bb88-5ba3cdd4ca1d",
      "type": "DigitalObject",
      "_label": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年)",
      "identified_by": [
        {
          "type": "Identifier",
          "content": "QC990.J32 H576 2014 CD [Library Shelving Facility (LSF)]",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300311706",
              "type": "Type",
              "_label": "Call Number"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)",
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
          "content": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ],
          "language": [
            {
              "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
              "type": "Language",
              "_label": "und"
            }
          ]
        },
        {
          "type": "Name",
          "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404672",
              "type": "Type",
              "_label": "Sorting Name"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Record-level entities](../concepts/record_level_entities.md)

