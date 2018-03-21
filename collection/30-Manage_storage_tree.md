# 30. Manage Storage Tree

## Background/Motivation
A collection manager wants to record the storage tree under which the specimens are physicaly stored.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
None

## Course of events
  1. The user imports a tree based on an existing taxonomy
  2. The user can add/change/delete information on each node (e.g. preparation)
  3. The user can move parts of the tree
  4. The user save the tree

## Alternative paths

## Success post-conditions
The tree is saved in the database and is complety detached from its source (the existing taxonomy).

## Notes
When the original taxonomy is modified the storage tree should not follow. They are 2 different things.
