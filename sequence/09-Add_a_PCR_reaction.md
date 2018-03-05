# 09. Add a PCR reaction

## Background/Motivationn

A user wants to enter a new PCR reaction for a sample.

## Actors
Lab technician

## Preconditions
- [04. Add a sample](04-Add_a_sample.md)
- [08. Add a PCR batch](08-Add_a_PCR_batch.md)

## Course of events
1. The user enters the well coordinates of the reaction’s tube
1. The user selects the sample to which the PCR reaction will be applied
1. The user selects the PCR Batch
1. If required, the user overides values of the gene region and primers from the PCR batch

## Alternative paths
 1. The system provides a PCR Reaction template (e.g. for a 96 well plate)
 1. The user fills the information in the template
 1. The user selects the PCR Batch
 1. The user uploads the template to the system
The Post-Condition will be for each element filled in the template.

## Success post-conditions

1. A unique identifier is assigned to the PCR reaction information
1. The PCR reaction information is saved in the database
1. The PCR reaction is linked to the sample
1. The PCR batch is linked to the PCR reaction

## Notes

## Model treatment
