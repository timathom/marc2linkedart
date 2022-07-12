---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: 
---

# Alternative title

Alternative title of a record-level entity. Taken from MARC `246`.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: AlternativeTitle
sampleBibs:
  - 242
fieldSpec:
  - 246abfghinp
trimPunctuation: true
scriptInclusion: BOTH
```

## Processing steps and output

1.  Join the string values of the `246` subfields with a whitespace character.

    `242`

    ```
    {
      "identified_by": [
        {
          "type": "Name",
          "content": "English morality plays and moral interludes",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300417226",
              "type": "Type",
              "_label": "Alternative Title"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Names](../../tasks/names-and-labels/names.md)

