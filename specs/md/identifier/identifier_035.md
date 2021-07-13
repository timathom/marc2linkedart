# 035 \(System Control Number: OCLC\)

Control number of a system other than the one whose control number is contained in field 001 \(Control Number\), field 010 \(Library of Congress Control Number\) or field 016 \(National Bibliographic Agency Control Number\).

Usage: ~29 million values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|035|System Control Number: OCLC|Undefined|Undefined|a|System control number|F|
|035|System Control Number: OCLC|Undefined|Undefined|z|Canceled/invalid control number|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [2395, 15589736]
input:
  - 035$a
  - 035$z
trim:
  - whitespace  
                    
```

1.  Do not capture `035$z` \(canceled/invalid control number\).

2.  Process `035$a`.

    1.  `035$a`: trim whitespace.

    2.  Normalize `035$a` \(lower case and remove punctuation characters\) to test the value.

    3.  If the normalized value of `035$a` starts with "oc", return the original \(whitespace-trimmed\) value.

    4.  Else, skip.

3.  Output JSON with values for OCLC number.


BIB ID: 2395

```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "(OCoLC)ocm00213132",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    },
    {
      "type": "Identifier",
      "content": "(OCoLC)ocn687654227",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    },
    {
      "type": "Identifier",
      "content": "(OCoLC)213132",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300404621",
          "type": "Type",
          "_label": "Owner-Assigned Number"
        }
      ],
      "attributed_by": [
        {
          "type": "AttributeAssignment",
          "carried_out_by": [
            {
              "type": "Group",
              "_label": "OCLC"
            }
          ]
        }
      ]
    }
  ]
                        
```

**Parent topic:**[Identifier Entity](../identifier/identifier.md)

