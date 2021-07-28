# 010 \(LCCN\)

The Library of Congress Control Number is a serially based identifier assigned to resources that also appear in the catalog of the Library of Congress.

Usage: ~4 million values.

```

---
examples:
  # Voyager record IDs for testing
  - [4, 3802861, 15589896]
input:
  - 010$a
trim:
  - whitespace
  
                    
```

1.  Trim whitespace.

2.  Output JSON with values for LCCN.


```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "66010930",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300417440",
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
              "_label": "Library of Congress"
            }
          ]
        }
      ]
    }
  ]
                        
```

