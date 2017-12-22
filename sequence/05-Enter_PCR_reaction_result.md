# 05. Enter PCR reaction result

## Background/Motivationn

A user wants to enter the results of a PCR reaction.

## Actors
Lab technician

## Preconditions
- [04. Add a PCR reaction](04-Add_a_PCR_reaction.md)
- Have the results of the reaction

## Course of events
1. The user selects the PCR reaction matching the physical tube
1. The user enters the result of the reaction:
   - Good band
   - Multiple bands
   - No band

## Alternative paths
1. The user selects a PCR batch that contains multiple PCR reactions
1. The user uploads an external source (e.g. a tabular file based on a pre-defined template) containing all the results of the PCR reaction results from the batch

## Success post-conditions

1. All the provided PCR reaction results are saved in the database
1. Each result is linked to its PCR reaction

## Notes

## Model treatment
