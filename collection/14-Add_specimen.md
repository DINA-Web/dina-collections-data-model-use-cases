# 14. Add a specimen

## Background/Motivation

A user wants to enter the data related to a specific physical specimen.

## Actors
Collection manager: A person working with the collections system, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
None

## Course of events
1. User indicates the intention to enter a new specimen
1. The system presents an empty specimen record (some fields may be pre-filled) 
1. User enters the information available about the physical specimen
   - Identifier of the physical specimen (e.g. catalogNumber)
   - Information about the event (who, where, when)


## Alternative paths
- [4. Creating a derived specimen that represents the same individual](04-Creating_a_derived_specimen_that_represents_the_same_individual.rst
)
- [5. Creating a derived specimen that represents a different taxon](05-Creating_a_derived_specimen_that_represents_a_different_taxon.rst) 
- [6. Registering a specimen that belongs to a nested preparation](06-Registering_a_specimen_that_belongs_to_a_nested_preparation.rst)
- [7. Transcribing text from an information source](07-Transcribing_text_from_an_information_source.rst)

## Success post-conditions

1. The specimen information is saved in the database and a unique identifier is assigned to it.

## Notes

## Model treatment
