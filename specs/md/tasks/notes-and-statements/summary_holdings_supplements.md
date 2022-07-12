---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Supplementary material holdings note

This specification applies to holdings records that contain `86X` fields with textual holdings notes.

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: SummaryHoldingsStatement
sampleMfhds:
  - 13867637
fieldSpec:
  - mfhd867a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  If the carrier-level record contains multiple `867` fields, join the string value of all `867a` values with an escaped newline character \(`\\n`\).

2.  Output a supplementary material note with the value from `867a`.


`13867637 [MFHD]`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "v.14(1839):suppl.-v.15(1839):suppl.,\\nv.20(1853):suppl.,\\nv.22(1860):suppl.,\\nv.28(1879):suppl,\\n1883:Nov.:suppl.,\\nv.32(1887):suppl.,\\nv.35(1890):suppl.-v.40(1905):suppl.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300027363",
          "type": "Type",
          "_label": "Supplementary Material",
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
          "content": "Supplementary Material Note",
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
  ]
}
```

**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

