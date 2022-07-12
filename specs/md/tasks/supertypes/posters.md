---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: [Assigned, Completed, Deployed]
---

# Posters

Notices, usually decorative or pictorial, intended to be posted to advertise, promote, or publicize an activity, cause, product, or service; also, decorative, mass-produced prints intended for hanging. For small printed notices or advertisements intended for distribution by hand, use "handbills."

## Source data

```
---
name: Posters
sampleBibs:
  - 11221175
fieldSpec:
  - 007[0]
  - 007[1]
  - 300a
  - 650v
  - 655a
```

## Processing steps and output

```
---
# Posters mapping
conditions:
  OR:
    - AND:    
      # Nonprojected graphic
      - - 007[0]
        - k
      # Poster
      - - 007[1]
        - k
    - lower-case(300a) contains 'poster'
    - lower-case(650v) contains 'posters'
    - lower-case(655a) contains 'posters'
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300027221",
      "type": "Type",
      "_label": "Posters",
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

**Parent topic:**[Visual Works](../../tasks/supertypes/imageformats.md)

