---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
---

# Record-level entities

Entities that correspond to resources held by the library \(books, journals, databases, archival collections, etc.\).

## Supertypes

The Linked Art profile of the [CIDOC Conceptual Reference Model \(CRM\)](http://www.cidoc-crm.org/html/5.0.4/cidoc-crm.html) includes a limited number of core or base classes. These can be refined by referencing terms from a taxonomy or classification scheme. Because record-level entities can be of many types, a *supertype* scheme has been developed for use in LUX.

The LUX supertype scheme is divided into two levels: *types* and *formats*. Types represent the mode of expression of a resource \(textual, visual, audible, etc.\), whereas formats can be thought of as specific instances of a type: for example, a *Book* is an instance or format of *Textual Works*. Some formats, such as *Geospatial Data* are instances of two different types: *Datasets* and *Cartography*.

## Multiple supertypes: order of precedence

The base class for record-level entities is determined by the supertype mapping. When a record-level entity is mapped to more than one supertype format, and the formats have different base classes, the following order of precedence is applied:

1.  `Set`
2.  `LinguisticObject`
3.  `VisualItem`
4.  `DigitalObject`
5.  `HumanMadeObject`

For formats that are instances of two different types, one base class has been marked as **primary**. For these supertypes, only the primary base class should be used as the `Type` of the record-level resources.

## Record processing rules

Apply the following rules to the processing of bibliographic \(bib\) and holdings \(mfhd\) records:

-   Ignore all suppressed bibs and mfhds.
-   Ignore bibs with no related mfhds \(orphan bibs\).
-   Ignore bibs that are unsuppressed, but whose related mfhds are all suppressed.
-   Ignore mfhds that are unsuppressed, but whose related bib is suppressed.

1.  [Content and carriers](../tasks/content_and_carriers.md)  

2.  [LUX supertype taxonomy](../tasks/supertypes/supertypes.md)  
Taxonomy of content types and related formats for classifying record-level resources in LUX.

**Parent topic:**[LUX top-level entities](../concepts/lux_top-level_entities.md)

**Next topic:**[Related entities](../tasks/related_entities.md)
