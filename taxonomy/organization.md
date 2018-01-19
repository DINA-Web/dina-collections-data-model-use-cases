# Organization of taxonomy use cases

Organizing the taxonomy use cases; categorization and prioritization.

## Possible categories:

Some of these categories are orthogonal.

* ~~identification : use cases related to identification / determination (the association between a specimen and a taxon)~~ *all identification cases moved to collections*
* reference taxonomy : use cases important for how we organize specimens taxonomically in the collection
* research : use cases important for taxonomic research
* editing : use cases about editing the taxonomy
* search : use cases about searching the taxonomy database

## Actions implied by the use cases

This list might help us find holes, or aspects of the use cases that are primarily relevant to other modules.

* display a `classification` and allow selection of a `taxon` (03)
* create a `classification` (16, 17, 29)
* add / edit `taxon` metadata (18, 19, 22, 23, 24, 25, 26, 27)
* edit `classification` - adding, deleting, moving taxa (03, 18, 19, 20, 21, 23, 25, 26)
* export taxonomy data (28)
* find a `taxon` based on name string (30)

Cases about these actions moved to collections:
* associate an `identification` with a `specimen` (01, 02, 09, 12)
* add / edit `identification` metadata (02, 08, 09, 10, 11, 12, 13, 14)
* associate a `determiner` with an `identification` (02, 04, 10)
* select a `determiner` (person) (04)
* add a `determiner` (04)
* associate a `publication` with an `identification` (05, 06)
* select a `publication` from a list of `publications` (07)

## Use case data types

These are data types mentioned in the use cases, along with some questions about storage.

* `specimen` : items in the collection; stored in collections module
* `taxon` :  stored in taxonomy module; questions about how we model (identifiers, name strings, taxon concepts)
* `identification` : information about how a `determiner` states that a `specimen` is an example of a `taxon`; includes many fields; stored in taxonomy module or collection module?
* `determiner` : a person; how and where are we storing people? linked to LDAP in any way?
* `classification` : a hierarchy of taxa (parent-child relationships); stored in taxonomy module
* `publication` : published scientific document; reference string and / or DOI; associated with identifications; store as identification field vs separate table for re-use?
