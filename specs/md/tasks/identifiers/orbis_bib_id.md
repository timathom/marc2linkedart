---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Voyager BIB ID

The Voyager BIB ID is a serially based identifier assigned to MARC 21 Bibliographic records in the Voyager ILS.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: VoyagerBibId
sampleBibs:
  - 2
  - 3
  - 4
fieldSpec: 001
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Get value of `001` and prepend with `ils:yul:`.

2.  Output JSON-LD with the Voyager BIB ID:


`2`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "ils:yul:2",
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

**Related information**  


[001 \(Control Number\)](../../tables/001_bib_table.md)

