---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Provenance statement

|Domains|Usage|
|-------|-----|
|`HumanMadeObject`|Do not repeat on related`LinguisticObject`.|
|`HumanMadeObject`|Do not repeat on related`VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing`Set`.|

## Source data

```
---
name: ProvenanceStatement
sampleBibs:
  - 3811379
fieldSpec:
  - 5613a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the provenance statement values \(MARC`5613a`\).

    1.  Join the string values of`5613a`with a whitespace character.

    2.  If subfield`3`is present, but does not appear first in the subfield sequence, prefix the statement with the value of subfield`3`.

    3.  Test the value of`3`to see whether it ends with a colon.

    4.  If no colon is present, concatenate the value with a colon \(`:`\).

    5.  Else, output the value of subfield`3`.

    ```
    561  $3 Copy 1: $a Purchased from Michael D. Heaston Co. on the Winlock William Miller, Jr. Memorial Fund, 1989.
    561  $3 Copy 2: $a Purchased from William Reese Company on the Frederick W. & Carrie S. Beinecke Fund for Western Americana, 1998.
    ```

    **Note:** This example is meant to illustrate a provenance statement and does not represent a complete JSON-LD document.

    `3811379`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "Copy 1: Purchased from Michael D. Heaston Co. on the Winlock William Miller, Jr. Memorial Fund, 1989.",
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
          "content": "Copy 2: Purchased from William Reese Company on the Frederick W. & Carrie S. Beinecke Fund for Western Americana, 1998.",
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
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

