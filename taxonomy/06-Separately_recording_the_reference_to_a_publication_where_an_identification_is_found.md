# 6. Separately recording the reference to a publication where an identification is found

## Background/Motivation
A collection manager wants to separately record the reference to a publication where an identification is found (i.e. the source reference).

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
An identification is recorded in the database. The user has a reference to the identification's source publication.

## Course of events
  1. The user inputs the reference to the publication.
  2. The user links an identification to the publication. [Optional]

## Alternative paths
  1. The user edits an identification record.
  2. The user inputs the reference to the identification's source publication. 

## Success post-conditions
The publication reference is persisted to the database and is then viewable from the user interface. Associations between the publication and identifications are persisted.

## Notes
The reference should be a text field.