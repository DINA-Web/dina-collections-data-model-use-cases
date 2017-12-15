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