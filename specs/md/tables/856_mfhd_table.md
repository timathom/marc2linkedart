---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
source: Library of Congress MARC Standards Office, https://www.loc.gov/marc/holdings/hd856.html
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: [MARC 21 reference, Tables]
keyword: [MARC 21, Holdings]
---

# 856 \(Electronic Location and Access\)

Information required to locate an electronic resource. The information identifies the electronic location containing the resource or from which it is available. It also contains information needed to retrieve the resource by the access method identified in the first indicator position. The relationship of the electronic location and access information in field 856 to the resource identified by the record as a whole is identified by the second indicator. The information contained in this field is sufficient to allow for the electronic transfer of a file, subscription to an electronic journal, or logon to an electronic resource. In some cases, only unique data elements are recorded which allow the user to access a locator table on a remote host containing the remaining information needed to access the resource. Field 856 is repeated when the location data elements vary \(the URL in subfield $u or subfields $a and $d, when used\). It is also repeated when more than one access method is used, different portions of the item are available electronically, mirror sites are recorded, different formats/resolutions with different URLs are indicated, and related items are recorded. See theGuidelines for the Use of Field 856for a more thorough discussion on the use of field 856.

|Tag|Tag Label|First Indicator|Second Indicator|Subfield|Subfield Label|Repeatable|
|---|---------|---------------|----------------|--------|--------------|----------|
|856|Electronic Location and Access|\#-7|\#-8|a|Host name|T|
|856|Electronic Location and Access|\#-7|\#-8|c|Compression information|T|
|856|Electronic Location and Access|\#-7|\#-8|d|Path|T|
|856|Electronic Location and Access|\#-7|\#-8|f|Electronic name|T|
|856|Electronic Location and Access|\#-7|\#-8|m|Contact for access assistance|T|
|856|Electronic Location and Access|\#-7|\#-8|o|Operating system|F|
|856|Electronic Location and Access|\#-7|\#-8|p|Port|F|
|856|Electronic Location and Access|\#-7|\#-8|q|Electronic format type|F|
|856|Electronic Location and Access|\#-7|\#-8|s|File size|T|
|856|Electronic Location and Access|\#-7|\#-8|u|Uniform Resource Identifier|T|
|856|Electronic Location and Access|\#-7|\#-8|v|Hours access method available|T|
|856|Electronic Location and Access|\#-7|\#-8|w|Record control number|T|
|856|Electronic Location and Access|\#-7|\#-8|x|Nonpublic note|T|
|856|Electronic Location and Access|\#-7|\#-8|y|Link text|T|
|856|Electronic Location and Access|\#-7|\#-8|z|Public note|T|
|856|Electronic Location and Access|\#-7|\#-8|2|Access method|F|
|856|Electronic Location and Access|\#-7|\#-8|3|Materials specified|F|
|856|Electronic Location and Access|\#-7|\#-8|6|Linkage|F|
|856|Electronic Location and Access|\#-7|\#-8|7|Access status|F|
|856|Electronic Location and Access|\#-7|\#-8|8|Field link and sequence number|T|

**Previous topic:**[856 \(Electronic Location and Access\)](../tables/856_bib_table.md)

