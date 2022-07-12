---
author: [timothy.thompson@yale.edu, timothy.thompson@yale.edu]
keyword: [Assigned, Completed]
---

# Table of contents

Corresponds to the`505`note field in MARC.

|Domains|Usage|
|-------|-----|
|`LinguisticObject`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`VisualItem`|Do not repeat on related `HumanMadeObject` or `DigitalObject`.|
|`Set`|Do not repeat on nested `members_exemplified_by → HumanMadeObject`.|

## Source data

```
---
name: TableOfContents
sampleBibs:
  - 18
fieldSpec:
  - 505agrt
trimPunctuation: false
scriptInclusion: NONE
```

## Processing steps and output

1.  If `505a` and no other subfields, output the value of `505a`.

2.  Else, join all `505` subfields with a whitespace character.

3.  If there is more than one `505` field, join the string value of all `505` fields with an escaped newline character \(`\\n`\)

4.  If additional `505` fields begin with the prefix “\(Cont.\)”, strip the prefix and trailing whitespace from the `505` field.

5.  Replace space-surrounded double hyphens \(`--`\) with escaped newline characters \(`\\n`\) and store the string as a single `content` value.


**Note:** This example is meant to illustrate an table of contents note and does not represent a complete JSON-LD document.

`2733`

```
{
  "referred_to_by": [
    {
      "type": "LinguisticObject",
      "content": "The letter\\nTaller to-day\\nThe journey\\nNo change of place\\nThe question\\nThis lunar beauty\\nThis one\\nChorus\\nThe watchers\\nOde\\nThe decoys\\nThe three companions\\nIn legend\\nThe quarry\\nSeascape\\nA dream\\nSong\\nAutumn song\\nOne evening\\nLullaby\\nUnderneath the abject willow\\nMadrigal\\nAble at times to cry\\nTwo songs for Hedli Anderson\\nMiss Gee : a ballad\\nRoman wall blues\\nVictor : a ballad\\nThe dead echo\\nGanymede\\nA new age\\nSurgical ward\\nEmbassy\\nThe sphinx\\nMacao\\nThe bard\\nMus©♭e des Beaux Arts\\nGare du Midi\\nRimbaud\\nThe capital\\nEpitaph on a tyrant\\nIn memory of W.B. Yeats\\nIn memory of Sigmund Freud\\nThe quest\\nLaw like love\\nAnother time\\nOur bias\\nHell\\nSong\\nLady, weeping at the crossroads\\nIf I could tell you\\nThe model\\nAtlantis\\nDoomsday song\\nSong of the old soldier\\nMundus et infans\\nThe lesson\\nInvocation to Ariel\\nStephano's song\\nTrinculo's song\\nAlonso to Ferdinand\\nSong of the master and boatswain\\nMiranda's song\\nCaliban to the audience\\nThree dreams\\nIn praise of limestone\\nOne circumlocution\\nTheir lonely betters\\nSong\\nPleasure island\\nThe fall of Rome\\nThe managers\\nBarbed wire\\nUnder Sirius\\nNumbers and faces\\nA household\\nPrecious five\\nThe shield of Achilles\\nFleet visit\\nThe willow-wren and the stare\\nThe proof\\nA permanent way\\nNocturne\\nIn memoriam L.K.A., 1950-52\\nBucolics. Winds\\nWoods\\nMountains\\nLakes\\nIslands\\nPlains\\nStreams\\nHorae canonicae. Prime\\nTerce\\nSext\\nNones\\nVespers\\nCompline\\nLauds\\nMetalogue to The magic flute\\nThe song\\nGood-bye to the mezzogiorno\\nPrologue : the birth of architecture\\nThanksgiving for a habitat\\nThe cave of making\\nDown there\\nUp there\\nThe geography of the house\\nEncomium Balnei\\nGrub first, then ethics\\nFor friends only\\nTonight at seven-thirty\\nThe cave of nakedness\\nThe common life\\nYou\\nOn the circuit\\nAfter reading a child's guide to modern physics\\nWhitsunday in Kirchstetten\\nJoseph Weinheber\\nThe Horatians\\nSince\\nIn due season\\nAugust 1968\\nRiver profile\\nPrologue at sixty.",
      "classified_as": [
        {
          "id": "http://vocab.getty.edu/aat/300195187",
          "type": "Type",
          "_label": "Table of Contents",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300418049",
              "type": "Type",
              "_label": "Brief Text"
            }
          ]
        }
      ],
      "identified_by": [
        {
          "type": "Name",
          "content": "Table of Contents Note",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404669",
              "type": "Type",
              "_label": "Display Title"
            }
          ]
        }
      ]
    }
  ]
}
```

**Parent topic:**[Notes and statements](../../concepts/notes_and_statements.md)

