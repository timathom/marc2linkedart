# 028 \(Publisher or Distributor Number\)

Formatted number used for sound recordings, printed music, other music-related materials, and video recordings.

Usage: ~834,000 values.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|028|Publisher or Distributor Number|0-6|0-3|a|Publisher or distributor number|F|
|028|Publisher or Distributor Number|0-6|0-3|b|Source|F|
|028|Publisher or Distributor Number|0-6|0-3|q|Qualifying information|T|

```

---
examples:
  # Voyager BIB IDs for testing
  - [1730032, 7222575, 7752804]
input:
  - 028$a
  - 028$b
  - 028$q
trim:
  - whitespace  
                    
```

1.  Process `028$a`.

    1.  `028$a`: trim whitespace.

2.  Process `028$b`.

    1.  `028$b`: trim whitespace.

    2.  If the value extracted from `028$b` begins and ends with open/closing parentheses, return the value.

    3.  Else, concatenate the value with open/closing parentheses.

    4.  Join the values of `028$a` and `028$b` with a whitespace character.

3.  Process any `028$q` \(qualifying information\) values.

    1.  For each `028$q`: trim whitespace.

    2.  If 2 or more `028$q`: join values with a whitespace character.

    3.  If the value extracted from `028$q` begins and ends with open/closing parentheses, return the value.

    4.  Else, concatenate the value with open/closing parentheses.

    5.  Join the values extracted from `028$q` and the string value of `028$a` + `028$b` with a whitespace character.

4.  Output JSON with values for the publisher/distributor number.


BIB ID: 1730032

```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "M301356 (MGM/UA Home Video)",
      "classified_as": [
        {
          "id": "TBD",
          "type": "Type",
          "_label": "Publisher/Distributor Number"
        }
      ]
    }
  ]
                        
```

**Parent topic:**[Identifier Entity](../identifier/identifier.md)

