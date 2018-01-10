12. Add a second-level catalog number to a specimen
---------------------------------------------------


Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

The situation to have two-level-identifiers for specimens is quite common.
The lowest level identifier is sometimes composed of the higher level identifier plus a suffix.
An example can be a herbarium sheet with a branch of a tree that includes a fruit. In this example, the sheet could have the catalog number "1234" and the branch "1234-A" and the fruit "1234-B". Another example could be a jar of bugs or a box with parts of fungi.

Actors
~~~~~~
Collection manager

Preconditions
~~~~~~~~~~~~~

Course of events
~~~~~~~~~~~~~~~~ 
  1. The user selects the specimen record
  1. The user indicates the need to add a new "sub identifier"
  1. The user enters the data specific to the "sub identifier" including the nature of the link between the "parent" specimen and itself

Alternative paths
~~~~~~~~~~~~~~~~~


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~
The link between the higher level identifier and the sub identifier is preserved. All the data specific to the sub identifier is saved to the database.
