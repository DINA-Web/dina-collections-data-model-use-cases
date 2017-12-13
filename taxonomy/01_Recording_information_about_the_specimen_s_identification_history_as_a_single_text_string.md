# 1. Recording information about the specimen’s identification history as a single text string. [Herbarium GB]

## Background/Motivation
A collection manager wants to record a specimen's identification history (including the current identification) as a collection of event records.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A specimen has been recorded in the database. The user has identification information for this specimen.

## Course of events
  1. The user selects the specimen record to edit.
  2. The user enters the identification history into separated text inputs.

## Alternative paths

## Success post-conditions
The identification history data is persisted to the database and is then readable from the client application.

## Notes
Example fields: genus, species, date, author