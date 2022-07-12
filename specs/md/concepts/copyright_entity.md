---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Copyright entities

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|

## Source data

```
---
name: CopyrightEntities
sampleBibs:
  - 693
fieldSpec:  
  - 264|*4|c
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  If `008[06]` has a value of `t`, then use the `008` date to generate a copyright entity, as specified in [008 dates](../tasks/dates/008_dates.md).

2.  Else, for each `264|*4|` with only `$c`, generate a copyright entity.

3.  If the value of `264|*4|c` starts with a copyright symbol, preserve the symbol in the value of `content`.

4.  If the value of `264|*4|c` starts with a copyright symbol, strip the copyright symbol to generate date/time values using the `begin_of_the_begin` and `end_of_the_end` properties.

    `693`

    ```
    264 4 $c ©1970
    ```

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
              "begin_of_the_begin": "1970-01-01T00:00:00Z",
              "end_of_the_end": "1971-01-01T00:00:00Z",
              "identified_by": [
                {
                  "type": "Name",
                  "content": "©1970",
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


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

