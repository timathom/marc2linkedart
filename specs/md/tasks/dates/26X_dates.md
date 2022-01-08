---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# 26X dates

Date values from a `26X` field.

## Source data

```
---
name: DatesFrom26X
sampleBibs:
  - 16098 # No 260c
  - 31529 # Single copyright date
  - 201837 # 1906-07
  - 62220 # [19]77
  - 2644136 # 189--
  - 3032778 # $a ... 1906-
  - 3110258 # 190? 
  - 4381238 # 18??
  - 5755117 # Single pub date
  - 8893226 # 1935-36 (v. 2: 1936)
  - 9088768 # 19XX
  - 10599527 # 1921/22-
  - 11398609 # Two 264
  - 11437005 # between 1900 and 1950?
  - 12605060 # Three 264
  - 12836744
  - 13814148 # 1937?-
  - 15569643 # $b ... (1903-1908)
  - 15569670 # $b ... (1907-1944) ... (1924-26)
# Source data fields
fieldSpec:
  - 260abc
  - 264| *|abc
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

A relatively small number of records lack a date value in the `008[07-14]` positions, but may contain date information in a `26X` field \(i.e., `260` or `264`\).

Typically, `26Xc` is used to record date information; however, a small number of records lack this subfield, but still contain date information. Example \(`16098`\):

```
260 0 $a Rio de Janeiro] SPVEA [Seção de Documentação e Relações Públicas, $b 1965]
```

As of November 2021, 39,485 records lacked a date value in the `008[07-14]` positions, but included date information in a `26X` field:

|Date in 26Xc|Date in 26X \(not $c\)|260|264|Total|
|------------|----------------------|---|---|-----|
|37,592|1,893|36,734|2,598|39,485|

Correctly parsing `26X` date information is challenging because the values represent a wide variety of data entry practices. Although the majority of records contain a single year in the `26X` field, there are many exceptions. The following example shows a record with no `008` date and three `264` fields with date information \(`12605060`\):

```
264 1 $a Milano : $b Dall'Oglio, $c [1986]
264 3 $a Varese : $b La Tipografica Varese S.p.A., $c 1986.
264 4 $c ©1976
```

Here, the first date \(`264 1`\) represents the date of publication, supplied by the cataloger; the second date \(`264 3`\) represents the date of manufacture \(printing\); and the third date \(`264 4`\) represents the copyright date. In older records, the copyright date may be supplied in the same `260` field as the publication date and preceded by the letter `c` \(`3315`\):

```
260  $a Berkeley, $b University of California Press [1971, c1967]
```

Imprecise dates are typically represented by hyphens \(`-`\) to substitute unknown digits. Uncertain dates are followed by a trailing question mark \(`?`\). However, a question mark or `X` may also be used to substitute unknown digits, and hyphens are also used to indicate date ranges. See the table below for examples.

**Illustrative \(but not comprehensive\) list of possible date forms:**

**\#1**

-   **ID**

    1

-   **Type**

    Publication or creation

-   **Description**

    Single known date of publication or creation

-   **Example**

    `260 $a Roma : $b Transmedia, $c 1982.`

-   **Bib**

    5755117


**\#2**

-   **ID**

    2

-   **Type**

    Copyright

-   **Description**

    Single copyright date given as implicit date of publication

-   **Example**

    `260 $a Geneve : Bureau international du travail, $c c1975.`

-   **Bib**

    31529


**\#3**

-   **ID**

    3

-   **Type**

    Publication and copyright

-   **Description**

    Publication and copyright dates in the same field

-   **Example**

    `260 $a Berkeley, $b University of California Press [1971, c1967]`

-   **Bib**

    3315


**\#4**

-   **ID**

    4

-   **Type**

    Publication and copyright

-   **Description**

    Publication and copyright dates in separate fields

-   **Example**

    ```
    264 1 $a [Buffalo, N.Y.] $b White Pine Press Signature Editions, $c [1996] 
    264 4 $c ©1996
    ```

-   **Bib**

    11866836


**\#5**

-   **ID**

    5

-   **Type**

    Imprecise publication or creation

-   **Description**

    Single imprecise date of publication or creation

-   **Example**

    `260 $a Canberra : $b Pacific Manuscripts Bureau, $c [19--]`

-   **Bib**

    12366270


**\#6**

-   **ID**

    6

-   **Type**

    Uncertain publication or creation

-   **Description**

    Single uncertain date of publication or creation

-   **Example**

    `264 1 $a [Bangkok], $c [2013?]`

-   **Bib**

    12332284


**\#7**

-   **ID**

    7

-   **Type**

    Hyphenated publication or creation range \(open\)

-   **Description**

    Date range of publication or creation with no end date

-   **Example**

    `260 $a Göteborg : P. Åströms förlag, $c 1978-`

-   **Bib**

    39579


**\#8**

-   **ID**

    8

-   **Type**

    Imprecise hyphenated publication or creation range \(open\)

-   **Description**

    Imprecise date range of publication or creation with no end date

-   **Example**

    `260 $a W Krakowie, W. L. Anczyc, $c 189--`

-   **Bib**

    2644136


**\#9**

-   **ID**

    9

-   **Type**

    Hyphenated publication or creation range \(closed\)

-   **Description**

    Date range of publication with end date

    **Note:** Date ranges may be expressed as two four-digit years or as a four-digit year followed by a two-digit continuation.

-   **Example**

    `260 0 $a Madrid, $b Bailly-Bailliére é hijos, $c 1906-07.`

-   **Bib**

    201837


**\#10**

-   **ID**

    10

-   **Type**

    Unhyphenated publication or creation range \(closed\)

-   **Description**

    Date range of publication with end date

-   **Example**

    `260 $a [Vietnam], $c [between 1900 and 1950?]`

-   **Bib**

    11437005


**\#11**

-   **ID**

    11

-   **Type**

    Manufacture \(printing\)

-   **Description**

    Single date of manufacture \(typically printing\)

-   **Example**

    `264 3 $a Varese : $b La Tipografica Varese S.p.A., $c 1986.`

-   **Bib**

    12605060


1.  Use the supertype value of the record-level resource to determine the default `generic_date_type` represented by the `26X` value.

    -   If the record-level supertype is one of the following:

        -   Any `Objects` format
        -   Any `Visual Works` format
        -   `Archival and Manuscript Materials`
        -   `Dissertations and Theses`
        then the default `generic_date_type` is `creation`.

    -   Else, the default `generic_date_type` is `publication`.
2.  Save the `generic_date_type` value for subsequent processing.

3.  Construct a `TimeSpan` object to store the date value for [\#1](26X_dates.md#_1), [\#5](26X_dates.md#_5), and [\#6](26X_dates.md#_6) above.

    -   **Conditions**
        -   **`generic_date_type`**

            publication/creation

    1.  Extract the publication or creation date using an appropriate regular expression.

    2.  If the `generic_date_type` is `publication`, output a `Publishing` activity.

        `12332284`

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
                  "id": "https://lux.collections.yale.edu/data/place/118e6df1-607d-41a1-93d9-4cd6eae69d6d",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "2013-01-01T00:00:00Z",
                "end_of_the_end": "2014-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "2013",
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
            }
          ]
        }
        ```

    3.  If the `generic_date_type` is `creation`, output a `Creation` activity.

        `4391062`

        **Note:** This example is provided to demonstrate the `Creation` pattern, but does not represent a `26X` date.

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/7dbd0827-cefd-4569-92e5-b1f54b8f497c",
                    "type": "Person",
                    "_label": "Hansberry, Lorraine, 1930-1965"
                  }
                ],
                "classified_as": [
                  {
                    "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                    "type": "Type",
                    "_label": "Creator"
                  }
                ]
              }
            ],
            "timespan": {
              "type": "TimeSpan",
              "begin_of_the_begin": "1958-01-01T00:00:00Z",
              "end_of_the_end": "1959-01-01T00:00:00Z",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "1958",
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
          }
        }
        ```

4.  Construct a `TimeSpan` object to store the date value for [\#2](26X_dates.md#_2), [\#3](26X_dates.md#_3), and [\#4](26X_dates.md#_4) above.

    -   **Conditions**
        -   **`generic_date_type`**

            publication

    1.  Extract the publication and/or copyright date using an appropriate regular expression.

    2.  Output a `Publishing` activity.

        `31529`

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
                  "id": "https://lux.collections.yale.edu/data/place/a406f5e8-90c5-4734-9f9c-e8ad3726aac9",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1975-01-01T00:00:00Z",
                "end_of_the_end": "1976-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1975",
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
            }
          ]
        }
        ```

    3.  Output a `Copyright` entity.

        `31529`

        ```
        {
          "subject_to": [
            {
              "type": "Right",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300055598",
                  "type": "Type",
                  "_label": "Copyright"
                }
              ],
              "created_by": {
                "type": "Creation",
                "timespan": {
                  "type": "TimeSpan",
                  "begin_of_the_begin": "1975-01-01T00:00:00Z",
                  "end_of_the_end": "1976-01-01T00:00:00Z",
                  "identified_by": [
                    {
                      "type": "Name",
                      "content": "1975",
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
              }
            }
          ]
        }
        ```

