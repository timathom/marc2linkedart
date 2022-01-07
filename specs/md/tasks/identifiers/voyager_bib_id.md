# Voyager BIB ID

The Voyager BIB ID is a serially based identifier assigned to MARC 21 Bibliographic records in the Voyager ILS.

## Source data

```
{
  "name": "OrbisBibId",
  "sampleBibs": [2, 3, 4],
  "fieldSpec": "001",
  "trimPunctuation": false,
  "scriptInclusion": "NONE"
}
```

## Processing steps

1.  Prepend value with `ils:yul:`.


`2`

```
{
  "identified_by": [
    {
      "type": "Identifier",
      "content": "ils:yul:2",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300435704",
          "type": "Type",
          "_label": "System-Assigned Number"
        }
      ]
    }
  ]
}
```

**Parent topic:**[Identifiers](../../concepts/identifiers.md)

**Related information**  


[001 \(Control Number\)](../../tables/001_bib_table.md)

