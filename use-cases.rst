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


Marking a DNA-sample as contaminated
------------------------------------

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


Sending part of a preparation on loan
-------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to send only a part of a preparation on loan,
without being required to create a new preparation. In this use case, a
*preparation* is understood as a physically coherent unit that contains 
detachable parts. This may for example involve cases when there is a jar with 
five fishes of the same species and the collection manager wants to send only 
one of the fishes on loan.

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
#. The collection manager identifies (enters or generates an ID-number) and
   registers the specimen to be sent on loan.
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

To begin with, the batch represents one material sample and one identifiable 
unit. The single material sample is then split into two material samples (and 
consequently two identifiable units) consisting of (1) the specimen to be sent 
out on loan, and (2) the remaining specimens. The two identifiable units belong 
to the same individual group and thus share the determination. They are also 
either attached to the same artificial unit, or belongs to the same assemblage.
The material sample corresponding to the specimen sent on loan make up the 
transaction unit, which means that no new preparation needs to be created.

In the alternative path, no new material sample is created. Instead, an
"unspecified part" of the material sample constitutes the transaction unit.
This is not the preferred way of handling the loan since it may be impossible
to trace which part of the material was actually sent on loan.


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
that situations like this will become more common in future, as curators
discover more of shared history between specimens. At its heart, this use case
demonstrates the need of handling information sources independently from
specimens.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

Each specimen represent a material sample. To begin with, each material sample
has its own collecting event, and each collecting event an interpreted
collecting date. In addition, each material sample also has an information
source with a verbatim collecting date. When the two material samples get
connected to the same collecting event, only one interpreted collecting date 
is saved for that event. The verbatim information is left unchanged.


Creating a derived specimen that represents the same individual
---------------------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to create a new specimen (sample) from an existing
one. The parent specimen may have identificaitons which the child specimen is 
supposed to inherit.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

Preconditions
~~~~~~~~~~~~~

A sample has been registered, together with a determination. A subsample has
then been taken from the registered sample.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the specimen from which the new sample has 
   been subsampled.

#. The collection manager creates a derived sample from the selected sample.

#. The system asks the collection manager whether (1) the new sample should
   belong to a separate preparation and (2) whether the new sample should
   represent a new individual or group of individual.

#. The collection manager chooses to treat the new sample as belonging to the
   same a individual or group of individual, but as belonging to a separate
   preparation.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A derived specimen (sample) has been created with a separate preparation. 
The derived sample shares the determination with the sample from which it was derived.


Notes
~~~~~

None.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

Two new identifiable units are created: one representing the child specimen, 
and one representing the remainder of the parent specimen. A new material 
sample is created for the child sample. All three identifiable units (including
the one representing the parent specimen) are connected to the same individual
group, and thus share all determinations.


Creating a derived specimen that represents a different taxon
-------------------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A collection manager wishes to take a part of a cataloged specimen (parent 
specimen) and create a new specimen (derived specimen) with a separate catalog 
number. Any previous identification or observation associated with the parent 
specimen should be inherited by the derived specimen. From the derived 
specimen, it should also be possible to trace the parent specimen's catalog 
number.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

**Researcher** – a person that want to use material from the collection.


Preconditions
~~~~~~~~~~~~~

A researcher realizes that a cataloged specimen actually represents two 
individuals and identify them as belonging to different taxa. Subsequently,
the collection manager picks one of the individuals and make it a separate 
specimen.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the record that represents the parent 
   specimen.

#. The collection manager chooses to create a derived record from the 
   selected record.

#. The system asks the user whether the record should represent the same

   - physical unit?
   
   - individual (or group of individuals)?
   
   - catalog number?

#. The collection manager creates a new record that represents a different 
   physical unit, a different individual, and a different catalog number.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A new record has been created for the new specimen. All previous 
identifications made to the parent speciemen is present in the identification 
history log. The new specimen has been assigned a new catalog number, and it
is clear from which specimen it was derived.


Notes
~~~~~

Splitting specimens into smaller units is common in many collections. Though, 
not all collections care about recording the history of the splitting
events. This use case is very similar to creating


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

The parent specimen is originally recorded as one identifiable unit (and 
consequently a single individual group, a single material sample, and a single 
cataloged unit). When a the new specimen has been prepared, two new 
identifiable units are created: one representing the new specimen and one
representing the remainder of the parent specimen. A new individual group, a
new material sample and a new cataloged unit is then also created for the new 
speciemen.


-------------------


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

#. The system adds a default highest level preparation for the specimen.

#. The collection manager identifies (enters or generates an ID-number for) the
   specimen.

#. The collection manager enters relevant information about the specimen and
   the default preparation.

#. The collection manager selects the default preparation and creates a child
   preparation.

#. The collection manager enters information about the child preparation.

#. The collection manager moves the specimen to the new child preparation.

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

None.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

One material sample (with one identifiable unit) that belong to a physical unit
that in turn belong to the highest level physical unit.

-------------------


Transcribing text from an information source - draft
----------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Sometimes a user wants to add information that is available without making 
interpretations of the content. In other words, the user wants to record whats
there – not the actual meaning of the information. This use case involves how 
to deal with those situations, but involves also how to record information 
about the source.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.

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

Many collections record verbatim text, but are usually less concerned with 
where the information comes from.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~


-------------------


Adding a determination based on an image - draft
------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Some collections treat physical or digital photos as collection object. This
is especially important whan the original physical material has been lost or
destroyed. With small animals, for example, it is common that all material is
consumed in a genetic analysis. In these cases may the image serve as valuable
historical reference. As with physical material, an image may be redetermined
as something else.

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


-------------------


Adding two observations of the same kind - draft
------------------------------------------------

Sometimes a user wishes to add more than one observation of the same kind,
without necessarily deciding on their respective official status. For example,
the body weight of an animal may have been recorded at two separate occasions.


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


-------------------


Adding two collecting events for an individual - draft
------------------------------------------------------

There may be more than one collecting event for a single biological individual. 
An example involves the botanist who collects material (e.g. flowers and fruit, 
respectively) from a tree at two different occasions during a season.


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


-------------------


Recognizing that a specimen is type for two names (at the same time) - draft
----------------------------------------------------------------------------

A specimen can be a nomenclatural type for more than one name at the same time.
This is rare, but can be seen for example in botany where two duplicate 
specimens located at different herbaria has been used (unintentionally) to 
typify different names.


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

-------------------


Add a second-level catalog number to a specimen - draft
-------------------------------------------------------

The situation to have two-level-identifiers for specimens is quite common. 
Sometimes is the lowest level identifier composed of the higher level 
identifier plus some suffix.


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
