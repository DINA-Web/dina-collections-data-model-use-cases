# 17. Recording identification information

## Background/Motivation
A collection manager wants to record information from the following (partially overlapping) categories:
  * string with the identification as written in the source
  * taxon name (scientific or vernacular)
  * qualifier (e.g. “cf.”, “aff.”) [Specify 6]
  * type status (i.e. secondary type status information) [Specify 6]
  * name(s) of determiner(s),
  * year (or other date)
  * determiner’s notes (including references)
  * taxon name usage [Specify 6]
  * basis of identification [Specify 6]
  * identification method [Specify 6]
  * reference(s) used for the identification.
  * level of certainty: determiner’s level of confidence in the identification, including an additional boolean value of whether the determiner has expressed doubts regarding the identification

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
A specimen has been recorded in the database. The user has text information from the listed categories for an identification record.
* [taxonomy/16-Search taxon names](https://github.com/DINA-Web/dina-use-cases/blob/master/taxonomy/16-Search_taxon_names.md)

## Course of events
  1. The user selects the specimen record to edit.
  2. The user inputs the information.

## Alternative paths

## Success post-conditions
The identification record is persisted to the database and is then readable from the user interface in labeled fields.

## Notes

## Model treatment: nrm
The information is persisted into separate columns on the identification model.
