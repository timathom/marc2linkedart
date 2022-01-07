---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Textual Data

## Source data

```
---
name: TextualData
sampleBibs:
  - 4941452
fieldSpec: 
  - 090a
```

## Processing steps and output

```
---
# Image Data mapping
conditions:
    - 090a
    - yuldsettxt
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300418050",
      "type": "Type",
      "_label": "Textual Data",
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

**Parent topic:**[Data and Files](../../tasks/supertypes/dataandfiles.md)

**Parent topic:**[Textual Works](../../tasks/supertypes/textualformats.md)

