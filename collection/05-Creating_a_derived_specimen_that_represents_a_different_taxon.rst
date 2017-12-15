5. Creating a derived specimen that represents a different taxon
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
