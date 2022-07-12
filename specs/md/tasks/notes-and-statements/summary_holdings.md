---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Summary holdings note

This specification applies to holdings records that contain `866` fields with textual holdings notes.

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
  - mfhd866a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  If the carrier-level record contains multiple `866` fields, join the string value of all `866a` values with an escaped newline character \(`\\n`\).

2.  Output a summary holdings note with the value from `866a`.


`13867637 [MFHD]`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "v.6(1812)-v.17:pt.1(1845),\\nv.18(1848),\\nv.20(1853)-v.32(1887),\\nv.35(1890)-v.41(1906),\\nv.44(1910)-v.59(1939),\\nv.62(1949/1951)-v.69:no.3(1973),\\nv.69:no.9(1974)-v.70:no.1/3(1977)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300411780",
          "type": "Type",
          "_label": "Description",
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
          "content": "Summary Holdings Note",
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

