---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Publisher or Distributor Number

Formatted number used for sound recordings, printed music, other music-related materials, and video recordings.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: PublisherOrDistributorNumber
sampleBibs:
  - 4
  - 3802861
  - 15589896
fieldSpec: 028abq
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Get value of `028a`.

2.  Process `028b`.

    1.  If the value of `028b` begins and ends with open/closing parentheses, return the value.

    2.  Else, concatenate the value with open/closing parentheses.

    3.  Join the values of `028a` and `028b` with a whitespace character.

3.  Process any `028q` \(qualifying information\) values.

    1.  If 2 or more `028q`: join values with a whitespace character.

    2.  If the value of `028q` begins and ends with open/closing parentheses, return the value.

    3.  Else, concatenate the value with open/closing parentheses.

    4.  Join `028q` with `028a + 028b` using a whitespace character.

4.  Output JSON-LD with the Publisher or Distributor Number:


`1730032`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "M301356 (MGM/UA Home Video)",
      "classified_as": [
        {
          "id": "TBD",
          "type": "Type",
          "_label": "Publisher/Distributor Number"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[028 \(Publisher or Distributor Number\)](../../tables/028_bib_table.md)

