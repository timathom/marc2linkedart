---
author: [tt434, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# System Control Number \(OCLC Number\)

System number used by OCLC to manage records in the WorldCat system.

## Source data

```

{
  "name": "OclcNumber",
  "sampleBibs": [4, 3802861, 15589896],
  "fieldSpec": "035az",
  "trimPunctuation": false,
  "scriptInclusion": "NONE"
}        		        		
        		
```

## Processing steps and output

1.  Skip `035` if `035z` \(canceled/invalid control number\).

2.  Get value of `035a`.

    1.  Normalize `035a` \(lower case and remove punctuation characters\) to test the value.

    2.  If the normalized value of `035a` starts with "oc", return the original value.

    3.  Else, skip `035`.


**Parent topic:**[System Control Numbers \(OCLC Numbers\)](../../tasks/identifiers/oclc_numbers.md)

**Related information**  


[035 \(System Control Number\)](../../tables/035_bib_table.md)

