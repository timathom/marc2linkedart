---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# 008 dates

Date values from `008` fixed field.

## Source data

```
---
name: DatesFrom008
sampleBibs:
  - 37273
  - 1203615
  - 1260604
  - 4391062
  - 10598048
  - 11167038
  - 12989258
# Source data fields
fieldSpec:
  - 008[06]
  - 008[07-14]
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

`008[06]` is used to record the specific type of date or publication status. `008[07-14]` contains one or two date values.

1.  Use the supertype value of the record-level resource to determine the default `generic_date_type` represented by the `008[07-14]` values.

    -   If the record-level supertype is one of the following:

        -   Any `Objects` format
        -   Any `Visual Works` format
        -   `Archival and Manuscript Materials`
        -   `Dissertations and Theses`
        then the default `generic_date_type` is `creation`.

    -   Else, the default `generic_date_type` is `publication`.
2.  Save the `generic_date_type` value for subsequent processing.

3.  Perform an additional check \(`journal_test`\) to test whether the supertype is `Journals`.

4.  Save the `journal_test` as a boolean value for subsequent processing.

5.  Select the `specific_date_type` from `008[06]`.

6.  Save the `specific_date_type` for subsequent processing.

7.  Process the date values in `008[07-10]` and `008[11-14]` to test for non-numeric characters \(e.g., `\s` \[whitespace\], `u`, `x`, `\|` \[pipe\]\).

8.  For each date value, replace the regular expression `[\sA-Za-z\|]` with `?`.

9.  Save the values as `date_1_temp` and `date_2_temp`.

10. Process the first date value and save as `date_1_val`.

    -   If `date_1_temp` contains only `?` characters, `date_1_val` is `false`.
    -   Else, replace the regular expression `\?` with `0` in `date_1_temp` as the value of `date_1_val`.
11. Process the second date value and save as `date_2_val`.

    -   If `date_2_temp` contains only `?` characters, `date_2_val` is `false`.
    -   Else, if `date_2_temp` is equal to `9999`, then set the value of `date_2_val` to `9999`.
    -   Else, replace the regular expression `\?` in `date_2_temp` with `9` as the value of `date_2_val`.
12. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

            -   **OR**
                -   **`specific_date_type`**

                    `e`

                -   **AND**
                    -   **`specific_date_type`**

                        `d`

                    -   **`journal_test`**

                        `false`

    ```
    
    if ($date_1_val castable as integer and $date_2_val castable as integer)
    then
      if ($generic_date_type == "e" or ($generic_date_type == "d" and $journal_test == false))
        ...
    
    ```

    1.  Analyze `date_2_val` using the regular expression `.{2}`.

    2.  Join the string value of the resulting matches that are **not** equal to `99` with a hyphen \(`-`\).

    3.  Save the resulting string value as `detailed_date`.

    4.  Concatenate `date_1_val` with `detailed_date` using a hyphen \(`-`\) \(e.g., `1983-06-15`\).

    5.  Save the value as `content`.

    6.  Construct a `dateTime` value by concatenating `date_1_val` with `-01-01T00:00:00Z`.

    7.  Save the result as `begin_of_the_begin`.

    8.  Increment the year value of `begin_of_the_begin` by one and save the value as `end_of_the_end`.

        -   **008\[06\] \(specific\_date\_type\)**

            e

        -   **generic\_date\_type**

            creation

        -   **008\[07-10\]**

            `1794`

        -   **008\[11-14\]**

            `06`

        `10598048`

        ```
        {
          "created_by": {
            "type": "Creation",    
            "timespan": {
              "type": "TimeSpan",
              "begin_of_the_begin": "1794-01-01T00:00:00Z",
              "end_of_the_end": "1795-01-01T00:00:00Z",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "1794-06",
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

13. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

            -   **`specific_date_type`**

                `t`

    1.  Save `date_1_val` as `content`.

    2.  Construct a `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    3.  Save the result as `begin_of_the_begin`.

    4.  Increment the year value of `begin_of_the_begin` by one and save the value as `end_of_the_end`.

    5.  Assign `date_1_val` to a publication activity.

        -   **008\[06\] \(specific\_date\_type\)**

            t

        -   **generic\_date\_type**

            publication

        -   **008\[07-10\]**

            `2016`

        -   **008\[11-14\]**

            `2011`

        `12989258`

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
                  "id": "https://lux.collections.yale.edu/data/place/8673efd5-7e74-4e6c-a6ed-d30ea0ba9260",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "2016-01-01T00:00:00Z",
                "end_of_the_end": "2017-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "2016",
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

    6.  Save `date_2_val` as `content`.

    7.  Construct a `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    8.  Save the result as `begin_of_the_begin`.

    9.  Increment the year value of `begin_of_the_begin` by one and save the value as `end_of_the_end`.

    10. Assign `date_2_val` to a `copyright` entity.

        -   **008\[06\] \(specific\_date\_type\)**

            t

        -   **generic\_date\_type**

            publication

        -   **008\[07-10\]**

            `2016`

        -   **008\[11-14\]**

            `2011`

        `12989258`

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
                  "begin_of_the_begin": "2011-01-01T00:00:00Z",
                  "end_of_the_end": "2012-01-01T00:00:00Z",
                  "identified_by": [
                    {
                      "type": "Name",
                      "content": "2011",
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

14. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

            -   **`specific_date_type`**

                `r`

    1.  Save `date_1_val` as `content`.

    2.  Construct a `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    3.  Save the result as `begin_of_the_begin`.

    4.  Increment the year value of `begin_of_the_begin` by one and save the value as `end_of_the_end`.

    5.  Assign `date_1_val` to a `publishing` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            r

        -   **generic\_date\_type**

            publication/creation

        -   **008\[07-10\]**

            `1995`

        -   **008\[11-14\]**

            `1958`

        `4391062`

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
                  "id": "https://lux.collections.yale.edu/data/place/8673efd5-7e74-4e6c-a6ed-d30ea0ba9260",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1995-01-01T00:00:00Z",
                "end_of_the_end": "1996-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1995",
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

    6.  Save `date_2_val` as `content`.

    7.  Construct an `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    8.  Save the result as `begin_of_the_begin`.

    9.  Increment the year value of `begin_of_the_begin` by one and save the value as `end_of_the_end`.

    10. For `date_2_val`, override the default value of generic\_date\_type and assign `date_2_val` to a `creation` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            r

        -   **generic\_date\_type**

            publication/creation

        -   **008\[07-10\]**

            `1995`

        -   **008\[11-14\]**

            `1958`

        `4391062`

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

15. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

                **NOT** `9999`

            -   **`generic_date_type`**

                `any`

            -   **`specific_date_type`**

                `any`

    1.  Take the minimum value of `date_1_val` and `date_2_val`.

    2.  Save minimum value as `min_content`.

    3.  Take the maximum value of `date_1_val` and `date_2_val`.

    4.  Save the maximum value as `max_content`.

    5.  Concatenate `min_content` and `max_content` with a hyphen \(`-`\).

    6.  Save the resulting value as `content`.

    7.  Construct an `dateTime` value by concatenating `min_content` with `-01-01T00:00:00Z`.

    8.  Save the result as `begin_of_the_begin`.

    9.  Increment the year value of `begin_of_the_begin` by one.

    10. Save the value as `end_of_the_end`.

    11. Construct an `dateTime` value by concatenating `end_of_the_end` with `-01-01T00:00:00Z`.

    12. If `generic_date_type` is `creation`, assign the dates to an `assembling` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            i

        -   **generic\_date\_type**

            creation

        -   **008\[07-10\]**

            `1401`

        -   **008\[11-14\]**

            `1599`

        `11167038`

        ```
        {
          "used_for": [
            {
              "type": "Activity",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300077121",
                  "type": "Type",
                  "_label": "Assembling"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1401-01-01T00:00:00Z",
                "end_of_the_end": "1600-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1401-1599",
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

    13. If `generic_date_type` is `publication`, assign the dates to a `publishing` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            q

        -   **generic\_date\_type**

            publication

        -   **008\[07-10\]**

            `1820`

        -   **008\[11-14\]**

            `1829`

        `1260604`

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
                  "id": "https://lux.collections.yale.edu/data/place/9ebe78d5-0a21-427b-a9f1-b170e453d513",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1820-01-01T00:00:00Z",
                "end_of_the_end": "1830-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1820-1829",
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

16. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

                `9999`

            -   **`generic_date_type`**

                `publication`

            -   **`specific_date_type`**

                `any`

    1.  Concatenate `date_1_val` with a hyphen \(`-`\).

    2.  Save the resulting value as `content`.

    3.  Construct a `dateTime` value by concatenating `content` with `01-01T00:00:00Z`.

    4.  Save the result as `begin_of_the_begin`.

    5.  Do not construct a value for `end_of_the_end`.

    6.  Assign the date to a `publishing` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            u

        -   **generic\_date\_type**

            creation

        -   **008\[07-10\]**

            `1966`

        -   **008\[11-14\]**

            `9999`

        `37273`

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
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1966-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1966-",
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

17. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                castable as `integer`

            -   **`data_2_val`**

                **NOT** castable as `integer`

            -   **`generic_date_type`**

                `publication`

            -   **`specific_date_type`**

                `any`

    1.  Save `date_1_val` as `content`.

    2.  Construct a `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    3.  Save the result as `begin_of_the_begin`.

    4.  Assign the date to a `publishing` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            s

        -   **generic\_date\_type**

            publication

        -   **008\[07-10\]**

            `1966`

        -   **008\[11-14\]**

            `[none]`

        `1203615`

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
                  "id": "https://lux.collections.yale.edu/data/place/8673efd5-7e74-4e6c-a6ed-d30ea0ba9260",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1948-01-01T00:00:00Z",
                "end_of_the_end": "1949-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1948",
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

18. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                **NOT** castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

            -   **`generic_date_type`**

                `any`

            -   **`specific_date_type`**

                `any`

    1.  Concatenate `date_1_val` with a hyphen \(`-`\).

    2.  Save the resulting value as `content`.

    3.  Construct a `dateTime` value by concatenating `content` with `01-01T00:00:00Z`.

    4.  Save the result as `begin_of_the_begin`.

    5.  Do not construct a value for `end_of_the_end`.

    6.  Assign the date to a `creation` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            r

        -   **generic\_date\_type**

            publication/creation

        -   **008\[07-10\]**

            `[none]`

        -   **008\[11-14\]**

            `1909`

        `247158`

        ```
        {
          "created_by": {
            "type": "Creation",
            "part": [
              {
                "type": "Creation",
                "carried_out_by": [
                  {
                    "id": "https://lux.collections.yale.edu/data/person/6239d9cf-f4d5-4c93-9837-2243bca31a8a",
                    "type": "Person",
                    "_label": "Godart, Justin, 1871-"
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
              "begin_of_the_begin": "1909-01-01T00:00:00Z",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "1909-",
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

19. Construct a `TimeSpan` object to store the date values.

    -   **Conditions**
        -   **AND**
            -   **`date_1_val`**

                **NOT** castable as `integer`

            -   **`data_2_val`**

                castable as `integer`

            -   **`generic_date_type`**

                `any`

            -   **`specific_date_type`**

                **NOT** `r`

    1.  Save `date_2_val` as `content`.

    2.  Construct a `dateTime` value by concatenating `content` with `-01-01T00:00:00Z`.

    3.  Save the result as `begin_of_the_begin`.

    4.  Assign the date to a `publishing` activity.

        -   **008\[06\] \(specific\_date\_type\)**

            q

        -   **generic\_date\_type**

            publication

        -   **008\[07-10\]**

            `[none]`

        -   **008\[11-14\]**

            `1960`

        `128548`

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
                  "id": "https://lux.collections.yale.edu/data/place/e7f47055-ea75-4e41-8c27-6bb4b075b4cc",
                  "type": "Place"
                }
              ],
              "timespan": {
                "type": "TimeSpan",
                "begin_of_the_begin": "1960-01-01T00:00:00Z",
                "end_of_the_end": "1961-01-01T00:00:00Z",
                "identified_by": [
                  {
                    "type": "Name",
                    "content": "1960",
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


**Parent topic:**[Dates](../../tasks/dates/dates.md)

