# Classification Numbers

## Top-Level Resources

For top-level resources, variable values are supplied for:

-   `root -> id` \[concept IRI\]
-   `root -> _label`
-   `root -> identified_by -> content`

Top-level Type \(Concept\) entity for classification number:

```

{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/concept/8331ccf4-f0d5-42b0-ac2f-f50fb4c5e871",
  "type": "Type",
  "_label": "BT825",
  "identified_by": [
    {
      "type": "Identifier",
      "content": "BT825"
    }
  ]
}
      
```

## Embedded References

The embedded reference must follow the supertype classification of the resource in the same `classified_as` array.

For embedded references, variable values are supplied for:

-   `root -> classified_as -> id` **\[must match the `id` of the top-level resource\]**.
-   `root -> classified_as -> _label` **\[must match the `_label` of the top-level resource\]**.

Embedded Type \(Concept\) entity for classification number:

```

"classified_as": [
  {
    "id": "http://vocab.getty.edu/aat/300263751",
    "type": "Type",
    "_label": "Textual Works",
    "classified_as": [
      {
        "id": "http://vocab.getty.edu/aat/300435443",
        "type": "Type",
        "_label": "Type of Work"
      }
    ]
  },
  {
    "id": "https://lux.collections.yale.edu/data/concept/8331ccf4-f0d5-42b0-ac2f-f50fb4c5e871",
    "type": "Type",
    "_label": "BT825"
  }
]
      
```

**Parent topic:**[Type Entity \(Concept\)](../type/type.md)

