---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed]
---

# Collages

Works in two dimensions or very low relief that were made by gluing paper, fabrics, photographs, or other materials onto a flat surface.

## Source data

```
---
name: Collages
sampleBibs:
  - 7647390
fieldSpec: 
  - ldr[6]
  - 006[0]
  - 007[0]
  - 007[1]
  - 300a
  - 655a
```

## Processing steps and output

```
---
# Collages mapping
conditions:
  OR:  
    # Two-dimensional nonprojectable graphic
    - - ldr[6]
      - k
    # Two-dimensional nonprojectable graphic
    - - 006[0]
      - k
  AND:
    - OR:      
      - AND:             
        # Nonprojected graphic
        - - 007[0]
          - k
        # Collage
        - - 007[1]
          - c
      - lower-case(300a) contains 'collage'
      - lower-case(655a) contains 'collage'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300033963",
      "type": "Type",
      "_label": "Collages",
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

**Parent topic:**[Visual Works](../../tasks/supertypes/imageformats.md)

