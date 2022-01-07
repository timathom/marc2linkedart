---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Dissertations and Theses

Texts written for the purpose of fulfilling an academic requirement.

## Source data

```
---
name: DissertationsAndTheses
sampleBibs:
  - 7456365
fieldSpec:
  - ldr[6]
  - 008[24-27]
  - 502a
```

## Processing steps and output

```
---
# Dissertations and Theses mapping
conditions:
  OR:
    - OR:
      # Language material
      - - ldr[6]
        - a
      # Manuscript language material
      - - ldr[6]
        - t
      - AND:
        # Theses
        - - 008[24-27] contains 'm'
    - 502a exists
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028028",
      "type": "Type",
      "_label": "Dissertations and Theses",
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

**Parent topic:**[Textual Works](../../concepts/supertypes/textualformats.md)

