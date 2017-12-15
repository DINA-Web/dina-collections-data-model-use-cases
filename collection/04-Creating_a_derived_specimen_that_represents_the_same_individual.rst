4. Creating a derived specimen that represents the same individual
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
