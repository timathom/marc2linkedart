---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Models

## Source data

```
---
name: Models
sampleBibs:
  - 9492648
fieldSpec: 
  - ldr[6]
  - 008[33]
  - 006[0]
  - 006[16]
```

## Processing steps and output

```
---
# Models mapping
conditions:
  OR:
    - AND:
      # Three-dimensional artifact or naturally occurring object
      - - ldr[6]
        - r 
      - OR:
        # Model
        - - 008[33]
          - q
        # Diorama
        - - 008[33]
          - d
    - AND:
      # 3-D artifact
      - - 006[0]
        - r
      - OR:
        # Model
        - - 006[16]
          - q
        # Diorama
        - - 006[16]
          - d
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300247279",
      "type": "Type",
      "_label": "Models",
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

**Parent topic:**[Objects](../../tasks/supertypes/objectformats.md)

