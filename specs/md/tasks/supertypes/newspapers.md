---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Newspapers

Serials published at stated, frequent intervals, such as daily or weekly, and containing news, editorials, features, advertisements, and other items of current interest.

## Source data

```
---
name: Newspapers
sampleBibs:
  - 1495840
fieldSpec:
  - ldr[6]
  - ldr[7]
  - 008[21]
  - 006[0]
  - 006[4]
```

## Processing steps and output

```
---
# Newspapers mapping
conditions:
  OR:
    - AND:
      # Language material
      - - ldr[6]
        - a
      - OR:
        # Serial component part
        - - ldr[7]
          - b
        # Serial
        - - ldr[7]
          - s
      # Newspaper
      - - 008[21]
        - n
    - AND:
      # Serial control
      - - 006[0]
        - s
      # Newspaper
      - - 006[4]
        - n
    - OR:
      - lower-case(760t) contains 'newspaper'
      - lower-case(830a) contains 'newspaper'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300026656",
      "type": "Type",
      "_label": "Newspapers",
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

**Parent topic:**[Journals and Periodicals](../../tasks/supertypes/journalsandperiodicals.md)

