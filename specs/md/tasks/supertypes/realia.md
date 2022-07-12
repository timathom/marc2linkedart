---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Realia

Three-dimensional items not covered by more specific terms \(e.g., clothing, stitchery, fabrics, tools, utensils\), and naturally occurring objects.

## Source data

```
---
name: Realia
sampleBibs:
  - 9088029
fieldSpec: 
  - ldr[6]
  - 008[33]
  - 006[0]
  - 006[16]
```

## Processing steps and output

```
---
# Realia mapping
conditions:
  OR:
    - AND:
      # Three-dimensional artifact or naturally occurring object
      - - ldr[6]
        - r 
      - OR:
        # Realia
        - - 008[33]
          - r
        # Other type of material
        - - 008[33]
          - z
    - AND:
      # 3-D artifact
      - - 006[0]
        - r
      - OR:
        # Realia
        - - 006[16]
          - r
        # Other type of material
        - - 006[16]
          - z
```

```
{
  "classified_as": [
    {
      "id": "http://id.loc.gov/vocabulary/marcgt/rea",
      "type": "Type",
      "_label": "Realia",
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

