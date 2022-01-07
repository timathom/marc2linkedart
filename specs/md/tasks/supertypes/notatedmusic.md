---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Notated Music

## Source data

```
---
name: NotatedMusic
sampleBibs:
  - 786701
fieldSpec:
  - ldr[6]
  - 006[0]
  - 336a
  - 336b
```

## Processing steps and output

```
---
# Notated Music mapping
conditions:
  OR:
    # Notated music
    - - ldr[6]
      - c
    # Manuscript notated music
    - - ldr[6]
      - d
    # Printed music
    - - 006[0]
      - c
    # Manuscript music
    - - 006[d]
      - d
    # Notated music
    - - 336a
      - notated music
    - - 336b
      - ntm
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300417622",
      "type": "Type",
      "_label": "Notated Music",
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

**Parent topic:**[Scores and Notation](../../tasks/supertypes/notationformats.md)

