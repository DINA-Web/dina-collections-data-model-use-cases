# 15. Search specimens by taxon

## Background/Motivation

A user wants to search all specimens based on a taxon name.

## Actors
Collection manager: A person working with the collections system, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
None

## Course of events
1. User enter the name of a taxon
1. The system display all specimens where the current identification is matching the provided taxon name

## Alternative paths
### Searching in all identifications
1. User enter the name of a taxon
1. The system display all specimens where any of the identification is matching the provided taxon name

### Searching using taxonomy 
1. User enter the name of a taxon
1. The system display information about the name (see [30. Search taxon names](../taxonomy/30-Search_taxon_names.md))
1. The system display all specimens where the current identification is related to the taxon (e.g. including synonyms)

## Success post-conditions

1. The specimen information is saved in the database and a unique identifier is assigned to it.

## Notes

## Model treatment
