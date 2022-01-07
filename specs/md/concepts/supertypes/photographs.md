---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Photographs

Refers to still images produced from radiation-sensitive materials generally by means of the chemical action of light on a sensitive film, paper, glass, or metal.

## Source data

```
---
name: Photographs
sampleBibs:
  - 6734224
fieldSpec: 
  - 007[0]
  - 007[1]
  - 300a
  - 650v
  - 655a
```

## Processing steps and output

```
---
# Photographs mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      - OR:
        # Photomechanical print
        - - 007[1]
          - f          
        # Photonegative
        - - 007[1]
          - g
        # Photoprint
        - - 007[1]
          - h
        # Radiograph
        - - 007[1]
          - r
        # Photograph, type unspecified
        - - 007[1]
          - v
    - lower-case(300a) contains 'photograph'
    - lower-case(650v) contains 'photograph'
    - lower-case(655a) contains 'photo'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300046300",
      "type": "Type",
      "_label": "Photographs",
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

**Parent topic:**[Visual Works](../../concepts/supertypes/imageformats.md)

