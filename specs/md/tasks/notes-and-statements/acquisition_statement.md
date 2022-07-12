---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Acquisition statement

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: AcquisitionStatement
sampleBibs:
  - 431
  - 58130
fieldSpec:
  - 541|1 |3abcdefn
  - 541|  |3abcdefn
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the acquisition statement values \(MARC `5413abcdefn`\).

    1.  Join the string values of `5413abcdefn` with a whitespace character.

    2.  If subfield `3` is present, but does not appear first in the subfield sequence, prefix the statement with the value of subfield`3`.

    3.  Test the value of `3` to see whether it ends with a colon.

    4.  If no colon is present, **trim punctuation** and concatenate the value with a colon \(`:`\).

    5.  Else, output the value of subfield `3`.

    ```
    541  $3 DIV copy 2; $c Gift; $a Gift of Marvin H. Pope; $d 1999.
    ```

    **Note:** This example is meant to illustrate an acquisition statement and does not represent a complete JSON-LD document.

    `58130`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "DIV copy 2: Gift; Div copy Gift of Marvin H. Pope; 1999.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300435439",
              "type": "Type",
              "_label": "Acquisition Statement",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

