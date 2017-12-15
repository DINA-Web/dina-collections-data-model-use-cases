Marking a DNA-sample as contaminated
------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to mark one of two DNA-samples from the same
individual as potentially contaminated. This may be needed in order
to trace for example erroneous identifications.


Actors
~~~~~~

**Collection manager** (in a wide sense), – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.


Preconditions
~~~~~~~~~~~~~

Two DNA-samples have been registered as coming from the same biological
individual. The samples have two determinations each that have been entered
into the system. All four determinations conflict with each other, and none has
been selected as the current identification for the individual.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects one of the DNA-sample records and mark it as
   dubious.
#. The collection manager writes a note saying that the sample may be
   contaminated. [Optional]
#. The system flags the determinations that are associated with the selected
   sample. The flag indicates that the determination has been based on a
   dubious sample.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

The dubious sample has been marked as such, and all its associated
identifications are flagged as dubious.


Notes
~~~~~

This use case involves two kinds of relations between determinations and
physical objects: a determination may *apply to* one set of objects, but at the
same time be *based on* only a subset of the first set. There is a need to
capture both these relationships.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

Each DNA-sample represents an identifiable unit. The two identifiable units
belong to the same individual group, to which all determinations *apply*.
In addition, each determination is *based on* either of the two samples.