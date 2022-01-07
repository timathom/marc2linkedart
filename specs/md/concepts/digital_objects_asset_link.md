---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: []
---

# Digital object link to asset

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related`HumanMadeObject`.|
|`VisualItem`|Do not repeat on related`HumanMadeObject`.|
|`Set`|Do not repeat on nested`members_exemplified_by → HumanMadeObject`.|
|`DigitalObject`| |

## Source data

```
---
name: DigitalObjectAsset
sampleBibs:
  - 358058
fieldSpec:  
  - 856uy
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  Output a `DigitalObject` link to a related digital asset using the URI recorded in `856u`.

    `358058`

    ```
    {
      "referred_to_by": [
        {
          "id": "http://hdl.handle.net/10079/4qrfjh5",
          "type": "DigitalObject"
        }
      ]
    }
    ```


**Parent topic:**[Embedded entities](../concepts/lux_embedded_entities.md)

**Previous topic:**[Digital object link to catalog](../concepts/digital_objects.md)

