---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Notated Movement

## Source data

```
---
name: NotatedMovement
sampleBibs:
  - 5776020
fieldSpec:
  - 650a
```

## Processing steps and output

```
---
# Notated Movement mapping
conditions:
  - lower-case(650a) contains 'movement notation'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300417623",
      "type": "Type",
      "_label": "Notated Movement",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300226816",
          "type": "Type",
          "_label": "Format"
        }
      ]
    }
  ]    		
}
```

**Parent topic:**[Scores and Notation](../../concepts/supertypes/notationformats.md)

