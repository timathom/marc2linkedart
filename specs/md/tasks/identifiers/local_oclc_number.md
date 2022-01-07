---
author: [tt434, timothy.thompson@yale.edu]
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Descriptive content
---

# Local System Control Number \(OCLC Number\)

System number used by OCLC to manage records in the WorldCat system.

## Source data

```

{
  "name": "OclcNumber",
  "sampleBibs": [907208],
  "fieldSpec": "079a",
  "trimPunctuation": false,
  "scriptInclusion": "NONE"
}        		        		
        		
```

## Processing steps and output

1.  Skip `079` if `079z` \(canceled/invalid control number\).

2.  Get value of `079a`.

    1.  Normalize `079a` \(lower case and remove punctuation characters\) to test the value.

    2.  If the normalized value of `079a` starts with "oc", return the original value.

    3.  Else, skip `079`.


**Parent topic:**[System Control Numbers \(OCLC Numbers\)](../../tasks/identifiers/oclc_numbers.md)

