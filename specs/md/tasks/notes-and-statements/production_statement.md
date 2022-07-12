---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: 
---

# Production statement

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: ProductionStatement
sampleBibs:
  - 31500
  - 3643333
fieldSpec:
  - 2603abcefg
  - 264|**|3abc
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  For each `26X` field, process the production statement values and generate a `Production Statement` within the `referred_to_by` array.

    1.  Do not trim punctuation from subfields.

    2.  Join subfields with a whitespace character.

    3.  If the field is `264|*4|` with only `$c` \(to record the copyright date\), do not generate a `Production Statement`. Instead, apply the instructions in [Copyright entities](../../concepts/copyright_entity.md).


**Note:** These examples are meant to illustrate production statements and do not represent complete JSON-LD documents.

`3643333`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "New York : Alfred A. Knopf, 1993, c1970",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435436",
          "type": "Type",
          "_label": "Production Statement",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ]
    }
  ]
}
```

`31500`

**Note:** This example is derived from a record with multiple `260` fields that include subfield `3` to refer to separate parts of the resource.

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "v. 1: Paris : Impr. et libr. administratives P. Dupont, 1878-<1954>",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435436",
          "type": "Type",
          "_label": "Production Statement",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ]
    },
    {
      "type": "LinguisticObject",
      "content": "v. 2:1: Avignon : Impr. et libr. administratives de Seguin frères.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435436",
          "type": "Type",
          "_label": "Production Statement",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ]
    },
    {
      "type": "LinguisticObject",
      "content": "v. 2:2-3:1: Avignon : F. Seguin.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435436",
          "type": "Type",
          "_label": "Production Statement",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ]
    },
    {
      "type": "LinguisticObject",
      "content": "v. 3:2-: Avignon : Archives départementales",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435436",
          "type": "Type",
          "_label": "Production Statement",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ]
    }
  ]
}
```

**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

