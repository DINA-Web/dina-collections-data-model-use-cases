Use cases
=========

.. contents:: Table of contents
   :depth: 1
   :backlinks: none
   :local:

-----------------------------------


Contaminated DNA-sample
-----------------------

Background
~~~~~~~~~~

This use case involves two different relations between determination and
physical objects: a determination may *apply to* one set of objects, but
at the same time be *based on* only a subset of the first set.


Use case description
~~~~~~~~~~~~~~~~~~~~

#. A single plant individual is dried and mounted on a herbarium sheet.
#. Three DNA-samples (labeled "sample A", "sample B", and "sample C"),
   are prepared at separate occasions from the preserved specimen.
#. The plant individual is determined as species X based on a DNA-sequence
   derived from sample A.
#. The determination to species X is considered doubtful and contamination
   of sample A is suspected.
#. The plant individual is redetermined as species Y based on new
   DNA-sequences derived from sample B and C, respectively.
#. Sample A is finally discarded after concluding that it has been
   contaminated.


Model treatment
~~~~~~~~~~~~~~~


Remarks
~~~~~~~

This is not a very common scenario, but important to support in order to
minimize errors.


Sending part of a preparation on loan
-------------------------------------

Background
~~~~~~~~~~


Use case description
~~~~~~~~~~~~~~~~~~~~

#. Two fishes of the same species are captured during the same collecting
   event and placed in a jar of alcohol.
#. At the museum, the jar is labeled with a catalog number.
#. One fish is then taken out of the jar, labled with an additional
   ID-tag, and sent out on loan.
#. When the loaned material is returned, the fish is put back into
   the original jar again.


Remarks
~~~~~~~
