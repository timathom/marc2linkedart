---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Entity modeling

The transformation from MARC to Linked Art requires that both **records** and **access points** within records be modeled and **[entified](../glossary/entification.md)** in order to create a normalized representation of the data.

-   Unique identifiers in the form of an [IRI](https://en.wikipedia.org/wiki/Internationalized_Resource_Identifier) must be assigned to each entity.

-   Entities corresponding to access points \(for example, [1XX](https://www.loc.gov/marc/bibliographic/bd1xx.html), [6XX](https://www.loc.gov/marc/bibliographic/bd6xx.html), and [7XX](https://www.loc.gov/marc/bibliographic/bd70x75x.html) fields in MARC\) must be extracted and merged \(deduplicated\).

-   Entities corresponding to records \(bibliographic and holdings\) should not be merged and deduplicated at this stage. For example, multiple editions of the novel *Beloved* will not be **[FRBRized](../glossary/frbr.md)** or linked to a common Work entity. However, they should all be linked to a single Person entity for the author Toni Morrison.

-   A [JSON-LD](https://json-ld.org/) representation of each top-level entity must be dereferenceable through a RESTful API.

-   **[LUX top-level entities](../concepts/lux_top-level_entities.md)**  
Eleven top-level entities are required for use in LUX.

