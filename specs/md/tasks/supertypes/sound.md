---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Sound

## Source data

```
---
name: Sound
sampleBibs:
  - 11144096
fieldSpec: 
  - ldr[6]
  - 006[0]
  - 007[0]
```

## Processing steps and output

```
---
# Music mapping
conditions:
  OR:    
    # Musical sound recording
    - - ldr[6]
      - i
    - - 006[0]
      - i
    - - 007[0]
      - s
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300056060",
      "type": "Type",
      "_label": "Sound",
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

**Parent topic:**[Audio](../../tasks/supertypes/audioformats.md)

