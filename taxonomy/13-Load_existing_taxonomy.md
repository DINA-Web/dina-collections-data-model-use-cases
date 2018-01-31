# 13. Load existing taxonomy

## Background/Motivation
The user wants to migrate taxonomy data into the system via spreadsheet/text/DwC-A/yaml.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
The user has existing taxonomy data in an importable format.

## Course of events

## Alternative paths

## Success post-conditions
The data is successfully imported into the system.

## Notes
  * Add a new specimen record with a determination
    * lookup name 
    * match accepted names to synonyms (search synonyms within a storage classification (locate names))
  * lookup children and ancestors of a taxon
  * add and search from a list of orphaned names
  * add a name to the list of accepted names
  * name CRUD (make an existing name (which is not a synonym) a synonym; make a synonym an accepted name; ...)
