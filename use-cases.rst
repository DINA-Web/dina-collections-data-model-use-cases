Use cases
=========

This document describes system use cases that have implications on model core
of the DINA-Web collection management system. The use cases are written at a
high level, just detailed enough to capture requirements for the development of
the data model core. The intended audience is anyone interested in the
conceptual understanding of collection management, which may for example
include end users, domain specialists and developers. The document serve as a
knowledge base and is updated continously.

More information about the conceptual model, see the 
`DINA-Web collections data model repository 
<https://github.com/DINA-Web/dina-collections-data-model>`_.

The use cases have not been prioritized!


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
specimens share a unique field number, so one can assume that they have been
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
one. The parent specimen may have taxonomic identificaitons (or other
observations) which the child specimen is supposed to inherit.


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
   represent a new individual or group of individuals.

#. The collection manager chooses to treat the new sample as belonging to the
   same a individual or group of individuals, but as belonging to a separate
   preparation.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A derived specimen (sample) has been created with a separate preparation. 
The derived sample shares the determination with the sample from which it was 
derived.


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
   
   - cataloged unit (i.e. catalog number)?

#. The collection manager creates a new record that represents a different 
   physical unit, a different individual, and a different cataloged unit.


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
events. This use case is  similar to the use case "Creating a derived specimen 
that represents the same individual".


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


-------------------


Transcribing text from an information source
--------------------------------------------


Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Sometimes a user wants to add information that is available without 
interpreting it. In other words, the user wants to record what s there – not 
the actual meaning of the information. This is related to recording metadata 
about the information source.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.


Preconditions
~~~~~~~~~~~~~

A specimen has been registered with a catalog number. The specimen has a label
with what seems to be a place name. This is the only information on the label,
and the information has not yet been entered into the system.


Course of events
~~~~~~~~~~~~~~~~

#. The collection manager selects the specimen record.

#. The collection manager registers the label (just as a "label" attached to
   the specimen).

#. The collection manager transcribes the text on the label as "verbatim 
   locality", and associates the information with the recently created label 
   record.


Alternative paths
~~~~~~~~~~~~~~~~~

None described.


Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

A record for the label has been created and associated with the specimen
record. The text on the label has been entered into the system as a "verbatim
locality".


Notes
~~~~~

Many collections record verbatim text, but are usually less concerned with 
where the information comes from. Though, it may be useful to know whether two
pieces of information (e.g. collecting locality and collecting date) come from
the same source (i.e. the same label).


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

One artificial unit representing the label, one transcribed content 
representing the text transcribed from the label that is of transcribed 
content type "verbatim locality".

-------------------


Adding a determination based on an image - draft
------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Some collections treat digital photos in the same way as physical collection
objects. This is often the case when the original physical material has been 
lost or destroyed (like when small animals are consumed in genetic analyses). 
The image then serves a valuable historical reference. As with any physical 
material, an image may later be identified as a different taxon than the 
current identification.


Actors
~~~~~~

**Collection manager** (in a wide sense) – a person that uses the system to
manage a collection, possibly a curator, a collection manager, a collection
assistant, or data capture person.


Preconditions
~~~~~~~~~~~~~

A photo of a specimen that is no longer kept in the collection.


Course of events
~~~~~~~~~~~~~~~~

Alternative paths
~~~~~~~~~~~~~~~~~

Success post-conditions
~~~~~~~~~~~~~~~~~~~~~~~

Notes
~~~~~

What about the use case when there is both specimen and a photo of that 
specimen?


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~


-------------------


Adding two observations of the same kind - draft
------------------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Sometimes a user wishes to add more than one observation of the same kind,
without necessarily deciding on their official statuses. For example, the body 
weight of an animal may have been recorded at two separate occasions.


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


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~


-------------------


Adding two collecting events for an individual - draft
------------------------------------------------------

There may be more than one collecting event for a single biological individual. 
One example involves the botanist who collects material (e.g. flowers and 
fruits, respectively) from a tree at two different occasions during a season.


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


Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

A specimen can be a nomenclatural type for more than one name at the same time.
This is rare, but can be seen for example in botany where two duplicate 
specimens located at different herbaria has been used (unintentionally) as 
types for different names.


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


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~


-------------------


Add a second-level catalog number to a specimen - draft
-------------------------------------------------------


Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

The situation to have two-level-identifiers for specimens is quite common. 
The lowest level identifier is sometimes composed of the higher level 
identifier plus a suffix.


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


Recognizing an additional individual for a specimen - draft
-----------------------------------------------------------


Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Physical objects may sometimes consist of unseparable individuals. These
individuals may represent the same or different taxa. An example of the latter
is a parasitic plant growing on a host plant of a different species. When a
collection manager wishes to distinguish two or more individuals (or groups of
individuals) they are usually given different catalog numbers.


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
