---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Databases

A dataset, structured according to a particular piece of software's requirements.

## Source data

```
---
name: Databases
sampleBibs:
  - 13077939
fieldSpec:
  - 035a
```

## Processing steps and output

```
---
# Databases mapping
conditions:
  - 035a contains 'yuldbase'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028543",
      "type": "Type",
      "_label": "Databases",
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

**Parent topic:**[Software and Electronic Media](../../concepts/supertypes/softwareformats.md)

