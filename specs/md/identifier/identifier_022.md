# 022 \(ISSN\)

The International Standard Serial Number is a unique identification number assigned to a continuing resource.

Usage: ~280,000 values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|022|ISSN|\#\|0\|1|Undefined|a|ISSN|F|
|022|ISSN|\#\|0\|1|Undefined|y|Incorrect ISSN|T|
|022|ISSN|\#\|0\|1|Undefined|z|Canceled ISSN|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [464630, 259853, 144793, 91117]
input:
  - 022$a
  - 022$y
  - 022$z
trim:
  - whitespace  
                    
```

1.  Do not capture `022$y` \(incorrect ISSN\) or `022$z` \(cancelled ISSN\).

2.  Process `022$a`.

    1.  `022$a`: trim whitespace.

3.  Output JSON with values for ISSN.


BIB ID: 464630

```

"identified_by": [
  {
    "type": "Identifier",
    "content": "0161-4223",
    "classified_as": [
      {
        "id": "http://vocab.getty.edu/aat/300417430",
        "type": "Type",
        "_label": "ISSN Identifier"
      }
    ]
  }
]
                        
```

**Parent topic:**[Identifier Entity](../identifier/identifier.md)

