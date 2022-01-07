---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: [Assigned, Completed, Deployed]
---

# Journals and Periodicals

Works published in pieces over time, typically at regular intervals.

## Source data

```
---
name: JournalsAndPeriodicals
sampleBibs:
  - 4354486
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
# Journals and Periodicals mapping
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
      - NOT:
        # Updating looseleaf
        - - 008[21]
          - l
        # Monographic series
        - - 008[21]
          - m
        # Newspaper
        - - 008[21]
          - n
    # Serial control
    - - - 006[0]
        - s
      - NOT:
        # Newspaper
        - - 006[4]
          - n       
        - lower-case(760t) contains 'newspaper'
        - lower-case(830a) contains 'newspaper'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300215390",
      "type": "Type",
      "_label": "Journals and Periodicals",
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

-   **[Newspapers](../../tasks/supertypes/newspapers.md)**  
Serials published at stated, frequent intervals, such as daily or weekly, and containing news, editorials, features, advertisements, and other items of current interest.

**Parent topic:**[Textual Works](../../tasks/supertypes/textualformats.md)

