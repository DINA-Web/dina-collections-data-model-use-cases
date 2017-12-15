Registering a specimen that belongs to a nested preparation
-----------------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to register a specimen that belong to a preparation
that in turn belong to another preparation, for example a moss inside a package
that has been mounted on a herbarium sheet.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.


Preconditions
~~~~~~~~~~~~~

An unregistered specimen belongs to a preparation that in turn belongs to
another preparation.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager opens an empty specimen record.

#. The system adds a default preparation for the specimen.

#. The collection manager identifies (enters or generates an ID-number for) the
   specimen.

#. The collection manager enters relevant information about the specimen
   (e.g. that it is a moss) and the default preparation (e.g. that it is a
   herbarium sheet).

#. The collection manager selects the default preparation and creates a child
   preparation.

#. The collection manager enters information about the child preparation
   (e.g. that it is a package mounted on the herbarium sheet).

#. The collection manager associates the specimen record with the child
   preparation (instead of the parent preparation).

#. The collection manager saves the specimen record.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A specimen has been registered as belonging to a physical unit that in turn
belongs to another physical unit.


Notes
~~~~~

There are several reasons for recognizing nested preparations: First, one
may want to record data separately for different container objects (like for
example different preparation dates for the package and the herbarium sheet).
Secondly, one may want to describe the physical position of one or more
samples with respect to each other and to the full object that is being stored
on the shelf. This is especially useful if there are multiple small samples
grouped together. Another reason has to do with transaction management. Some
collections allow parts of their stored objects to be sent on loan. For
example, a pollen slide may be detached from its herbarium sheet before being
sent on loan. Nested preparations allows the user to indicate what
material has been sent out on loan and what is still on the shelf.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

One material sample (with one identifiable unit) that belong to a physical unit
that in turn belong to the highest level physical unit.