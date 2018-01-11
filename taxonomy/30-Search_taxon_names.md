# 30. Search taxon names

## Background/Motivation

A user wants to find information associated with a particular taxonomic name.

## Actors
Collection manager: A person working with the collections system, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
At least one taxon exists in the taxonomy database.

## Course of events
1. User enters a string representing a full or partial taxonomic name
1. System presents a list of potential taxon names to the user
1. User selects appropriate name from list
1. System presents information associated with that name

## Alternative path 1: Filtering results

1. User enters a string representing a full or partial taxonomic name
1. System presents a list of potential taxon names to the user
1. The list is long, so user wants to filter the list of results to more easily find the right name
1. User enters filter criteria (see [32-Query taxa](https://github.com/DINA-Web/dina-use-cases/blob/master/taxonomy/32-Query_taxa.md))
1. System filters list based on criteria and presents filtered list to user.
1. User selects appropriate name from list.
1. System presents information associated with that name

## Alternative path 2: Autocomplete

1. User enters a string representing a part of a taxonomic name (>= 3 letters)
1. System presents a list of potential taxon names to the user
1. User selects appropriate name from list
1. System presents information associated with that name

## Success post-conditions

1. User selects the correct taxon.

## Notes

* Based on section 2.1 of [PlutoF use case doc](https://plutof.ut.ee/assets/varia/manuals/docs/taxonomy_manual_3_en.pdf).
* for step 2 ("System presents a list of potential taxon names to the user"), the search implementation could be some of all of 1) exact; 2) partial based on string matching; 3) taxonomically-aware (return synonyms, warnings about homonyms, etc).
* "information" could be : taxon records, specimen records, identification records, etc. 

## Model treatment
