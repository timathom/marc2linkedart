---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Music

## Source data

```
---
name: Music
sampleBibs:
  - 7780497
fieldSpec: 
  - ldr[6]
  - 006[0]
```

## Processing steps and output

```
---
# Music mapping
conditions:
  OR:    
    # Musical sound recording
    - - ldr[6]
      - j
    - - 006[0]
      - j
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300054146",
      "type": "Type",
      "_label": "Music",
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

**Parent topic:**[Audio](../../concepts/supertypes/audioformats.md)

