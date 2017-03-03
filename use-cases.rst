Use cases
=========

This document describes system use cases that have implications on model core
of the DINA-Web collection management system. The use cases are written at a
high level, just detailed enough to capture requirements for the development of
the data model core.


.. contents:: Table of contents
   :depth: 1
   :backlinks: none
   :local:

-------------------


Mark a DNA-sample as contaminated
---------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to mark one of two DNA-samples from the same
individual as potentially contaminated.

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
#. [Optional] The collection manager writes a note saying that the sample may
   be contaminated.
#. The system flags the determinations that are associated with the selected
   sample. (The flag indicates that the determination has been based on a
   dubious sample.)


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


Sending part of a preparation on loan
-------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to send only a part of a preparation on loan,
without being required to create a new preparation. This may for example
involve cases when there is a jar with five fishes of the same species and the
collection manager wants to send only one of them on loan.

Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

**Researcher** – a person that want to use material from the collection.


Preconditions
~~~~~~~~~~~~~

A researcher requests material from a preparation with multiple specimens.
The specimens have been registered as a batch with a single determination. The
collection manager picks one specimen to be sent on loan.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the batch record that represents the
   specimen to be sent on loan.
#. The collection manager identifies (enters an ID-number) and registers the
   specimen to be sent on loan.
#. The collection manager creates a loan transaction for the transfer of the
   selected specimen.


Alternative paths
~~~~~~~~~~~~~~~~~

#. The collection manager selects the batch record that represents the
   specimen to be sent on loan.
#. The collection manager creates a loan transaction for the transfer of the
   selected specimen.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

The loaned material has been registered as part of a loan transaction. No new
preparation has been created.


Notes
~~~~~

Why not create a new preparation for the specimen sent on loan? Answer:
Creating a preparation would involve extra work for the collection manager and
potentially also require more physical storage.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

To begin with, the batch represents one material sample, one preparation and
one identifiable unit. The single material sample is then split into two
material samples (and consequently two identifiable units) consisting of (1)
the specimen to be sent out on loan, and (2) the remaining specimens. The two
identifiable units belong to the same individual group and thus share the
determination. They also belong to the same preparation. The material sample
corresponding to the specimen sent on loan is the transaction unit, which means
that no new preparation needs to be created.

In the alternative path, no new material sample is created. Instead, an
"unspecified part" of the material sample constitutes the transaction unit.
This is not the preferred way of dealing with the loan since it may be
impossible to trace what part of the material was actually sent on loan.


Resolving conflicting collecting dates
--------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Two specimens that evidently were collected during the same event have
conflicting source information about the collecting date. The collection
manager wishes to resolve the conflict without loosing any of the original
verbatim information that independently has been associated with the specimens.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

Preconditions
~~~~~~~~~~~~~

Two specimens have been registered separately with different collecting dates.
Both the verbatim date and interpreted date differ between the specimens. The
specimens share a unique field number, so it can be assumed that they have been
collected during the same event.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the two specimen records.

#. The collection manager merges the two collecting events into one.

#. The system notifies the collection manager about the information conflict.

#. The collection manager selects/enters the correct collecting date for the
   collecting event.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

The two specimen are associated with the same collecting event. The interpreted
collecting date for that event has been set. The original verbatim date
information that was associated with the specimens has been preserved.


Notes
~~~~~

It is difficult to tell how common this use case is since users of current
collection management systems often ignore information conflicts. It is likely
that situations like this may become more common in future, as curators
discover more of shared history between specimens. At its heart, this use case
demonstrates the need of handling information sources independently from
specimens.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

Each specimen represent a material sample. To begin with, each material sample
has its own collecting event, and each collecting event an interpreted
collecting date. In addition, each material sample also has an information
source with a verbatim collecting date. The two material samples are then
connected to the same collecting event. Consequently, only one interpreted
collecting date is saved for that event. The verbatim information is left
unchanged.


Deriving a sample from an existing sample
-----------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to create a new sample (specimen) from an existing
one. The parent sample has a determination which the child sample is supposed
to inherit.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

Preconditions
~~~~~~~~~~~~~

A sample has been registered, together with a determination associated with
that sample. A subsample has then been taken from the registered sample.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the sample from which the new sample is
   subsampled.

#. The collection manager creates a derived sample from the selected sample.

#. The system ask the collection manager whether (1) the new sample should
   belong to a separate preparation and (2) whether the new sample should
   represent a new individual or group of individual (i.e. whether it should
   inherit the determination history from the parent sample).

#. The collection manager chooses to treat the new sample as belonging to the
   same a individual or group of individual, but as belonging to a separate
   preparation.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A derived sample has been created with a separate preparation. The derived
sample shares the determination with the sample from which it was
derived.


Notes
~~~~~

None.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

A material sample is created from an existing material sample. The derived
material sample shares the individual group with its parent, but belongs to a
separate preparation. Since the two material samples belong to the same
individual group, they will share the determination.


-------------------

Title
-----
Background/Motivation
~~~~~~~~~~~~~~~~~~~~~
Actors
~~~~~~
Preconditions
~~~~~~~~~~~~~
Course of events
~~~~~~~~~~~~~~~~
Alternative paths
~~~~~~~~~~~~~~~~~
Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~
Notes
~~~~~
Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~
