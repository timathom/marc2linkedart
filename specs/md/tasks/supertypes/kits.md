---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Kits

“Mixture of various components issued as a unit and intended primarily for instructional purposes. No one component is identifiable as the predominant component of the item.”

## Source data

```
---
name: Kits
sampleBibs:
  - 8068082
fieldSpec: 
  - ldr[6]
  - 008[33]
  - 006[0]
```

## Processing steps and output

```
---
# Kits mapping
conditions:
  OR:
    # Kit
    - - ldr[6]
      - o
    - AND:
      # Three-dimensional artifact or naturally occurring object
      - - ldr[6]
        - r      
      # Kit
      - - 008[33]
        - b        				     
    # Kit
    - - 006[0]
      - o
```

```
{
  "classified_as": [    
    {
      "id": "http://vocab.getty.edu/aat/300247921",
      "type": "Type",
      "_label": "Kits",
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

**Parent topic:**[Collections](../../tasks/supertypes/collectionformats.md)

