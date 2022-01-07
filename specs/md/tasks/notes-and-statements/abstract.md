---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Abstract

Corresponds to the`520`note field in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: Abstract
sampleBibs:
  - 18
fieldSpec:
  - 520a
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Process the abstract values \(MARC`520a`\).

    |JSON structure|Description|Default|
    |--------------|-----------|-------|
    |`root → referred_to_by → type`| |`LinguisticObject`|
    |`root → referred_to_by → content`|String value of MARC`520a`subfield| |
    |`root → referred_to_by → classified_as → id`|IRI of the concept used to classify the statement|[http://vocab.getty.edu/aat/300026032](http://vocab.getty.edu/aat/300026032)|
    |`root → referred_to_by → classified_as → type`| |`Type`|
    |`root → referred_to_by → classified_as → _label`|Label of the concept used to classify the statement|`Abstract`|
    |`root → referred_to_by → classified_as → classified_as → id`|IRI of the concept used to classify the kind of statement|[http://vocab.getty.edu/aat/300418049](http://vocab.getty.edu/aat/300418049)|
    |`root → referred_to_by → classified_as → classified_as → type`| |`Type`|
    |`root → referred_to_by → classified_as → classified_as → _label`| |`Brief Text`|
    |`root → referred_to_by → identified_by → type`| |`Name`|
    |`root → referred_to_by → identified_by → content`| |`Summary, Etc.`|
    |`root → referred_to_by → identified_by → classified_as → id`|IRI of the concept used to classify the statement name|[http://vocab.getty.edu/aat/300404669](http://vocab.getty.edu/aat/300404669)|
    |`root → referred_to_by → identified_by → classified_as → type`| |`Type`|
    |`root → referred_to_by → identified_by → classified_as → _label`|Label of the concept used to classify the statement name|`Display Title`|

    **Note:** This example is meant to illustrate an abstract and does not represent a complete JSON-LD document.

    `18`

    ```
    {
      "referred_to_by": [
        {
          "type": "LinguisticObject",
          "content": "A boy grows to manhood while attempting to subdue the evil he unleashed on the world as an apprentice to the Master Wizard.",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300026032",
              "type": "Type",
              "_label": "Abstract",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300418049",
                  "type": "Type",
                  "_label": "Brief Text"
                }
              ]
            }
          ],
          "identified_by": [
            {
              "type": "Name",
              "content": "Summary, Etc.",
              "classified_as": [
                {
                  "id": "http://vocab.getty.edu/aat/300404669",
                  "type": "Type",
                  "_label": "Display Title"
                }
              ]
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

