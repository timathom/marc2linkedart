# 001 \(BIB ID\)

The Voyager BIB ID is a serially based identifier assigned to MARC 21 Bibliographic records in the Voyager ILS.

Usage: ~11.7 million values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|001|Control Number \(Voyager BIB ID\)|NA|NA|NA|Control Number|F|

```

---
examples:
  # Voyager BIB IDs for testing
  - [2, 3, 4]
input:
  - 001
trim:
  - whitespace
                    
```

1.  Trim whitespace.

2.  Concatenate value with `ils:yul:`.

3.  Output JSON with values for BIB ID.


BIB ID: 2

```

"identified_by": [
  {
    "type": "Identifier",
    "content": "ils:yul:2",
    "classified_as": [
      {
        "id": "http://vocab.getty.edu/aat/300435704",
        "type": "Type",
        "_label": "System-Assigned Number"
      }
    ]
  }
]
                        
```

**Parent topic:**[Identifier Entity](../identifier/identifier.md)

