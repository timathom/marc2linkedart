---
author: [tt434, timothy.thompson@yale.edu, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Data and Files

## Source data

```
---
name: DataAndFiles
sampleBibs:
  - 10086214
fieldSpec: 
  - 090a
  - 336ab
  - 655a
trimPunctuation: true
```

## Processing steps and output

```
---
# Data and Files mapping
conditions:
  OR:  
    - - 090a
      - - yuldset
        - yuldsetnum
    - - 336a
      - computer dataset
    - - 336b
      - cod
    - lower-case(655a) equals trim-punctuation('data sets')
  NOT:     
    - - 090a
      - - yuldsetgis
        - yuldsetimg          
        - yuldsettxt          
    - - 336a
      - cartographic dataset          
    - - 336b
      - crd          
    - lower-case(655a) contains 'geospatial'
    - lower-case(655a) equals trim-punctuation('text corpora')
```

```
{
  "classified_as": [
    {
      "id": "http://vocab.getty.edu/aat/300312038",
      "type": "Type",
      "_label": "Data and Files",
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

-   **[Geospatial Data](../../concepts/supertypes/geospatialdata.md)**  

-   **[Image Data](../../concepts/supertypes/imagedata.md)**  

-   **[Textual Data](../../concepts/supertypes/textualdata.md)**  


**Parent topic:**[Datasets](../../concepts/supertypes/dataformats.md)

