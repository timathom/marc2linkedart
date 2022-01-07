---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
source: Library of Congress MARC Standards Office, https://www.loc.gov/marc/bibliographic/bd034.html
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: [MARC 21 reference, Tables]
keyword: [MARC 21, Bibliographic]
---

# 034 \(Coded Cartographic Mathematical Data\)

Contains cartographic mathematical data, including scale, projection, and/or coordinates in coded form. For digital items, the coordinates can represent a bounding rectangle, the outline of the area covered and/or the outline of an interior area not covered. For celestial charts, it may also contain zone, declination data, and/or right ascension data, and/or equinox. There should be an 034 field corresponding to each 255 field in a record. Forrelief modelsandother three-dimensional items, if a single set of scales is used in field 255 \(i.e., one horizontal and one vertical scale\), the first indicator position in field 034 contains value 1, the denominator of the representative fraction for the horizontal scale is recorded in subfield $b, and the denominator of the representative fraction for the vertical scale is recorded in subfield $c. If multiple or varying sets of scales are recorded as a range, the smaller and larger denominators for the horizontal scales are recorded in the first and second subfield $b respectively, the smaller and larger denominators for the vertical scales are recorded in the first and second subfield $c, respectively, and the first indicator position contains value 3.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|a|Category of scale|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|b|Constant ratio linear horizontal scale|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|c|Constant ratio linear vertical scale|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|d|Coordinates - westernmost longitude|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|e|Coordinates - easternmost longitude|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|f|Coordinates - northernmost latitude|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|g|Coordinates - southernmost latitude|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|h|Angular scale|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|j|Declination - northern limit|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|k|Declination - southern limit|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|m|Right ascension - eastern limit|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|n|Right ascension - western limit|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|p|Equinox|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|r|Distance from earth|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|s|G-ring latitude|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|t|G-ring longitude|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|x|Beginning date|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|y|Ending date|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|z|Name of extraterrestrial body|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|0|Authority record control number or standard number|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|1|Real World Object URI|T|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|2|Source|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|3|Materials specified|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|6|Linkage|F|
|034|Coded Cartographic Mathematical Data|0-3|\#-1|8|Field link and sequence number|T|

**Previous topic:**[028 \(Publisher or Distributor Number\)](../tables/028_bib_table.md)

**Next topic:**[035 \(System Control Number\)](../tables/035_bib_table.md)

