---
author: [tt434, timothy.thompson@yale.edu, tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Image Data

## Source data

```
---
name: ImageData
sampleBibs:
  - 14624188
fieldSpec: 090a
```

## Processing steps and output

```
---
# Image Data mapping
conditions:
    - 090a
    - yuldsetimg
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300215302",
      "type": "Type",
      "_label": "Image Data",
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

**Parent topic:**[Data and Files](../../concepts/supertypes/dataandfiles.md)

**Parent topic:**[Visual Works](../../concepts/supertypes/imageformats.md)

