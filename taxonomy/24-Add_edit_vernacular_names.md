# 24. Add/edit vernacular names

## Background/Motivation
A collection manager wants to add or edit vernacular names for a taxon.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A taxon record exists.

## Course of events
  1. The user navigates to the taxon record.
  2. The user indicates the need to add or edit a vernacular name.
  3. The user selects the language of the vernaculare name.
  4. The user enters the vernacular name.

## Alternative paths

## Success post-conditions
The changes to the taxon's vernacular names are persisted to the database, and are then viewable from the user interface.

## Notes
The available languages are coming from a control vocabulary and should probably be configurable.
