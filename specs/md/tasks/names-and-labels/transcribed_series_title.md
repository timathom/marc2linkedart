---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: 
---

# Transcribed series title

Transcribed series title of a record-level entity. Taken from MARC `440` or `490`.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: TranscribedSeriesTitle
sampleBibs:
  - 242
fieldSpec:
  - 444anpv
  - 490av
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Join the string values of the `444` or `490` subfields with a whitespace character.

    `242`

    ```
    {
      "identified_by": [
        {
          "type": "Name",
          "content": "Rinehart editions, 136",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300417214",
              "type": "Type",
              "_label": "Series Title"
            },
            {
              "id": "http://vocab.getty.edu/aat/300404333",
              "type": "Type",
              "_label": "Transcribed Title"
            }        
          ]
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

