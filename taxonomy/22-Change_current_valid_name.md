# 22. Change current valid name

## Background/Motivation
A collection manager wants to change a taxon's currently valid name.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
 - At least 2 taxa representing the same "thing" shall exist in the database
 - 1 shall be the current accepted name
 - 1 shall be a synonym or a new taxon

## Course of events
  1. The user selects the taxon record to edit.
  2. The user ensures that valid name, synonym type, and higher taxon where this name was described in, are specified.

## Alternative paths

## Success post-conditions
The taxon's valid name is changed in the database and the other taxon is now a synonym.

## Notes
This use case basically covers "replace accepted name by its synonym" and "change synonym into a new accepted name"
Based on PlutoF use case from https://plutof.ut.ee/assets/varia/manuals/docs/taxonomy_manual_3_en.pdf
