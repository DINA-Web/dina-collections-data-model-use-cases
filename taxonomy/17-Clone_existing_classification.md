# 17. Clone existing classification

## Background/Motivation
A collection manager wants to clone an existing classification (whole or sub-branch). It can be from a consensus classification.

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
The user wants to clone an existing classification record.

## Course of events
  1. The user opens a form to clone an existing classification.
  2. The user enters the mandatory tree name string and mandatory link to the higher taxon node.
  3. The user links to the origin tree. [Optional]
  4. The user specifies access rights for viewing and editing the classification. Each action can be restricted to public, workgroup/users, or private.

## Alternative paths

## Success post-conditions
The new classification clone record is persisted to the database and is then viewable from the user interface. The specified access rights are enforced.

## Notes
Based on PlutoF use case from https://plutof.ut.ee/assets/varia/manuals/docs/taxonomy_manual_3_en.pdf