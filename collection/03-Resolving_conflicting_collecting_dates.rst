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