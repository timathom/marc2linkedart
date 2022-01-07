---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Toys and Games

## Source data

```
---
name: ToysAndGames
sampleBibs:
  - 8465357
fieldSpec: 
  - ldr[6]
  - 008[33]
  - 006[0]
  - 006[16]
  - 655a
```

## Processing steps and output

```
---
# Toys and Games mapping
conditions:
  OR:
    - AND:
      # Three-dimensional artifact or naturally occurring object
      - - ldr[6]
        - r 
      - OR:
        # Game
        - - 008[33]
          - g
        # Toy
        - - 008[33]
          - w				      
    - AND:
      # 3-D artifact
      - - 006[0]
        - r
      - OR:
        # Game
        - - 006[16]
          - g
        # Toy
        - - 006[16]
          - w
    # Genre heading
    - lower-case(655a) contains 'games'
```

```
{
  "classified_as": [    
    {
      "id": "http://vocab.getty.edu/aat/300218781",
      "type": "Type",
      "_label": "Toys and Games",
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

**Parent topic:**[Objects](../../tasks/supertypes/objectformats.md)

