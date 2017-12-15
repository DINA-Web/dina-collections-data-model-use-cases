# 4. Selecting one or more determiners from a catalogue of agents (or adding the agents to the catalogue if they are not there)

## Background/Motivation
A collection manager wants to select one or more determiners from a catalogue of agents (or add the agents to the catalogue if they are not there).

## Actors
Collection manager (in a wide sense) – a person that uses the system to manage a collection, possibly a curator, a collection manager, a collection assistant, or data capture person.

## Preconditions
An identification has been recorded, or is being recorded.

## Course of events
  1. The user selects the identification record to edit.
  2. The user adds a new agent record to the catalogue. [Optional]
  3. The user selects the determiner from a list of agents.

## Alternative paths

## Success post-conditions
The selected determiners are associated to the identification record. 

## Notes
Agent lookups may be a service from a different module.

## Model treatment: nrm
Determiners are associated to the selected identification. Any new agents specified are inserted as the agent model.