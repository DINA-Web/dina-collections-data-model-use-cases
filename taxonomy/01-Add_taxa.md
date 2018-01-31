# 01. Add taxa

## Background/Motivation
A collection manager wants to add a taxon.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
The user has data for a new taxon record to add, including tree name, higher taxon, taxon rank, and epithet.

## Course of events
  1. The user opens a form to create a new taxon.
  2. The user enters the taxon data, including tree name, higher taxon, taxon rank, and epithet.
  3. The user enters taxon name concept, author, year described in, nomenclature status, valid name, Uid, user defined id, remarks, citation text, and vernacular names. [Optional]
  4. The user saves the taxon.

## Alternative paths

## Success post-conditions
The new taxon data is persisted to the database and is then viewable from the user interface.

## Notes
Based on PlutoF use case from https://plutof.ut.ee/assets/varia/manuals/docs/taxonomy_manual_3_en.pdf
Focus on adding leaves only for v1.
