---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, ]
---

# Locations and call numbers

Locations and call numbers are derived from MARC holdings records \(MFHDs\).

|Domains|Usage|
|-------|-----|
|`HumanMadeObject` `DigitalObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`Set → members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: LocationsAndCallNumbers
sampleMfhds:
  - 
fieldSpec:
  - mfhd852bhimk
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  For each [carrier-level record](../../glossary/carrier_level_record.md), extract the call number.

2.  For each `852` field that contains a subfield `b`, select and save the value of subfield `b`.

3.  If field `852` does not contain a subfield `b`, skip the `852` field.

4.  [Normalize](../../glossary/normalization.md) the value of subfield `b` and test whether it is equal to `withdrawn` or `suppressed`.

5.  If the value of subfield `b` is equal to either `withdrawn` or `suppressed`, skip the `852` field.

6.  If the value of subfield `b` is equal to `yulint` or `yulintx`, generate a `DigitalObject` carrier resource.

    See [Content and carriers](../content_and_carriers.md) for more information.

    MFHDs with a subfield `b` value of `yulint` or `yulintx` will not have an associated item record.

    Subfield `b` with a value of `yulint` should not have a call number \(i.e., a value of `None` in subfield `h`\).

    However, subfield `b` with a value of `yulintx` may include call number information \(e.g., when the MFHD represents a digital copy of a digitized resource\).

    **Note:** MFHDs for digitized copies may be suppressed.

    1.  Extract the call number for \(suppressed\) MFHDs with a subfield `b` value of `yulintx`.

        `852 80 $b yulintx $k SUPPRESSED $k Folio $h 49 $i 3582 $m (Oversize)`

7.  Select and save the value of subfield `h`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

8.  Select and save the value of subfield `i`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

9.  Select and save the value of subfield `k`.

    Ignore any subfield `k` with a value of `SUPPRESSED`.

10. Select and save the value of subfield `m`.

11. If `852i` starts with a period \(`.`\), join the values of subfields `852hi` **without** a whitespace character.

    `852 01 $b lsf $h BL1840 $i .L84 2003 (LC)`

    ```
    {
      "type": "Identifier",
      "content": "BL1840.L84 2003",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300311706",
          "type": "Type",
          "_label": "Call Number"
        }
      ]
    }
    ```

12. Else, join the values of subfields `852hi` with a whitespace character.

    `852 00 $b lsf $h DS904 $i U66`

    ```
    {
      "type": "Identifier",
      "content": "DS904 U66",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300311706",
          "type": "Type",
          "_label": "Call Number"
        }
      ]
    }
    ```

13. Join `852hi` with `852km` \(if present\) with a whitespace character.

    Join `852km` in the order in which they appear.

    `852 80 $b lwl $k Folio $h 49 $i 3582 ‡m (Oversize)`

    ```
    {
      "type": "Identifier",
      "content": "Folio 49 3582 (Oversize)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300311706",
          "type": "Type",
          "_label": "Call Number"
        }
      ]
    }
    ```

14. The resulting value is the `call_number`.


`12416627 [MFHD]`

```
{
  "id": "https://lux.collections.yale.edu/data/digital/0283cba8-169b-4950-bb88-5ba3cdd4ca1d",
  "type": "DigitalObject",
  "_label": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年)",
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028566",
      "type": "Type",
      "_label": "Software Applications",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435443",
          "type": "Type",
          "_label": "Type of Object"
        }
      ]
    }
  ],
  "identified_by": [
    {
      "type": "Identifier",
      "content": "ils:yul:mfhd:12416627",
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "id": "https://lux.collections.yale.edu/data/group/yale-university-library",
              "type": "Group",
              "_label": "Yale University Library"
            }
          ]
        }
      ],
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435704",
          "type": "Type",
          "_label": "System-Assigned Number"
        }
      ]
    },
    {
      "type": "Identifier",
      "content": "QC990.J32 H576 2014 CD",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300311706",
          "type": "Type",
          "_label": "Call Number"
        }
      ]
    },
    {
      "type": "Name",
      "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404670",
          "type": "Type",
          "_label": "Primary Name"
        }
      ]
    },
    {
      "type": "Name",
      "content": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404670",
          "type": "Type",
          "_label": "Primary Name"
        }
      ],
      "language": [
        {
          "id": "https://lux.collections.yale.edu/data/concept/70cb6397-2b2f-400c-b887-70fd80969c8b",
          "type": "Language",
          "_label": "und"
        }
      ]
    }
  ],
  "number_of_parts": 1,
  "member_of": [
    {
      "id": "https://lux.collections.yale.edu/data/set/collection1",
      "type": "Set",
      "_label": "Yale University Library"
    }
  ],
  "digitally_carries": [
    {
      "id": "https://lux.collections.yale.edu/data/text/example-content1",
      "type": "LinguisticObject",
      "_label": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)"
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

