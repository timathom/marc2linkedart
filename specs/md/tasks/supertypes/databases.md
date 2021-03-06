---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
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
          "id": "http://vocab.getty.edu/aat/300435443",
          "type": "Type",
          "_label": "Type of Object"
        }
      ]
    }
  ]    		
}
```

**Parent topic:**[Software and Electronic Media](../../tasks/supertypes/softwareformats.md)

