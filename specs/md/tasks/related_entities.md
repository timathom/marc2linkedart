---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Related entities

Entities that represent the people, places, concepts, etc., that are connected to record-level resources.

Relationships are recorded for seven different entity types:

|Linked Art class|MARC tags|Entity types|MARC types|
|----------------|---------|------------|----------|
|Type|650 or 690|Concept|Topical subject|
|Period|6XXy|Event or time period|Chronological subdivision|
|Type|655|Genre or format|Genre/form term|
|Group|110, 111, 610, 611, 693, 694, 710, 711|Group|Corporate name \(610, 693\) or conference name \(611, 694\)|
|Person|100, 600, 692, 700|Person|Personal name|
|Place|651, 691, 751, 752|Place|Geographic name|
|LinguisticObject|130, 240, 630, 695, 730, 740, 830|Work \(textual work, moving image, music, scores and notation\)|Uniform title|

In MARC, entries can be either simple or complex. Simple entries contain a reference to a single entity type:

-   Concept
-   Genre or format
-   Group
-   Person
-   Place
-   Work

Complex entries include a reference to two or more entity types. Complex entries are used to record name/title references and subject headings with subdivisions.

|Linked Art class|MARC code|Entity type|MARC type|
|----------------|---------|-----------|---------|
|LinguisticObject|240|Work \(textual work, moving image, music, scores and notation\)|Uniform title|
|LinguisticObject|t|Work \(textual work, moving image, music, scores and notation\)|Title of a work|
|Type|v|Genre or format|Form subdivision|
|Type|x|Concept|General subdivision|
|Period|y|Event or time period|Chronological subdivision|
|Place|z|Place|Geographic subdivision|

## Processing information

1.  Extract related entities from MARC bibliographic records and assign an IRI to each distinct entity.

    1.  Create top-level related entities by joining subfields to create a key for matching and merging.

    2.  [Normalize](../glossary/normalization.md) and match each unique string value.

    3.  Apply specific processing steps for each related entity type \(concepts, agents, places, etc.\).

2.  Add embedded references to related entities within corresponding record-level resources \(`DigitalObject`, `HumanMadeObject`, `LinguisticObject`, `Set`, `VisualItem`\).


-   **[Creators, contributors, standalone works, simple subject/genre headings, and associated places](../tasks/concepts/simple_subject_headings.md)**  
Related resources that represent a single entity type.
-   **[Complex subject/genre headings and hierarchical associated places](../tasks/concepts/complex_subject_headings.md)**  
Subject headings representing two or more entity types.
-   **[Citation entities](../tasks/citation_entities.md)**  

-   **[Related title entities](../tasks/names-and-labels/related_title_entities.md)**  

-   **[Concepts](../concepts/concepts.md)**  
Entities that represent what a resource is about.
-   **[Events](../concepts/events.md)**  
Entities that represent time periods and/or discrete events related to a record-level resource.
-   **[Groups](../concepts/groups.md)**  
Entities that represent groups of people functioning collectively \(e.g., organizations and meetings/conferences\).
-   **[People](../concepts/people.md)**  

-   **[Places](../concepts/places.md)**  

-   **[Works](../concepts/works.md)**  

-   **[Sets](../concepts/related_sets.md)**  
Membership in library collections.

**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Previous topic:**[Record-level entities](../concepts/record_level_entities.md)

