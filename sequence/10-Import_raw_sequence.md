# 10. Import raw sequence file

## Background/Motivationn

A user wants to import a raw sequence file.

## Actors
Lab technician

## Preconditions
- Have a sequence file in ab1 format

## Course of events
1. The user selects and uploads the raw sequence file
1. The user links the raw sequence file to the Sequence Reaction

## Alternative paths
1. The user configures the file name convention to be used for raw sequence files
1. The system monitors a predefined folder for any new files
1. For each new files, the system extract the information from the file name and automaticaly links the raw sequence to the Sequence Reaction.


## Success post-conditions

1. The raw sequence file is copied to the server filesystem
1. The raw sequence file is linked to the sequence reaction

## Notes

## Model treatment
