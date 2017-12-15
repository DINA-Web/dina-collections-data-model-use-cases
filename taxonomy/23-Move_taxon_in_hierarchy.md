# 23. Move taxon in hierarchy

## Background/Motivation
A collection manager wants to move a taxon to a different hierarchical position.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A taxon record exists with or without a hierarchical position.

## Course of events
  1. The user navigates to the taxon record to be modified.
  2. The user enters the new hierarchical position.

## Alternative paths

## Success post-conditions
The new hierarchical position is persisted to the database and is then viewable from the user interface when looking at the taxon itself and at any hierarchical views.

## Notes