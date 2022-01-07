---
author: [tt434, timothy.thompson@yale.edu, tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Atlases

Volumes of maps, with or without descriptive text, which may be issued to supplement or accompany texts or be published independently.

## Source data

```
---
name: Atlases
sampleBibs:
  - 5607075
fieldSpec: 
  - ldr[6]
  - 008[25]
  - 006[0]
  - 006[8]
  - 007[0]
  - 650v
  - 655a
```

## Processing steps and output

```
---
# Atlases mapping
conditions:
  OR:
    - AND:
      # Atlas
      - - 008[25]
        - e        
      - OR:
        # Cartographic material
        - - ldr[6]
          - e
        # Manuscript cartographic material
        - - ldr[6]
          - f
    - AND:
      # Printed map
      - - 006[0]
        - e
      # Atlas
      - - 006[8]
        - e
    - AND:
      # Manuscript map
      - - 006[0]
        - f
      # Atlas
      - - 006[8]
        - e
    - AND:
      # Map
      - - 007[0]
        - a
      # Atlas
      - - 007[1]
        - d
    # Form subdivision
    - lower-case(650v) contains 'atlas'
    # Genre heading
    - lower-case(655a) contains 'atlas'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028053",
      "type": "Type",
      "_label": "Atlases",
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

**Parent topic:**[Cartography](../../concepts/supertypes/cartographicformats.md)

**Parent topic:**[Books](../../concepts/supertypes/books.md)

