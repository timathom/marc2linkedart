---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Library of Congress Control Number \(LCCN\)

The Library of Congress Control Number is a serially based identifier assigned to resources that also appear in the catalog of the Library of Congress.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: Lccn
sampleBibs:
  - 4
  - 3802861
  - 15589896
fieldSpec: 010a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Get value of`010a`.

2.  Output JSON-LD with theLCCN:


`4`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "66010930",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300417440",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "Library of Congress"
            }
          ]
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[010 \(Library of Congress Control Number\)](../../tables/010_bib_table.md)

