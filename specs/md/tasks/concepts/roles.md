---
author: timothy.thompson@yale.edu
publisher: YUL Technical Services, Resource Discovery Services, Metadata Services Unit
category: Entity extraction
keyword: 
---

# Roles

Roles for related entities within activities.

## Source data

```
---
name: Roles
sampleBibs:
  - 693
# Source data fields
fieldSpec:
  - 100e4
  - 110e4
  - 111j4
  - 600e4
  - 610e4
  - 611j4
  - 700e4
  - 710e4
  - 711j4 
trimPunctuation: true
scriptInclusion: NONE
```

## Processing steps and output

The role of an agent within an activity is derived from `$e` \(relator term for organizations and persons\), `$j` \(relator term for conferences/meetings\), or `$4` \(relationship code for any entity type\). When those subfields are absent, a generic role of `Creator` is assigned when `1XX` is the source or `Contributor` when `7XX` is the source.

Roles are typically used in the context of an activity. However, entities referenced as subjects may also have role terms assigned to them.

The mapping table below should be used to generate unique concept entities for role terms. For entries in the table with a type of `translations`, the `Target` column represents a reference to an “authorized” version of the term that appears later in the table. For all other entries, the `Target` column represents an `equivalent` IRI that should be included in the top-level resource description for the role concept.

