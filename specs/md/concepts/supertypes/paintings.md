---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu, tt434]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Paintings

Unique works in which images are formed primarily by the direct application of pigments suspended in oil, water, egg yolk, molten wax, or other liquid, arranged in masses of color, onto a generally two-dimensional surface.

## Source data

```
---
name: Paintings
sampleBibs:
  - 12433502
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
# Paintings mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      # Painting
      - - 007[1]
        - e
    - lower-case(300a) contains 'painting'
    - lower-case(655a) contains 'painting'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300033618",
      "type": "Type",
      "_label": "Paintings",
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

