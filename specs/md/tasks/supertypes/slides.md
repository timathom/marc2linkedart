---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Slides

An image on film or glass, usually positive, intended to be viewed by means of light passing through the image.

## Source data

```
---
name: Slides
sampleBibs:
  - 6491786
fieldSpec: 
  - ldr[6]
  - 008[33]
  - 006[0]
  - 006[16]
  - 007[0]
  - 007[1]
```

## Processing steps and output

```
---
# Slides mapping
conditions:
  OR:
    - AND:    
      # Projected medium
      - - ldr[6]
        - g
      - OR:
        # Microscope slide
        - - 008[33]
          - p
        # Slide
        - - 008[33]
          - s
        # Transparency
        - - 008[33]
          - t
    - AND:
      # Projected medium
      - - 006[0]
        - g
      - OR:
        # Microscope slide
        - - 006[16]
          - p
        # Slide
        - - 006[16]
          - s
        # Transparency
        - - 006[16]
          - t
    - AND:
      # Projected graphic
      - - 007[0]
        - g
      - OR:
        # Slide
        - - 007[1]
          - s
        # Transparency
        - - 007[1]
          - t
```

```
{
  "classified_as": [
    {
       "id": "http://vocab.getty.edu/aat/300128371",
      "type": "Type",
      "_label": "Slides",
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