|Type|Source|Code|Target|
|----|------|----|------|
|translations|acteur| |actor|
|translations|architects| |architect|
|translations|auteur| |author|
|translations|auth| |author|
|translations|authors| |author|
|translations|binders| |binder|
|translations|binding designers| |binding designer|
|translations|bookjacket designer| |book jacket designer|
|translations|cast| |actor|
|translations|cast member| |actor|
|translations|co-author| |author|
|translations|collaborator| |contributor|
|translations|colourist| |colorist|
|translations|comp| |composer|
|translations|defendent| |defendant|
|translations|director of photography| |cinematographer|
|translations|ed| |editor|
|translations|honouree| |honoree|
|translations|ill| |illustrator|
|translations|illus| |illustrator|
|translations|illustrations| |illustrator|
|translations|main author| |author|
|translations|maker| |creator|
|translations|metal engraver| |metal-engraver|
|translations|onscreen participant| |on-screen participant|
|translations|onscreen presenter| |on-screen presenter|
|translations|prin| |printer|
|translations|printers| |printer|
|translations|ptr| |printer|
|translations|pub| |publisher|
|translations|publishers| |publisher|
|translations|respondant| |respondent|
|translations|tr| |translator|
|translations|trad| |translator|
|translations|traducteur| |translator|
|translations|trans| |translator|
|translations|wen zi zuo zhe| |author|
|translations|wood engraver| |wood-engraver|
|translations|writer| |author|
|translations|主编| |editor in chief|
|translations|原着| |author|
|translations|撰| |author|
|translations|编| |editor|
|translations|编校| |editor|
|translations|编纂| |compiler|
|translations|编著| |editor|
|translations|编译| |compiler|
|translations|编辑| |editor|
|translations|编选| |compiler|
|translations|译| |translator|
|translations|译述| |translator|
|translations|辑| |editor|
|production|abridger|abr|[http://vocab.getty.edu/aat/300440753](http://vocab.getty.edu/aat/300440753)|
|production|adapter|adp|[http://vocab.getty.edu/aat/300410355](http://vocab.getty.edu/aat/300410355)|
|production|after| | |
|production|animator|anm|[http://vocab.getty.edu/aat/300025646](http://vocab.getty.edu/aat/300025646)|
|production|architect|arc|[http://vocab.getty.edu/aat/300024987](http://vocab.getty.edu/aat/300024987)|
|production|architect\_GROUP| |[http://vocab.getty.edu/aat/300312082](http://vocab.getty.edu/aat/300312082)|
|production|arranger|arr|[http://vocab.getty.edu/aat/300025667](http://vocab.getty.edu/aat/300025667)|
|production|artist|art|[http://vocab.getty.edu/aat/300025103](http://vocab.getty.edu/aat/300025103)|
|production|author|aut|[http://vocab.getty.edu/aat/300025492](http://vocab.getty.edu/aat/300025492)|
|production|binder|bnd|[http://vocab.getty.edu/aat/300025704](http://vocab.getty.edu/aat/300025704)|
|production|binding designer|bdd|[http://id.loc.gov/vocabulary/relators/bdd](http://id.loc.gov/vocabulary/relators/bdd)|
|production|book artist| |[http://vocab.getty.edu/aat/300386346](http://vocab.getty.edu/aat/300386346)|
|production|book designer|bkd|[http://id.loc.gov/vocabulary/relators/bkd](http://id.loc.gov/vocabulary/relators/bkd)|
|production|book jacket designer| | |
|production|book producer|bkp|[http://id.loc.gov/vocabulary/relators/bkp](http://id.loc.gov/vocabulary/relators/bkp)|
|production|bookbinder| |[http://vocab.getty.edu/aat/300025704](http://vocab.getty.edu/aat/300025704)|
|production|bookplate designer|bpd|[http://id.loc.gov/vocabulary/relators/bpd](http://id.loc.gov/vocabulary/relators/bpd)|
|production|calligrapher|cll|[http://vocab.getty.edu/aat/300025107](http://vocab.getty.edu/aat/300025107)|
|production|cartographer|ctg|[http://vocab.getty.edu/aat/300025593](http://vocab.getty.edu/aat/300025593)|
|production|carver| |[http://vocab.getty.edu/aat/300025256](http://vocab.getty.edu/aat/300025256)|
|production|casemaker| | |
|production|chromo-lithographer| |[http://vocab.getty.edu/aat/300251177](http://vocab.getty.edu/aat/300251177)|
|production|clockmaker| |[http://vocab.getty.edu/aat/300025397](http://vocab.getty.edu/aat/300025397)|
|production|collotyper|clt|[http://id.loc.gov/vocabulary/relators/clt](http://id.loc.gov/vocabulary/relators/clt)|
|production|colorist|clr|[http://vocab.getty.edu/aat/300435165](http://vocab.getty.edu/aat/300435165)|
|production|compiler|com|[http://vocab.getty.edu/aat/300121766](http://vocab.getty.edu/aat/300121766)|
|production|composer|cmp|[http://vocab.getty.edu/aat/300025671](http://vocab.getty.edu/aat/300025671)|
|production|compositor|cmt|[http://vocab.getty.edu/aat/300025708](http://vocab.getty.edu/aat/300025708)|
|production|contributor|ctb|[http://vocab.getty.edu/aat/300403974](http://vocab.getty.edu/aat/300403974)|
|production|copyist| |[http://vocab.getty.edu/aat/300025189](http://vocab.getty.edu/aat/300025189)|
|production|cover artist| | |
|production|cover designer|cov|[http://id.loc.gov/vocabulary/relators/cov](http://id.loc.gov/vocabulary/relators/cov)|
|production|creator|cre|[http://vocab.getty.edu/aat/300386174](http://vocab.getty.edu/aat/300386174)|
|production|decorator| |[http://vocab.getty.edu/aat/300435238](http://vocab.getty.edu/aat/300435238)|
|production|designer|dsr|[http://vocab.getty.edu/aat/300025190](http://vocab.getty.edu/aat/300025190)|
|production|diesinker| |[http://vocab.getty.edu/aat/300386327](http://vocab.getty.edu/aat/300386327)|
|production|draftsman|drm|[http://vocab.getty.edu/aat/300112172](http://vocab.getty.edu/aat/300112172)|
|production|editor|edt|[http://vocab.getty.edu/aat/300025526](http://vocab.getty.edu/aat/300025526)|
|production|editor in chief| | |
|production|electrotyper|elt|[http://id.loc.gov/vocabulary/relators/elt](http://id.loc.gov/vocabulary/relators/elt)|
|production|engraver|egr|[http://vocab.getty.edu/aat/300239410](http://vocab.getty.edu/aat/300239410)|
|production|etcher|etr|[http://vocab.getty.edu/aat/300025174](http://vocab.getty.edu/aat/300025174)|
|production|fabricator| |[http://vocab.getty.edu/aat/300251917](http://vocab.getty.edu/aat/300251917)|
|production|fore-edge painter| | |
|production|gilder| |[http://vocab.getty.edu/aat/300025261](http://vocab.getty.edu/aat/300025261)|
|production|illuminator|ilu|[http://vocab.getty.edu/aat/300025122](http://vocab.getty.edu/aat/300025122)|
|production|illustrator|ill|[http://vocab.getty.edu/aat/300025123](http://vocab.getty.edu/aat/300025123)|
|production|inker| | |
|production|inscriber|ins|[http://vocab.getty.edu/aat/300121785](http://vocab.getty.edu/aat/300121785)|
|production|inventor|inv|[http://vocab.getty.edu/aat/300025845](http://vocab.getty.edu/aat/300025845)|
|production|letterer| |[http://vocab.getty.edu/aat/300025115](http://vocab.getty.edu/aat/300025115)|
|production|lithographer|ltg|[http://vocab.getty.edu/aat/300025175](http://vocab.getty.edu/aat/300025175)|
|production|lyricist|lyr|[http://vocab.getty.edu/aat/300025675](http://vocab.getty.edu/aat/300025675)|
|production|manufacturer|mfr|[http://vocab.getty.edu/aat/300025230](http://vocab.getty.edu/aat/300025230)|
|production|metal-engraver|mte|[http://id.loc.gov/vocabulary/relators/mte](http://id.loc.gov/vocabulary/relators/mte)|
|production|mint| |[http://vocab.getty.edu/aat/300205362](http://vocab.getty.edu/aat/300205362)|
|production|modeler| |[http://vocab.getty.edu/aat/300025417](http://vocab.getty.edu/aat/300025417)|
|production|mounter| | |
|production|organizer|orm|[http://id.loc.gov/vocabulary/relators/orm](http://id.loc.gov/vocabulary/relators/orm)|
|production|originator|org|[http://vocab.getty.edu/aat/300386177](http://vocab.getty.edu/aat/300386177)|
|production|paper engineer| | |
|production|paper maker| |[http://vocab.getty.edu/aat/300025344](http://vocab.getty.edu/aat/300025344)|
|production|papermaker|ppm|[http://vocab.getty.edu/aat/300025344](http://vocab.getty.edu/aat/300025344)|
|production|penciller| | |
|production|photographer|pht|[http://vocab.getty.edu/aat/300025687](http://vocab.getty.edu/aat/300025687)|
|production|playing card maker| | |
|production|potter| |[http://vocab.getty.edu/aat/300025414](http://vocab.getty.edu/aat/300025414)|
|production|printer|prt|[http://vocab.getty.edu/aat/300025732](http://vocab.getty.edu/aat/300025732)|
|production|printer of plates|pop|[http://vocab.getty.edu/aat/300025733](http://vocab.getty.edu/aat/300025733)|
|production|printer\_GROUP| |[http://vocab.getty.edu/aat/300386347](http://vocab.getty.edu/aat/300386347)|
|production|printmaker|prm|[http://vocab.getty.edu/aat/300025164](http://vocab.getty.edu/aat/300025164)|
|production|printmaker\_GROUP| |[http://vocab.getty.edu/aat/300312299](http://vocab.getty.edu/aat/300312299)|
|production|proofreader|pfr|[http://vocab.getty.edu/aat/300418027v](http://vocab.getty.edu/aat/300418027v)|
|production|repairer| | |
|production|screenwriter|aus|[http://vocab.getty.edu/aat/300025515](http://vocab.getty.edu/aat/300025515)|
|production|scribe|scr|[http://vocab.getty.edu/aat/300025580](http://vocab.getty.edu/aat/300025580)|
|production|sculptor|scl|[http://vocab.getty.edu/aat/300025181](http://vocab.getty.edu/aat/300025181)|
|production|series editor| | |
|production|stereotyper|str|[http://vocab.getty.edu/aat/300025743](http://vocab.getty.edu/aat/300025743)|
|production|transcriber|trc|[http://vocab.getty.edu/aat/300440751](http://vocab.getty.edu/aat/300440751)|
|production|translator|trl|[http://vocab.getty.edu/aat/300025601](http://vocab.getty.edu/aat/300025601)|
|production|type designer|tyd|[http://vocab.getty.edu/aat/300417840](http://vocab.getty.edu/aat/300417840)|
|production|typesetter| |[http://vocab.getty.edu/aat/300025744](http://vocab.getty.edu/aat/300025744)|
|production|typographer|tyg|[http://vocab.getty.edu/aat/300025745](http://vocab.getty.edu/aat/300025745)|
|production|wood-engraver|wde|[http://vocab.getty.edu/aat/300025167](http://vocab.getty.edu/aat/300025167)|
|production|woodcutter|wdc|[http://vocab.getty.edu/aat/300025178](http://vocab.getty.edu/aat/300025178)|
|sponsor|commissioned by| |[http://vocab.getty.edu/aat/300400903](http://vocab.getty.edu/aat/300400903)|
|sponsor|commissioning body| |[http://vocab.getty.edu/aat/300400903](http://vocab.getty.edu/aat/300400903)|
|sponsor|degree granting institution|dgg|[http://id.loc.gov/vocabulary/relators/dgg](http://id.loc.gov/vocabulary/relators/dgg)|
|sponsor|degree supervisor|dgs|[http://id.loc.gov/vocabulary/relators/dgs](http://id.loc.gov/vocabulary/relators/dgs)|
|sponsor|funder|fnd|[http://vocab.getty.edu/aat/300188572](http://vocab.getty.edu/aat/300188572)|
|sponsor|funder/sponsor| |[http://vocab.getty.edu/aat/300188572](http://vocab.getty.edu/aat/300188572)|
|sponsor|host institution|his|[http://id.loc.gov/vocabulary/relators/his](http://id.loc.gov/vocabulary/relators/his)|
|sponsor|sponsor|spn|[http://vocab.getty.edu/aat/300188572](http://vocab.getty.edu/aat/300188572)|
|sponsor|sponsoring body| |[http://vocab.getty.edu/aat/300400903](http://vocab.getty.edu/aat/300400903)|
|sponsor|sponsoring institution| |[http://vocab.getty.edu/aat/300188572](http://vocab.getty.edu/aat/300188572)|
|publication|bank| | |
|publication|bookseller|bsl|[http://vocab.getty.edu/aat/300025244](http://vocab.getty.edu/aat/300025244)|
|publication|broadcaster|brd|[http://vocab.getty.edu/aat/300025502](http://vocab.getty.edu/aat/300025502)|
|publication|distributor|dst|[http://vocab.getty.edu/aat/300404885](http://vocab.getty.edu/aat/300404885)|
|publication|enacting jurisdiction|enj|[http://id.loc.gov/vocabulary/relators/enj](http://id.loc.gov/vocabulary/relators/enj)|
|publication|film distributor|fds|[http://id.loc.gov/vocabulary/relators/fds](http://id.loc.gov/vocabulary/relators/fds)|
|publication|issuer| | |
|publication|issuing body|isb|[http://vocab.getty.edu/aat/300386627](http://vocab.getty.edu/aat/300386627)|
|publication|publisher|pbl|[http://vocab.getty.edu/aat/300025574](http://vocab.getty.edu/aat/300025574)|
|publication|publisher\_GROUP| |[http://vocab.getty.edu/aat/300386627](http://vocab.getty.edu/aat/300386627)|
|publication|retailer| |[http://vocab.getty.edu/aat/300025246](http://vocab.getty.edu/aat/300025246)|
|performance|actor|act|[http://vocab.getty.edu/aat/300025658](http://vocab.getty.edu/aat/300025658)|
|performance|bass| |[http://vocab.getty.edu/aat/300206743](http://vocab.getty.edu/aat/300206743)|
|performance|boy soprano| | |
|performance|camera| | |
|performance|choreographer|chr|[http://vocab.getty.edu/aat/300025649](http://vocab.getty.edu/aat/300025649)|
|performance|cinematographer|cng|[http://vocab.getty.edu/aat/300025650](http://vocab.getty.edu/aat/300025650)|
|performance|clarinet| | |
|performance|conductor|cnd|[http://vocab.getty.edu/aat/300025672](http://vocab.getty.edu/aat/300025672)|
|performance|costume designer|cst|[http://vocab.getty.edu/aat/300163428](http://vocab.getty.edu/aat/300163428)|
|performance|dancer|dnc|[http://vocab.getty.edu/aat/300025653](http://vocab.getty.edu/aat/300025653)|
|performance|direction| | |
|performance|director|drt|[http://vocab.getty.edu/aat/300025654](http://vocab.getty.edu/aat/300025654)|
|performance|film director|fmd|[http://vocab.getty.edu/aat/300312209](http://vocab.getty.edu/aat/300312209)|
|performance|film editor|flm|[http://vocab.getty.edu/aat/300386237](http://vocab.getty.edu/aat/300386237)|
|performance|film producer|fmp|[http://vocab.getty.edu/aat/300312211](http://vocab.getty.edu/aat/300312211)|
|performance|filmmaker|fmk|[http://vocab.getty.edu/aat/300075154](http://vocab.getty.edu/aat/300075154)|
|performance|guitarist| |[http://vocab.getty.edu/aat/300235042](http://vocab.getty.edu/aat/300235042)|
|performance|hornist| | |
|performance|instrumentalist|itr|[http://vocab.getty.edu/aat/300162131](http://vocab.getty.edu/aat/300162131)|
|performance|interpreter| | |
|performance|interviewee|ive|[http://id.loc.gov/vocabulary/relators/ive](http://id.loc.gov/vocabulary/relators/ive)|
|performance|interviewer|ivr|[http://id.loc.gov/vocabulary/relators/ivr](http://id.loc.gov/vocabulary/relators/ivr)|
|performance|librettist|lbt|[http://vocab.getty.edu/aat/300025674](http://vocab.getty.edu/aat/300025674)|
|performance|lighting designer|lgd|[http://vocab.getty.edu/aat/300386275](http://vocab.getty.edu/aat/300386275)|
|performance|music| | |
|performance|musician|mus|[http://vocab.getty.edu/aat/300025666](http://vocab.getty.edu/aat/300025666)|
|performance|narrator|nrt|[http://vocab.getty.edu/aat/300417254](http://vocab.getty.edu/aat/300417254)|
|performance|on-screen participant| | |
|performance|on-screen presenter| | |
|performance|orchestra| |[http://vocab.getty.edu/aat/300025666](http://vocab.getty.edu/aat/300025666)|
|performance|organist| |[http://vocab.getty.edu/aat/300235015](http://vocab.getty.edu/aat/300235015)|
|performance|performer|prf|[http://vocab.getty.edu/aat/300068931](http://vocab.getty.edu/aat/300068931)|
|performance|pianist| |[http://vocab.getty.edu/aat/300235018](http://vocab.getty.edu/aat/300235018)|
|performance|praeses|pra|[http://id.loc.gov/vocabulary/relators/pra](http://id.loc.gov/vocabulary/relators/pra)|
|performance|producer|pro|[http://vocab.getty.edu/aat/300197742](http://vocab.getty.edu/aat/300197742)|
|performance|production| | |
|performance|production company|prn|[http://vocab.getty.edu/aat/300419391](http://vocab.getty.edu/aat/300419391)|
|performance|production designer|prs|[http://vocab.getty.edu/aat/300435129](http://vocab.getty.edu/aat/300435129)|
|performance|production personnel|prd|[http://id.loc.gov/vocabulary/relators/prd](http://id.loc.gov/vocabulary/relators/prd)|
|performance|recording engineer|rce|[http://id.loc.gov/vocabulary/relators/rce](http://id.loc.gov/vocabulary/relators/rce)|
|performance|saxophonist| | |
|performance|script| | |
|performance|set designer|std|[http://vocab.getty.edu/aat/300435127](http://vocab.getty.edu/aat/300435127)|
|performance|singer|sng|[http://vocab.getty.edu/aat/300025684](http://vocab.getty.edu/aat/300025684)|
|performance|soprano| |[http://vocab.getty.edu/aat/300206741](http://vocab.getty.edu/aat/300206741)|
|performance|stage director|sgd|[http://vocab.getty.edu/aat/300312210](http://vocab.getty.edu/aat/300312210)|
|performance|stage manager|stm|[http://id.loc.gov/vocabulary/relators/stm](http://id.loc.gov/vocabulary/relators/stm)|
|performance|television director|tld|[http://id.loc.gov/vocabulary/relators/tld](http://id.loc.gov/vocabulary/relators/tld)|
|performance|television producer|tlp|[http://id.loc.gov/vocabulary/relators/tlp](http://id.loc.gov/vocabulary/relators/tlp)|
|performance|tenor| |[http://vocab.getty.edu/aat/300206746](http://vocab.getty.edu/aat/300206746)|
|performance|trombonist| | |
|performance|trumpet player| |[http://vocab.getty.edu/aat/300235064](http://vocab.getty.edu/aat/300235064)|
|performance|video designer| | |
|performance|videographer|vdg|[http://vocab.getty.edu/aat/300263895](http://vocab.getty.edu/aat/300263895)|
|performance|violist| |[http://vocab.getty.edu/aat/300235045](http://vocab.getty.edu/aat/300235045)|
|performance|violoncellist| |[http://vocab.getty.edu/aat/300235047](http://vocab.getty.edu/aat/300235047)|
|performance|vocalist| |[http://vocab.getty.edu/aat/300025684](http://vocab.getty.edu/aat/300025684)|
|performance|voice actor|vac|[http://id.loc.gov/vocabulary/relators/vac](http://id.loc.gov/vocabulary/relators/vac)|
|encounter|art collector| | |
|encounter|collector|col|[http://vocab.getty.edu/aat/300025234](http://vocab.getty.edu/aat/300025234)|
|encounter|discoverer| | |
|encounter|expedition| | |
|provenance|auctioneer|auc|[http://vocab.getty.edu/aat/300025208](http://vocab.getty.edu/aat/300025208)|
|provenance|client|cli|[http://vocab.getty.edu/aat/300025833](http://vocab.getty.edu/aat/300025833)|
|provenance|commissaire-priseur| |[http://vocab.getty.edu/aat/300412173](http://vocab.getty.edu/aat/300412173)|
|provenance|copyright holder|cph|[http://id.loc.gov/vocabulary/relators/cph](http://id.loc.gov/vocabulary/relators/cph)|
|provenance|current owner| | |
|provenance|donor|dnr|[http://vocab.getty.edu/aat/300025240](http://vocab.getty.edu/aat/300025240)|
|provenance|exchanger| | |
|provenance|former owner|fmo|[http://id.loc.gov/vocabulary/relators/fmo](http://id.loc.gov/vocabulary/relators/fmo)|
|provenance|land owner| | |
|provenance|licensee|lse|[http://id.loc.gov/vocabulary/relators/lse](http://id.loc.gov/vocabulary/relators/lse)|
|provenance|licensor|lso|[http://id.loc.gov/vocabulary/relators/lso](http://id.loc.gov/vocabulary/relators/lso)|
|provenance|owner|own|[http://vocab.getty.edu/aat/300203630](http://vocab.getty.edu/aat/300203630)|
|provenance|patron|pat|[http://vocab.getty.edu/aat/300115251](http://vocab.getty.edu/aat/300115251)|
|provenance|previous owner| | |
|provenance|purchaser| |[http://vocab.getty.edu/aat/300025211](http://vocab.getty.edu/aat/300025211)|
|provenance|source| | |
|provenance|vendor| |[http://vocab.getty.edu/aat/300150791](http://vocab.getty.edu/aat/300150791)|
|exhibition|borrower| |[http://vocab.getty.edu/aat/300311675](http://vocab.getty.edu/aat/300311675)|
|exhibition|exhibition| | |
|exhibition|lender|len|[http://id.loc.gov/vocabulary/relators/len](http://id.loc.gov/vocabulary/relators/len)|
|other|addressee|rcp|[http://id.loc.gov/vocabulary/relators/rcp](http://id.loc.gov/vocabulary/relators/rcp)|
|other|advertiser| |[http://vocab.getty.edu/aat/300252554](http://vocab.getty.edu/aat/300252554)|
|other|annotator|ann|[http://id.loc.gov/vocabulary/relators/ann](http://id.loc.gov/vocabulary/relators/ann)|
|other|appellant|apl|[http://id.loc.gov/vocabulary/relators/apl](http://id.loc.gov/vocabulary/relators/apl)|
|other|appellee|ape|[http://id.loc.gov/vocabulary/relators/ape](http://id.loc.gov/vocabulary/relators/ape)|
|other|assignee|asg|[http://id.loc.gov/vocabulary/relators/asg](http://id.loc.gov/vocabulary/relators/asg)|
|other|associated name|asn|[http://id.loc.gov/vocabulary/relators/asn](http://id.loc.gov/vocabulary/relators/asn)|
|other|auxilium| | |
|other|claimant| | |
|other|commentator|cmm|[http://id.loc.gov/vocabulary/relators/cmm](http://id.loc.gov/vocabulary/relators/cmm)|
|other|complainant|cpl|[http://id.loc.gov/vocabulary/relators/cpl](http://id.loc.gov/vocabulary/relators/cpl)|
|other|conservator|con|[http://vocab.getty.edu/aat/300102842](http://vocab.getty.edu/aat/300102842)|
|other|correspondent|crp|[http://vocab.getty.edu/aat/300225705](http://vocab.getty.edu/aat/300225705)|
|other|court reporter|crt|[http://vocab.getty.edu/aat/300136440](http://vocab.getty.edu/aat/300136440)|
|other|curator|cur|[http://vocab.getty.edu/aat/300025633](http://vocab.getty.edu/aat/300025633)|
|other|dedicatee|dte|[http://vocab.getty.edu/aat/300121765](http://vocab.getty.edu/aat/300121765)|
|other|defendant|dfd|[http://id.loc.gov/vocabulary/relators/dfd](http://id.loc.gov/vocabulary/relators/dfd)|
|other|digitiser| | |
|other|editor and translator| | |
|other|honoree|hnr|[http://vocab.getty.edu/aat/300404867](http://vocab.getty.edu/aat/300404867)|
|other|judge|jud|[http://vocab.getty.edu/aat/300025625](http://vocab.getty.edu/aat/300025625)|
|other|magistrate| |[http://vocab.getty.edu/aat/300025467](http://vocab.getty.edu/aat/300025467)|
|other|moderator|mod|[http://id.loc.gov/vocabulary/relators/mod](http://id.loc.gov/vocabulary/relators/mod)|
|other|other|oth|[http://id.loc.gov/vocabulary/relators/oth](http://id.loc.gov/vocabulary/relators/oth)|
|other|panelist|pan|[http://id.loc.gov/vocabulary/relators/pan](http://id.loc.gov/vocabulary/relators/pan)|
|other|petitioner| | |
|other|plaintiff|ptf|[http://vocab.getty.edu/aat/300440758](http://vocab.getty.edu/aat/300440758)|
|other|presenter|pre|[http://id.loc.gov/vocabulary/relators/pre](http://id.loc.gov/vocabulary/relators/pre)|
|other|pressman| |[http://vocab.getty.edu/aat/300025731](http://vocab.getty.edu/aat/300025731)|
|other|proprietor| |[http://vocab.getty.edu/aat/300025241](http://vocab.getty.edu/aat/300025241)|
|other|pseud| |[http://vocab.getty.edu/aat/300404657](http://vocab.getty.edu/aat/300404657)|
|other|recipient| | |
|other|reporter|rpt|[http://vocab.getty.edu/aat/300025508](http://vocab.getty.edu/aat/300025508)|
|other|respondent|rsp|[http://id.loc.gov/vocabulary/relators/rsp](http://id.loc.gov/vocabulary/relators/rsp)|
|other|reviewer|rev|[http://vocab.getty.edu/aat/300440750](http://vocab.getty.edu/aat/300440750)|
|other|sender| | |
|other|signer|sgn|[http://vocab.getty.edu/aat/300137375](http://vocab.getty.edu/aat/300137375)|
|other|speaker|spk|[http://vocab.getty.edu/aat/300136462](http://vocab.getty.edu/aat/300136462)|
|other|subject of parody| | |
|other|surveyor|srv|[http://vocab.getty.edu/aat/300025100](http://vocab.getty.edu/aat/300025100)|
|other|teacher|tch|[http://vocab.getty.edu/aat/300025529](http://vocab.getty.edu/aat/300025529)|
|other|user| | |
|other|witness|wit|[http://id.loc.gov/vocabulary/relators/wit](http://id.loc.gov/vocabulary/relators/wit)|

1.  Generate and store the top-level concept resources using the mapping table, each identified by an IRI.

    1.  For the `_label` and `Primary Name`, capitalize the first letter of the term.

    2.  For each entry in the mapping table with an IRI in the `Target` column, add a corresponding `equivalent` reference.

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/concept/271d291f-0d42-4abf-bf43-070b241edc98",
      "type": "Type",
      "_label": "Translator",
      "identified_by": [
        {
          "type": "Name",
          "content": "Translator",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "equivalent": [
        {
          "id": "http://vocab.getty.edu/aat/300025601",
          "type": "Type"
        }
      ]
    }
    ```

2.  For each `1XX` or `7XX` field, inspect each subfield `e` \(all but `111` or `711`\), `j` \(only `X11`\), and `4` \(all\) for a role term or code.

3.  [Normalize](../../glossary/normalization.md) and match role terms in `e` or `j` and role codes in `4` against the top-level entities corresponding to the terms and codes listed in the mapping table.

4.  For each `part` of an activity in a record-level resource, add a `classified_as` reference for the corresponding role concept.

5.  Inspect the `Type` column in the mapping table to determine the type of activity to be generated.

    **Note:** Roles types still need further consideration and may be used to generate different mappings in a future version of the specification.

6.  If the role type is `production`, then generate a `Production` activity on the carrier-level resource \(`HumanMadeObject` or `DigitalObject`\).

    `7647390`

    Domain: `HumanMadeObject`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/object/54f1fcae-4898-413f-91cd-806d9f4f9cb3",
      "type": "HumanMadeObject",
      "_label": "Illustrations of Shakespeare",            
      "produced_by": {
        "type": "Production",
        "part": [
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/28a98ded-4a66-4c12-a175-20a3733428fa",
                "type": "Person",
                "_label": "Bunbury, Henry William, 1750-1811"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/a18e0571-0842-4f9c-86de-3229e64dc64d",
                "type": "Person",
                "_label": "Bartolozzi, Francesco, 1727-1815"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/ec100aa5-11c4-47af-8c42-f21af2cbea27",
                "type": "Person",
                "_label": "Benedetti, Michele, 1745-1810"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/644c3ba3-0320-4b41-b59b-d1fc902f5abb",
                "type": "Person",
                "_label": "Chapman, J. (John), active 1792-1823"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/514f84c1-8861-48b1-b3e9-5d5f00647c0b",
                "type": "Person",
                "_label": "Cheesman, Thomas, 1760-"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/61c133b7-ee19-45ad-a7c6-57216f7f349b",
                "type": "Person",
                "_label": "Coles, J."
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/e01c532d-8281-4be2-9911-7896a7c01065",
                "type": "Person",
                "_label": "Duterrau, Benjamin, 1767-1851"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/3082e61d-2a84-4cd8-9a85-58091df39bd5",
                "type": "Person",
                "_label": "Gardiner, W. N. (William Nelson), 1766-1814"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/8b303da9-5350-43be-9587-df56cd45b75f",
                "type": "Person",
                "_label": "Leney, William Satchwell, 1769-1831"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },    
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/61128e1b-2b5a-42ef-800d-8777052b3c5a",
                "type": "Person",
                "_label": "Meadows, Robert Mitchell"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/5ce84446-6e6a-433b-8364-f1ddfbf75ea1",
                "type": "Person",
                "_label": "Shenner"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/12b1555a-9e61-45d3-9a4d-200f15f908e9",
                "type": "Person",
                "_label": "Tomkins, Peltro William, 1759-1840"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          },
          {
            "type": "Production",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/82efbe04-d078-43a7-8351-b0ef3b8b7bea",
                "type": "Person",
                "_label": "Vandenbergh, Ignatius Joseph, 1752-1824"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/printmaker-role",
                "type": "Type",
                "_label": "Printmaker"
              }
            ]
          }
        ]
      }
    }
    ```

7.  If the role type is **not** `production`, then generate a `Creation` activity on the content-level resource \(`LinguisticObject`, `VisualItem`, or `Set`\).

    `693`

    Domain: `LinguisticObject`

    ```
    {
      "created_by": {
        "type": "Creation",
        "part": [
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/70ef44e6-621f-4edb-a13d-a7f2149229d5",
                "type": "Person",
                "_label": "Ricœur, Paul"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/81b7e2c2-b7bb-4bcb-a806-9bfc1838e317",
                "type": "Type",
                "_label": "Author"
              }
            ]
          },
          {
            "type": "Creation",
             "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/person/9011fee1-8916-4117-a07b-1519667f121d",
                "type": "Person",
                "_label": "Savage, Denis"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/271d291f-0d42-4abf-bf43-070b241edc98",
                "type": "Type",
                "_label": "Translator"
              }
            ]
          },
          {
            "type": "Creation",
            "carried_out_by": [
              {
                "id": "https://lux.collections.yale.edu/data/group/cdbe8c98-a3a6-4f7e-a20d-698cbe87dcc2",
                "type": "Group",
                "_label": "Samuel R. Delany Library (Beinecke Rare Book and Manuscript Library). Working Library"
              }
            ],
            "classified_as": [
              {
                "id": "https://lux.collections.yale.edu/data/concept/e7e0a406-3b6c-4a89-b6c7-96536c08553c",
                "type": "Type",
                "_label": "Contributor"
              }
            ]
          }
        ]
      }
    }
    ```

8.  For each `6XX`, field, inspect each subfield `e` \(all but `611`\), `j` \(only `611`\), and `4` \(all\) for a role term or code.

9.  [Normalize](../../glossary/normalization.md) and match role terms in `e` or `j` and role codes in `4` against the top-level entities corresponding to the terms and codes listed in the mapping table.

10. If the role term in `$e` is `depicted` or the code in `$4` is `dpc`, then generate a reference using the `represents` property rather than `about`.

    `4887522`

    ```
    {
      "represents": [
        {
          "id": "https://lux.collections.yale.edu/data/person/fbb6aff5-5c18-4653-8db8-8cff23988ca4",
          "type": "Person",
          "_label": "Broughton, Jack, 1704-1789"
        }
      ]
    }
    ```

11. Else, for all other `6XX` role terms or codes, construct a complex subject heading \(person/concept\) with the agent entity and role term as facets.

    1.  For embedded reference instructions, see [People as subjects](../../concepts/people_as_subjects.md) or [Groups as subjects](../../concepts/groups_as_subjects.md).

    `6146780`

    ```
    {
      "@context": "https://linked.art/ns/v1/linked-art.json",
      "id": "https://lux.collections.yale.edu/data/person/6e2bc024-ad8b-4906-95ab-83f441a1d306",
      "type": "Type",
      "_label": "Schrade, Paul -- Interviewee",
      "identified_by": [
        {
          "type": "Name",
          "content": "Schrade, Paul -- Interviewee",
          "classified_as": [
            {
              "id": "http://vocab.getty.edu/aat/300404670",
              "type": "Type",
              "_label": "Primary Name"
            }
          ]
        }
      ],
      "created_by": {
        "type": "Creation",
        "influenced_by": [
          {
            "id": "https://lux.collections.yale.edu/data/person/6e2bc024-ad8b-4906-95ab-83f441a1d306",
            "type": "Person",
            "_label": "Schrade, Paul"
          },
          {
            "id": "https://lux.collections.yale.edu/data/concept/e7e0a406-3b6c-4a89-b6c7-96536c08553c",
            "type": "Type",
            "_label": "Interviewee"
          }
        ]
      }
    }
    ```


**Parent topic:**[Concepts](../../concepts/concepts.md)

