---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# International Standard Book Number \(ISBN\)

The International Standard Book Number \(ISBN\) is a publisher-assigned commercial book identifier that is intended to be unique. May appear in 10- or 13-digit formats.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: Isbn
sampleBibs:
  - 693
  - 8827
  - 3802857
  - 13101718
fieldSpec: 020aqz
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Skip`020`if`020z`\(canceled/invalid ISBN\).

2.  Get value of`020a`.

3.  Process any`020q`\(qualifying information\) values.

    1.  If 2 or more`020q`, join values with a whitespace character.

    2.  If value extracted from`020q`begins and ends with open/closing parentheses, return the value.

    3.  Else, concatenate the value with open/closing parentheses.

    4.  Join the values extracted from`020a`and`020q`with a whitespace character.

4.  Output JSON-LD with theISSN:


`13101718`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "9780227904787 (e-book)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300417443",
          "type": "Type",
          "_label": "ISBN Identifier"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[020 \(International Standard Book Number\)](../../tables/020_bib_table.md)

