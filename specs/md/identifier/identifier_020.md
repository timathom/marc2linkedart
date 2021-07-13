# 020 \(ISBN\)

The International Standard Book Number \(ISBN\) is a publisher-assigned commercial book identifier that is intended to be unique. May appear in 10- or 13-digit formats.

Usage: ~9 million values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|020|ISBN|Undefined|Undefined|a|ISBN|F|
|020|ISBN|Undefined|Undefined|q|Qualifying information|T|
|020|ISBN|Undefined|Undefined|z|Canceled/invalid ISBN|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [693, 8827, 3802857, 13101718]
input:
  - 020$a
  - 020$q
  - 020$z
trim:
  - whitespace  
                    
```

1.  Do not capture `020$z` \(canceled/invalid ISBN\).

2.  Process `020$a`.

    1.  `020$a`: trim whitespace.

3.  Process any `020$q` \(qualifying information\) values.

    1.  For each `020$q`: trim whitespace.

    2.  If 2 or more `020$q`: join values with a whitespace character.

    3.  If the value extracted from `020$q` begins and ends with open/closing parentheses, return the value.

    4.  Else, concatenate the value with open/closing parentheses.

    5.  Join the values extracted from `020$a` and `020$q` with a whitespace character.

4.  Output JSON with values for ISBN.


BIB ID: 13101718

```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "9780227904787 (e-book)",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300417443",
          "type": "Type",
          "_label": "ISBN Identifier"
        }
      ]
    }
  ]
                        
```

**Parent topic:**[Identifier Entity](../identifier/identifier.md)

