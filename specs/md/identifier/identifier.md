# Identifier Entity

## Overview of MARC data sources

|Tag|Label|Repeatable|Mapped|Label|URI|
|---|-----|----------|------|-----|---|
|001|Voyager Bibliographic Identifier \(BIB ID\)|F|T|System-Assigned Number|[http://vocab.getty.edu/aat/300435704](http://vocab.getty.edu/aat/300435704)|
|010|LCCN \(Library of Congress Control Number\)|F|T|Owner-Assigned Number|[http://vocab.getty.edu/aat/300417440](http://vocab.getty.edu/aat/300417440)|
|020|ISBN \(International Standard Book Number\)|T|T|ISBN Identifier|[http://vocab.getty.edu/aat/300417443](http://vocab.getty.edu/aat/300417443)|
|022|ISSN \(International Standard Serial Number\)|T|T|ISSN Identifier|[http://vocab.getty.edu/aat/300417430](http://vocab.getty.edu/aat/300417430)|
|028|Publisher or Distributor Number|T|T|Publisher/Distributor Number|TBD|
|035|System Control Number \(OCLC Number\)|T|T|Owner-Assigned Number|[http://vocab.getty.edu/aat/300404621](http://vocab.getty.edu/aat/300404621)|
|079|Local System Control Number \(OCLC Number\)|T|T|Owner-Assigned Number|[http://vocab.getty.edu/aat/300404621](http://vocab.getty.edu/aat/300404621)|

## JSON Structure

Variable values are supplied for:

-   `identified_by -> content`
-   `identified_by -> classified_as -> id`
-   `identified_by -> classified_as -> _label`
-   `identified_by -> attributed_by -> carried_out_by -> _label` \[optional depending on identifier type\]

```

  "identified_by": [
    {
      "type": "Identifier",
      "content": "(OCoLC)ocn702057138",
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

-   **[001 \(BIB ID\)](../identifier/identifier_001.md)**  
The Voyager BIB ID is a serially based identifier assigned to MARC 21 Bibliographic records in the Voyager ILS.
-   **[010 \(LCCN\)](../identifier/identifier_010.md)**  
The Library of Congress Control Number is a serially based identifier assigned to resources that also appear in the catalog of the Library of Congress.
-   **[020 \(ISBN\)](../identifier/identifier_020.md)**  
The International Standard Book Number \(ISBN\) is a publisher-assigned commercial book identifier that is intended to be unique. May appear in 10- or 13-digit formats.
-   **[022 \(ISSN\)](../identifier/identifier_022.md)**  
The International Standard Serial Number is a unique identification number assigned to a continuing resource.
-   **[028 \(Publisher or Distributor Number\)](../identifier/identifier_028.md)**  
Formatted number used for sound recordings, printed music, other music-related materials, and video recordings.
-   **[035 \(System Control Number: OCLC\)](../identifier/identifier_035.md)**  
Control number of a system other than the one whose control number is contained in field 001 \(Control Number\), field 010 \(Library of Congress Control Number\) or field 016 \(National Bibliographic Agency Control Number\).
-   **[079 \(Local System Control Number: OCLC\)](../identifier/identifier_079.md)**  
Control number of a system other than the one whose control number is contained in field 001 \(Control Number\), field 010 \(Library of Congress Control Number\) or field 016 \(National Bibliographic Agency Control Number\).

