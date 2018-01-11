# 32. Query taxa

## Background/Motivation

A user wants to find taxa based on some parameters.

## Actors
Collection manager: A person working with the collections system, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
At least one taxon exists in the taxonomy database.

## Course of events
1. User enters the value for one or more of the folling parameters: rank, name, classification, ancestor (of a single taxon key), 
return_related [ancestor, parent, siblings, immediate_children, basionym, accepted]
1. System presents a list of potential taxon to the user

## Success post-conditions

1. User can see a list of taxon

## Notes
Can be combined with:
 - [30-Search taxon names](https://github.com/DINA-Web/dina-use-cases/blob/master/taxonomy/30-Search_taxon_names.md)
 - [31-Search taxon by vernacular name](https://github.com/DINA-Web/dina-use-cases/blob/master/taxonomy/31-Search_taxon_by_vernacular_name.md)

## Model treatment

