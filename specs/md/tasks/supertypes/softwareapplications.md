---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Software Applications

## Source data

```
---
name: SoftwareApplications
sampleBibs:
  - 12244893
fieldSpec:
  - ldr[6]
  - 035a
  - 336a
```

## Processing steps and output

```
---
# Software Applications mapping
conditions:
  # Computer file
  - - ldr[6]
    - m
  - NOT:
    - - 090a
      - yuldset
    - - 035a contains 'yuldbase'
    - - 336a
      - computer datasets
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028566",
      "type": "Type",
      "_label": "Software Applications",
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

**Parent topic:**[Software and Electronic Media](../../tasks/supertypes/softwareformats.md)