5.  Construct a `TimeSpan` object to store the date value for [\#7](26X_dates.md#_7) and [\#8](26X_dates.md#_8) above.

    -   **Conditions**
        -   **`generic_date_type`**

            publication/creation

    1.  Extract the publication or creation date using an appropriate regular expression.

        Open date ranges should not include an `end_of_the_end` property.

    2.  If the `generic_date_type` is `publication`, output a `Publishing` activity.

        `2644136`

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
                  "id": "https://lux.collections.yale.edu/data/place/b878202d-365d-4a2d-a176-e8a50ed2773c",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1890-01-01T00:00:00Z",        
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1890-",
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
            }
          ]
        }
        ```

    3.  If the `generic_date_type` is `creation`, output a `Creation` activity.

        `4391062`

        **Note:** This example is provided to demonstrate the `Creation` pattern, but does not represent a `26X` date.

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/7dbd0827-cefd-4569-92e5-b1f54b8f497c",
                    "type": "Person",
                    "_label": "Hansberry, Lorraine, 1930-1965"
                  }
                ],
                "classified_as": [
                  {
                    "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                    "type": "Type",
                    "_label": "Creator"
                  }
                ]
              }
            ],
            "timespan": {
              "type": "TimeSpan",
              "begin_of_the_begin": "1958-01-01T00:00:00Z",      
              "identified_by": [
                {
                  "type": "Name",
                  "content": "1958-",
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
          }
        }
        ```

