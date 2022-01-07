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
|`HumanMadeObject`|Do not repeat on related `LinguisticObject` or `VisualItem`.|
|`DigitalObject`| |
|`Set → members_exemplified_by → HumanMadeObject`|Do not repeat on containing `Set`.|

## Source data

```
---
name: LocationsAndCallNumbers
sampleBibs:
  - 3
  - 9447
fieldSpec:
  - mfhd852bhim
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Prepare the Voyager location code lookup table, which contains mappings between location codes and their corresponding names.

    ```
    {
      "LOCATION_MAP_FACET": "Beinecke Rare Book and Manuscript Library",
      "ORBIS_LOCATION_CODE": "beingen"
    }
    ```

2.  For each `852` field that contains a subfield `b`, select the value of subfield `b`.

3.  If field `852` does not contain a subfield `b`, skip the `852` field.

    **Note:** This instruction is temporary. At some point, other MFHD fields should also be processed.

4.  [Normalize](../../glossary/normalization.md) the value of subfield `b` and test whether it is equal to `withdrawn` or `suppressed`.

5.  If the value is equal to either `withdrawn` or `suppressed`, skip the `852` field.

6.  If the normalized value of subfield `b` starts with `yulint`, there is no call number.

    **Note:** MFHDs with an `852b` value of `yulint` or `yulintx` should be converted to `DigitalObject` carrier resources. See [Content and carriers](../content_and_carriers.md).

7.  Select and save the value of subfield `b`.

    1.  Match the value of subfield `b` against the location code lookup table and save the value of the `location_name`.

    2.  Surround the value of the `location_name` with square brackets.

        `[Library Shelving Facility (LSF)]`

8.  Select and save the value of subfield `h`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

9.  Select and save the value of subfield `i`.

    1.  [Normalize](../../glossary/normalization.md) the value.

    2.  If the value contains “\(lc\)”, select the original substring before “\(lc\)” and trim whitespace.

10. Select and save the value of subfield `m`.

11. Join the values of subfields `852him` with a whitespace character. This is the `call_number`.

12. Concatenate the `call_number` with the `location_name`.


`12244893`

```
{
  "id": "https://lux.collections.yale.edu/data/digital/0283cba8-169b-4950-bb88-5ba3cdd4ca1d",
  "type": "DigitalObject",
  "_label": "弘前藩庁日記ひろひよみ : 気象・災害等の記述を中心に. Vol.2, (1741年-1868年)",
  "identified_by": [
    {
      "type": "Identifier",
      "content": "QC990.J32 H576 2014 CD [Library Shelving Facility (LSF)]",
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
    },
    {
      "type": "Name",
      "content": "Hirosaki hanchō nikki hiroiyomi : kishō saigai nado no kijutsu o chūshin ni. Vol.2, (1741-nen-1868-nen)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404672",
          "type": "Type",
          "_label": "Sorting Name"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

