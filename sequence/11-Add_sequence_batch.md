# 11. Add sequence batch

## Background/Motivation

A user wants to enter a new sequence batch.

## Actors
Lab technician

## Preconditions
- [10. Enter PCR reaction result](10-Enter_PCR_reaction_result.md)

## Course of events
1. The user selects a source PCR batch
1. The user selects the Gene Region and a primer
1. The user selects which PCR Reaction should be part of the Sequence Reaction
1. Optionally, the user repeats the previous steps using different input from step 1) or 2)

## Alternative paths

## Success post-conditions

1. The sequence batch is saved in the database.
1. The sequence reactions are linked to their source PCR batch

## Notes

## Model treatment
