---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
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
          "id": "http://vocab.getty.edu/aat/300435443",
          "type": "Type",
          "_label": "Type of Object"
        }
      ]
    }
  ]    		
}
```

**Parent topic:**[Audio Works](../../tasks/supertypes/audioformats.md)

