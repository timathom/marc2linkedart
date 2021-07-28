# Type Entity \(Concept\)

## Overview of MARC data sources

|Tag|Label|Repeatable|Mapped|Label|URI|
|---|-----|----------|------|-----|---|
|050|Library of Congress Call Number|T|T|Content|System-generated|
|090|Locally Assigned LC-Type Call Number|T|T|Content|System-generated|
|600|Person Subject|T|T|Content|System-generated|
|610|Corporate Body Subject|T|T|Content|System-generated|
|611|Meeting Subject|T|T|Content|System-generated|
|630|Title Subject|T|T|Content|System-generated|
|650|Topical Subject|T|T|Content|System-generated|
|651|Geographic Subject|T|T|Content|System-generated|
|653|Uncontrolled Keyword Subject|T|T|Content|System-generated|
|656|Associated Occupation|T|T|Content|System-generated|
|657|Associated Function|T|T|Content|System-generated|
|662|Hierarchical Place Subject|T|T|Content|System-generated|
|690|Locally Assigned Topical Subject|T|T|Content|System-generated|
|691|Locally Assigned Geographic Subject|T|T|Content|System-generated|
|692|Locally Assigned Person Subject|T|T|Content|System-generated|
|693|Locally Assigned Corporate Body Subject|T|T|Content|System-generated|
|694|Locally Assigned Meeting Subject|T|T|Content|System-generated|
|695|Locally Assigned Title Subject|T|T|Content|System-generated|

## JSON Structure

Type \(Concept\) entities are generated for classification numbers and subject headings.

For each Type entity:

-   A top-level resource is generated.

-   An embedded reference is added to the associated `LinguisticObject`, `VisualItem`, or `DigitalObject` resource.


-   **[Classification Numbers](../type/type_classification.md)**  

-   **[Subject Headings](../type/type_subject.md)**  


