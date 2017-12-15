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