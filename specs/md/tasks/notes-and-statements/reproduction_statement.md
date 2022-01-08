---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Reproduction statement

|Domains|Usage|
|-------|-----|
|`HumanMadeObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: ReproductionStatement
sampleBibs:
  - 485171
  - 11178775
fieldSpec:
  - 5333abcdefn
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the acquisition statement values \(MARC `5333abcdefn`\).

    1.  Join the string values of `5333abcdefn` with a whitespace character.

    2.  If subfield `3` is present, but does not appear first in the subfield sequence, prefix the statement with the value of subfield`3`.

    3.  Test the value of `3` to see whether it ends with a colon.

    4.  If no colon is present, **trim punctuation** and concatenate the value with a colon \(`:`\).

    5.  Else, output the value of subfield`3`.

    ```
    533  $3 Logbooks, 1799-1805 $a Microfilm. $b [Washington, D.C.] : $c The Library of Congress Photoduplication Service, $d 1982. $e 1 microfilm reel ; 35 mm. $f (Papers of Edward Preble, 1680-1912 ; no. 18,525)
    ```

    **Note:** This example is meant to illustrate a reproduction statement and does not represent a complete JSON-LD document.

    `11178775`

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

