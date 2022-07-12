---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Index holdings note

This specification applies to holdings records that contain `868` fields with textual holdings notes.

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
  - mfhd868a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  If the carrier-level record contains multiple `868` fields, join the string value of all `868a` values with an escaped newline character \(`\\n`\).

2.  Output an indexes note with the value from `868a`.


`13867637 [MFHD]`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "v.16(1849),\\nv.20(1853),\\nv.28(1879),\\nv.32(1887),\\nv.35(1890)-v.41(1906),\\nv.45(1908)-v.59(1939),\\nv.62(1949/1955)-v.63(1955/1959)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300054640",
          "type": "Type",
          "_label": "Indexes Note",
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
          "content": "Indexes Note",
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

