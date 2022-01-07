---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
keyword: Assigned
---

# Broadsides

## Source data

```
---
name: Broadsides
sampleBibs:
  - 6642610
fieldSpec:
  - 300a
  - 500a
  - 655a
  - MFHD 852hik
```

## Processing steps and output

```
---
# Broadsides mapping
conditions:
  OR:
    - 300a contains 'broadside'    
    - AND:
      - 300a contains 'sheet'
      - OR:
        - 500a contains 'broadsheet'
        - 500a contains 'broadside'
        - 500a contains 'broad-side'
    - lower-case(655a) contains 'broadside'
    - lower-case(MFHD 852h) contains 'brside'
    - lower-case(MFHD 852i) contains 'brside'
    - lower-case(MFHD 852k) contains 'brside'
  NOT:
    - 035a contains 'yuldbase'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300026739",
      "type": "Type",
      "_label": "Broadsides",
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

**Parent topic:**[Textual Works](../../tasks/supertypes/textualformats.md)

