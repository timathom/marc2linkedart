---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Motion Pictures

## Source data

```
---
name: MotionPictures
sampleBibs:
  - 9441132
fieldSpec:
  - ldr[6]
  - 008[33]
  - 006[0]
  - 006[1]
  - 007[0]
  - 007[1]
```

## Processing steps and output

```
---
# Video mapping
conditions:
  OR:
    - AND:
      # Projected medium
      - - ldr[6]
        - c            
      - OR:
        # Motion picture
        - - 008[33]
          - m
        # Video recording
        - - 008[33]
          - v
    - AND:
      # Project medium
      - - 006[0]
        - g
      - OR:
        # Motion picture
        - - 006[1]
          - m
        # Video recording
        - - 006[1]
          - v
    - AND:
      # Projected graphic
      - - 007[0]
        - g
      - OR:
        # Filmstrip cartridge
        - - 007[1]
          - c
        # Filmslip
        - - 007[1]
          - d
        # Filmstrip, type unspecified
        - - 007[1]
          - f
        # Filmstrip roll
        - - 007[1]
          - o
    # Motion picture
    - - 007[0]
      - m
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300136900",
      "type": "Type",
      "_label": "Motion Pictures",
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

**Parent topic:**[Moving Images](../../tasks/supertypes/movingimageformats.md)

