---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Number of parts

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject`.|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: NumberOfParts
sampleMfhds:
  - 13867637
fieldSpec:
  - NA
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Count the total number of item records attached each holdings record.

2.  Output the value as an integer using the `number_of_parts` property.


`13867637 [MFHD]`

```
{
  "number_of_parts": 104
}
```

**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

