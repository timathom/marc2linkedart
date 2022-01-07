---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Books

Long form texts, divided into sections and/or the physical, paged objects that carry them.

## Source data

```
---
name: Books
sampleBibs:
  - 7778409
fieldSpec:
  - ldr[6]
  - ldr[7]
  - 008[21]
  - 006[0]
  - 035a
```

## Processing steps and output

```
---
# Books mapping
conditions:
  OR:
    - AND:
      # Language material
      - - ldr[6]
        -  a
      # Monograph component part
      - - ldr[7]
        - a
    - AND:
      # Language material
      - - ldr[6]
        - a
      # Serial component part
      - - ldr[6]
        - b
      - OR:
        # Updating looseleaf
        - - 008[21]
          - l
        # Monographic series
        - - 008[21]
          - m
    - AND:
      # Language material
      - - ldr[6]
        - a
      # Integrating resource
      - - ldr[7]
        - i
      # Updating looseleaf
      - - 008[21]
        - l
    - AND:
      # Language material
      - - ldr[6]
        - a
      # Monograph/item
      - - ldr[7]
        - m
    - AND:
      # Language material
      - - ldr[6]
        - a
      # Serial
      - - ldr[7]
        - s
      - OR:
        # Updating looseleaf
        - - 008[21]
          - l
        # Monographic series
        - - 008[21]
          - m
    # Books
    - - 006[0]
      - a
  NOT:
    - 035a contains 'yuldbase'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300028051",
      "type": "Type",
      "_label": "Books",
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

-   **[Atlases](../../tasks/supertypes/atlases.md)**  
Volumes of maps, with or without descriptive text, which may be issued to supplement or accompany texts or be published independently.

**Parent topic:**[Textual Works](../../tasks/supertypes/textualformats.md)

