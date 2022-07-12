---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Prints

Pictorial works produced by transferring images by means of a matrix such as a plate, block, or screen, using any of various printing processes.

## Source data

```
---
name: Prints
sampleBibs:
  - 8902194
fieldSpec: 
  - 007[0]
  - 007[1]
  - 300a
  - 655a
```

## Processing steps and output

```
---
# Prints mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      - OR:
        # Print
        - - 007[1]
          - j
        # Study print
        - - 007[1]
          - s
    - lower-case(300a) contains 'print'
    - lower-case(655a) contains 'lithograph'
    - - lower-case(655a) contains 'posters'
      - NOT:
        - lower-case(655a) contains 'photo'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300041273",
      "type": "Type",
      "_label": "Prints",
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

