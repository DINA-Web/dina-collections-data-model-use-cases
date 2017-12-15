# 12. Flagging an identification as the "current identification"

## Background/Motivation
A collection manager wants to distinguish the current identification.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A specimen record is persisted to the database. An identification for the specimen is recorded or is being recorded by the user. 

## Course of events
  1. The user edits the identification meant to be the current identification.
  2. The user marks the identification as being the current identification. 

## Alternative paths
  1. The user views a list of a specimen's identifications.
  2. The user marks an identification from the list as being the current identification.

## Success post-conditions
The identification is flagged as current in the database and this flag is viewable from the identification's record and from the associated specimen's record in the client application.

## Notes