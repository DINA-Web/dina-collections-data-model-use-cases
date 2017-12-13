# 13. Distinguish the original identification made by the collector

## Background/Motivation
A collection manager wants to distinguish the original identification made by the collector.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A specimen record is persisted to the database. An identification for the specimen is recorded or is being recorded by the user.

## Course of events
  1. The user queries the collection of identifications to get the identification with the earliest date by the collector.

## Alternative paths

## Success post-conditions
Whether an identification is the current identification is viewable from the identification's record and from the associated specimen's record.

## Notes