6.  Construct a `TimeSpan` object to store the date value for [\#9](26X_dates.md#_9) and [\#10](26X_dates.md#_10) above.

    -   **Conditions**
        -   **`generic_date_type`**

            publication/creation

    1.  Extract the publication or creation date using an appropriate regular expression.

    2.  If the `generic_date_type` is `publication`, output a `Publishing` activity.

        `201837`

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
                  "id": "https://lux.collections.yale.edu/data/place/a9ec9299-f33c-4fcb-b7b1-30ec5e2f4a9c",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1906-01-01T00:00:00Z",
                "end_of_the_end": "1908-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1906-1907",
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
            }
          ]
        }
        ```

    3.  If the `generic_date_type` is `creation`, output a `Creation` activity.

        `4391062`

        **Note:** This example is provided to demonstrate the `Creation` pattern, but does not represent a `26X` date.

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/7dbd0827-cefd-4569-92e5-b1f54b8f497c",
                    "type": "Person",
                    "_label": "Hansberry, Lorraine, 1930-1965"
                  }
                ],
                "classified_as": [
                  {
                    "id": "https://lux.collections.yale.edu/data/concept/9d2c734e-afd3-44bd-972d-8cf441423edc",
                    "type": "Type",
                    "_label": "Creator"
                  }
                ]
              }
            ],
            "timespan": {
              "type": "TimeSpan",
              "begin_of_the_begin": "1958-01-01T00:00:00Z",
              "end_of_the_end": "1960-01-01T00:00:00Z",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "1958-1959",
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
          }
        }
        ```

7.  [\#11](26X_dates.md#_11), above, is not yet mapped.


**Parent topic:**[Dates](../../tasks/dates/dates.md)

