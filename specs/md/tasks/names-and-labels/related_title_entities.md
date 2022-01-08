---
author: timothy.thompson@yale.edu
keyword: [Assigned, Completed, Deployed]
---

# Related title entities

## Source data

```
---
name: RelatedTitleEntries
sampleBibs:
  - 2733
  - 3931
fieldSpec:
  - 505agrt
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

1.  Process each entry in a `505` contents note as a top-level `LinguisticObject`.

    1.  If subfields `grt` are present, join the string values of MARC `505agrt` with a whitespace character.

    2.  Split the joined string on double hyphen characters \(`--`\).

    3.  For each title entry, generate and store a top-level related title entity, each identified by an IRI.

    4.  Within each top-level related title entity, include a `part_of` reference to the `LinguisticObject` representing the bibliographic record with the `505` contents note.

    `3931`

    ```
    {
      "id": "https://lux.collections.yale.edu/data/text/08bdfe14-6deb-494c-b7c1-93a32d568ca4",
      "type": "LinguisticObject",
      "part_of": [
        {
          "id": "https://lux.collections.yale.edu/data/text/2189ea9f-98b9-48fb-9745-eaaffcff360d",
          "type": "LinguisticObject",
          "_label": "The early dynastic cemeteries of Naga-ed-Dêr"
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "pt. 3. A provincial cemetery of the Pyramid Age, Naga-ed-Dêr / by George A. Reisner",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ]
    }
    ```


**Parent topic:**[Related entities](../../tasks/related_entities.md)

