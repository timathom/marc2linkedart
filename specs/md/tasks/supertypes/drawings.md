---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Drawings

Visual works produced by drawing, typically by the application of lines on a surface, often paper, by using a pencil, pen, chalk, or some other tracing instrument to focus on the delineation of form rather than the application of color.

## Source data

```
---
name: Drawings
sampleBibs:
  - 12903124
fieldSpec: 
  - ldr[6]
  - 006[0]
  - 007[0]
  - 007[1]
  - 300a
  - 650v
  - 655a
```

## Processing steps and output

```
---
# Drawings mapping
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
        - OR:
          # Drawing
          - - 007[1]
            - d
          # Technical drawing
          - - 007[1]
            - l              
      - lower-case(300a) contains 'drawing'
      - lower-case(650v) contains 'drawing'
      - lower-case(655a) contains 'drawings'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300033973",
      "type": "Type",
      "_label": "Drawings",
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

**Parent topic:**[Visual Works](../../tasks/supertypes/imageformats.md)

