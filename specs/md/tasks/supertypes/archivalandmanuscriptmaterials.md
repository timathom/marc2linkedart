---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Archival and Manuscript Materials

## Source data

```
---
name: ArchivalAndManuscriptMaterials
sampleBibs:
  - 3779671
fieldSpec:
  - ldr[6]
  - 006[0]
  - 655a
  - 690a
```

## Processing steps and output

```
---
# Archival and Manuscript Materials mapping
conditions:
  OR:
    # Manuscript notated music
    - - ldr[6]
      - d
    # Manuscript cartographic material
    - - ldr[6]
      - f
    # Mixed materials
    - - ldr[6]
      - p
    # Manuscript language materials
    - - ldr[6]
      - t
    # Manuscript music
    - - 006[0]
      - d
    # Manuscript map
    - - 006[0]
      - f
    # Mixed materials
    - - 006[0]
      - p
    # Manuscript language
    - - 006[0]
      - t
    # Genre heading
    - lower-case(655a) contains 'manuscript'
    # Local genre heading
    - lower-case(690a) contains 'manuscript'
```

```
{
  "classified_as": [    
    {
      "id": "http://vocab.getty.edu/aat/300375748",
      "type": "Type",
      "_label": "Archival and Manuscript Materials",
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

**Parent topic:**[Collections](../../tasks/supertypes/collectionformats.md)

