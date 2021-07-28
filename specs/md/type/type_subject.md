# Subject Headings

## Top-Level Resources

For top-level resources, variable values are supplied for:

-   `root -> id` \[concept IRI\]
-   `root -> type`
-   `root -> _label` \[label of precoordinated subject heading, joined with double hyphens\]
-   `root -> identified_by -> content` \[same as `_label`\]
-   `root -> influenced_by -> id` \[concept IRI for facet concept\]
-   `root -> influenced_by -> type`
-   `root -> influenced_by -> _label`

## Embedded References

For embedded references, variable values are supplied for:

-   `root -> about -> id` **\[must match the `id` of the top-level resource\]**.
-   `root -> about -> type` **\[must match the `type` of the top-level resource\]**.
-   `root -> about -> _label` **\[must match the `_label` of the top-level resource\]**.

Top-level Type \(Concept\) entity for subject heading:

```

{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
  "type": "Type",
  "_label": "Death--Religious aspects--Christianity--History--2nd century",
  "identified_by": [
    {
      "type": "Name",
      "content": "Death--Religious aspects--Christianity--History--2nd century"
    }
  ],
  "created_by": {
    "type": "Creation",
    "influenced_by": [
      {
        "id": "https://lux.collections.yale.edu/data/concept/c54ba0ac-c106-4afe-8007-cb4a34cf0bd7",
        "type": "Type",
        "_label": "Death"
      },
      {
        "id": "https://lux.collections.yale.edu/data/concept/b273c64d-a9bb-4c2e-bb3f-5c13a6825a55",
        "type": "Type",
        "_label": "Religious aspects"
      },
      {
        "id": "https://lux.collections.yale.edu/data/concept/33a05e84-57bc-4f1d-a792-0de7758bd0d8",
        "type": "Type",
        "_label": "Christianity"
      },
      {
        "id": "https://lux.collections.yale.edu/data/concept/d43ab750-6e8d-4f7c-b3e2-d5a8dc134a37",
        "type": "Type",
        "_label": "History"
      },
      {
        "id": "https://lux.collections.yale.edu/data/event/92a599a2-2117-43f9-be3e-6e07f36cb2a5",
        "type": "Period",
        "_label": "2nd century"
      }
    ]
  }
}               
                
```

Embedded Type \(Concept\) entity for subject heading:

```

"about": [
  {
    "id": "https://lux.collections.yale.edu/data/concept/c5ba671b-c41d-40f5-983f-beb38b75b5b2",
    "type": "Type",
    "_label": "Death--Religious aspects--Christianity"
  },
  {
    "id": "https://lux.collections.yale.edu/data/concept/24f1b754-9566-4f38-8c61-9ce4082606aa",
    "type": "Type",
    "_label": "Death--Religious aspects--Christianity--History--2nd century"
  }
]               
                
```

**Parent topic:**[Type Entity \(Concept\)](../type/type.md)

