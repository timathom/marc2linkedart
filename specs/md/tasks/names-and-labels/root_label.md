---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed]
---

# Root label

Root label of the top-level entity.

Each top-level entity must have a root `_label` property.

The root `_label` of a resource generally mirrors the `root → identified_by → Name → content` value.

**Note:** For MARC `245` content, when a parallel `880` non-Latin script title is present, that title is used as the value of the root `_label`.

**Note:** This example is meant to illustrate the root `_label` value and does not represent a complete JSON-LD document.

```
{
  "@context": "https://linked.art/ns/v1/linked-art.json",
  "id": "https://lux.collections.yale.edu/data/object/8e0bdbff-ebb1-4f9b-b98b-e97d64a01ff9",
  "type": "HumanMadeObject",
  "_label": "麗澤論說集錄 : [十卷]",
  "carries": [
    {
      "id": "https://lux.collections.yale.edu/data/text/416165c2-1108-4acd-b7ab-008f773a2ba3",
      "type": "LinguisticObject",
      "_label": "麗澤論說集錄 : [十卷]"
    }
  ]
}
```

**Parent topic:**[Labels](../../tasks/names-and-labels/labels.md)

