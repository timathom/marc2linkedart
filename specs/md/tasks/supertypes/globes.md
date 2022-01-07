---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Globes

Representations of the Earth, heavens, or another planet in the form of a ball.

## Source data

```
---
name: Globes
sampleBibs:
  - 11416653
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
# Globes mapping
conditions:
  OR:
    - AND:
      # Globe      
      - - 008[25]
        - d
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
      # Globe
      - - 006[8]
        - d
    - AND:
      # Manuscript map
      - - 006[0]
        - f
      # Globe
      - - 006[8]
        - d
    # Globe
    - - 007[0]
      - d
    - lower-case(655a) contains 'globe'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028089",
      "type": "Type",
      "_label": "Globes",
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

**Parent topic:**[Cartography](../../tasks/supertypes/cartographicformats.md)

**Parent topic:**[Objects](../../tasks/supertypes/objectformats.md)

