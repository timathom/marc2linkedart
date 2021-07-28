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

