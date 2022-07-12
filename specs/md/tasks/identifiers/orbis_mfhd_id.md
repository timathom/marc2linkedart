---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [, , ]
---

# Voyager MFHD ID

The Voyager MFHD ID is a serially based identifier assigned to MARC 21 Holdings records in the Voyager ILS.

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: VoyagerMfhdId
sampleMfhds:
  - 4082244
fieldSpec: NA
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Get value of MFHD ID and prepend with `ils:yul:mfhd:`.

2.  For each [Carrier-level record](../../glossary/carrier_level_record.md), output the MFHD identifier.


`4082244`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "ils:yul:mfhd:4082244",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435704",
          "type": "Type",
          "_label": "System-Assigned Number"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

