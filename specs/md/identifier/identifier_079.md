# 079 \(Local System Control Number: OCLC\)

Control number of a system other than the one whose control number is contained in field 001 \(Control Number\), field 010 \(Library of Congress Control Number\) or field 016 \(National Bibliographic Agency Control Number\).

Usage: ~8 million values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|079|Local System Control Number: OCLC|Undefined|Undefined|a|Local system control number|F|

```

---
examples:
  # Voyager BIB IDs for testing
  - [907208]
input:
  - 079$a
trim:
  - whitespace  
                    
```

1.  Process `079$a`.

    1.  `079$a`: trim whitespace.

    2.  Normalize `079$a` \(lower case and remove punctuation characters\) to test the value.

    3.  If the normalized value of `079$a` starts with "oc", return the original \(whitespace-trimmed\) value.

    4.  Else, skip.

2.  Output JSON with values for OCLC number.


BIB ID: 907208

```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "ocm36682480",
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

