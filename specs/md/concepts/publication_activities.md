---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Publication activities

Activities with information from `26X` fields.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|

## Source data

```
---
name: PublicationActivities
sampleBibs:
  - 358058
fieldSpec:  
  - 260abc
  - 264|**|abc
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

Publication activities incorporate information from the `008` and `26X` fields.

-   Mappings for `008` are specified in [Places from fixed field 008](places_from_fixed_field_008.md) and [008 dates](../tasks/dates/008_dates.md)
-   Mappings for `26X` are specified in [Production statement](../tasks/notes-and-statements/production_statement.md) and [26X dates](../tasks/dates/26X_dates.md) \(as a fallback when no `008` date is present\).

In addition, place and agent information from `26X` fields should be included as provisional references within publication activities.

Although information recorded in `26X` fields is uncontrolled, exposing it will allow it to be processed and potentially reconciled by the LUX data enrichment pipeline.

1.  Process each `26X` field.

    `260` may contain multiple `abc` subfields. A semicolon \(`;`\) is used when `$a` is followed by another `$a`.

2.  If `260` includes a semicolon, split the field on the semicolon. Each group is a `subfield set`.

3.  For each `26X` field or `subfield set`, generate a publication activity using the `used_for` property.

    If there is more than one `26X` field, attach the publication-related information derived from `008` to the **first** activity in the sequence.

4.  For `26Xa`:

    1.  [Normalize](../glossary/normalization.md) the subfield value.

    2.  Add a blank node using the `took_place_at` property, with the subfield as the value of `_label`.

    `3`

    ```
    260  $a México : $b Instituto Nacional de Antropología e Historia, $c 1979.
    ```

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
            },
            {
              "type": "Place",
              "_label": "México"
            }
          ],
          "timespan": {
            "type": "TimeSpan",
            "begin_of_the_begin": "1878-01-01T00:00:00Z",
            "end_of_the_end": "1879-01-01T00:00:00Z",
            "identified_by": [
              {
                "type": "Name",
                "content": "1878",
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

5.  For `26Xb`:

    1.  [Normalize](../glossary/normalization.md) the subfield value.

    2.  Add a blank node using the `carried_out_by` property, with a type of `Actor` and with the subfield as the value of `_label`.

    `3`

    ```
    260  $a México : $b Instituto Nacional de Antropología e Historia, $c 1979.
    ```

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
          "carried_out_by": [
            {
              "type": "Actor",
              "_label": "Instituto Nacional de Antropología e Historia"
            }
          ]
          "took_place_at": [
            {
              "id": "https://lux.collections.yale.edu/data/place/3dcbc9fa-ca9c-4fa1-bd0e-d25e93f461e5",
              "type": "Place"
            },
            {
              "type": "Place",
              "_label": "México"
            }
          ],
          "timespan": {
            "type": "TimeSpan",
            "begin_of_the_begin": "1878-01-01T00:00:00Z",
            "end_of_the_end": "1879-01-01T00:00:00Z",
            "identified_by": [
              {
                "type": "Name",
                "content": "1878",
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

6.  If the field is `264|*4|` with only `$c` \(to record the copyright date\), do not generate an activity. Instead, apply the instructions in [Copyright entities](copyright_entity.md).


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

