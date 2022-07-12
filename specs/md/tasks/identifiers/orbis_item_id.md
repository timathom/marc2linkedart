---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [, , ]
---

# Voyager item ID

The Voyager item ID is a serially based identifier assigned to item records in the Voyager ILS.

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: VoyagerItemId
sampleMfhds:
  - 12104059
fieldSpec: NA
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Get value of item ID and prepend with `ils:yul:item:`.

2.  For each [Carrier-level record](../../glossary/carrier_level_record.md) that corresponds to an item record, output the item record identifier.


`12104059`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "ils:yul:item:12104059",
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

