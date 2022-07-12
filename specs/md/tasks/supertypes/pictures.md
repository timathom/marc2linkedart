---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Pictures

Catch-all category for resources that contain some kind of pictorial content, but a more specific kind cannot be determined from the mapping.

## Source data

```
---
name: Pictures
sampleBibs
  - 9855433
fieldSpec: 
  - ldr[6]
  - 006[0]
  - 007[0]
  - 007[1]
  - 090a
  - 300a
  - 336ab
  - 655a
```

## Processing steps and output

```
---
# Pictures mapping
conditions:
  OR:  
    # Two-dimensional nonprojectable graphic
    - - ldr[6]
      - k
    # Two-dimensional nonprojectable graphic
    - - 006[0]
      - k
    # Nonprojected graphic
    - - 007[0]
      - k
    # Still image
    - - 336a
      - still image
    - - 336b
      - sti
    - lower-case(650v) contains 'pictorial works'
    - lower-case(650v) contains 'caricatures and cartoons'
    - lower-case(650v) contains 'charts, diagrams, etc.'
    - lower-case(650v) contains 'illustrations'
    - lower-case(650v) contains 'in art'
    - lower-case(650v) contains 'portraits'
  NOT:         
    # Collage
    - - 007[1]
      - c
    - lower-case(300a) contains 'collage'
    - lower-case(655a) contains 'collage'
    # Painting
    - - 007[1]
      - e
    - lower-case(300a) contains 'painting'
    - lower-case(655a) contains 'painting'
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
    - lower-case(650v) contains 'photographs'
    - lower-case(655a) contains 'photo
    # Poster
    - - 007[1]
      - k
    - lower-case(300a) contains 'poster'
    - lower-case(650v) contains 'posters'
    - lower-case(655a) contains 'posters'
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
    # Image Data
    - - 090a
      - yuldsetimg
```

```
{
  "classified_as": [
    {
       "id": "http://id.loc.gov/vocabulary/marcgt/pic",
      "type": "Type",
      "_label": "Pictures",
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

