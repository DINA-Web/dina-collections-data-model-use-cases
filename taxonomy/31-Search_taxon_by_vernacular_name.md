# 30. Search taxon names

## Background/Motivation

A user wants to find information associated with a particular taxonomic name from a vernacular name

## Actors
Collection manager: A person working with the collections system, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
At least one taxon exists in the taxonomy database.

## Course of events
1. User enters a string representing a full or partial vernacular name
1. Optionally, the user provide the language (e.g. en) to use for the search
1. System presents a list of potential taxon names to the user
1. User selects appropriate name from list
1. System presents information associated with that name

## Alternative path 2: Autocomplete

1. User enters a string representing a part of a vernacular name (>= 3 letters)
1. Optionally, the user provide the language (e.g. en) to use for the search
1. System presents a list of potential taxon names to the user
1. User selects appropriate name from list
1. System presents information associated with that name

## Success post-conditions

1. User selects the correct taxon.

## Notes

## Model treatment
