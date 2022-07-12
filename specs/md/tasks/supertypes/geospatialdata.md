---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Geospatial Data

## Source data

```
---
name: GeospatialData
sampleBibs:
  - 11909897
fieldSpec: 
  - ldr[6]
  - 008[25]
  - 006[0]
  - 006[8]
  - 007[0]
  - 655a
```

## Processing steps and output

```
---
# Geospatial Data mapping
conditions:
  OR:
    - AND:
      # Cartographic material
      - - ldr[6]
        - e
      # Electronic
      - - 008[28]
        - s
    # Remote sensing image
    - - 007[0]
      - r
    - - 090a
      - yuldsetgis
    - - 336a
      - cartographic dataset  
    - - 336b
      - crd    
    - lower-case(655a) contains 'geospatial'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300380194",
      "type": "Type",
      "_label": "Geospatial Data",
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

**Parent topic:**[Cartographic Works](../../tasks/supertypes/cartographicformats.md)

**Parent topic:**[Data and Files](../../tasks/supertypes/dataandfiles.md)

