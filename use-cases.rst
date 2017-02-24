Use cases
=========

.. contents:: Table of contents
   :depth: 1
   :backlinks: none
   :local:


-----------------------------------


Contaminated DNA-sample
-----------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

This use case involves two kinds of relations between determination and
physical object: a determination may *apply to* one set of objects, but
at the same time be *based on* only a subset of the first set.


Use case description
~~~~~~~~~~~~~~~~~~~~

#. A single plant individual is dried and mounted on a herbarium sheet.
#. Three DNA-samples (labeled "sample A", "sample B", and "sample C")
   are prepared from the plant by a researcher at separate occasions.
   The DNA-samples are managed within the same collection as the
   original voucher material.
#. Based on a DNA-sequence derived from sample A, the researcher
   determine the plant individual as species X.
#. The determination to species X is considered doubtful by the researcher
   and contamination of sample A is therefore suspected.
#. The plant individual is redetermined by the researcher as species Y
   based on new DNA-sequences derived from sample B and C, respectively.
#. Sample A is finally discarded by a curator after concluding that it
   has been contaminated.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

The herbarium sheet with the plant specimen constitutes
a preparation, where the dried plant itself is a material sample. Each
DNA-sample is also a material sample that belong to a separate
preparation (probably a microtube). Each of the 4 material samples
contains one identifiable unit.

All 4 identifiable units belong to the same individual group, to which
the two determinations *apply*. In addition, the determination to
species X *is based on* the identifiable unit for sample A, whereas
the determination to species Y *is based on* the two identifiable units
for samples B and C.

Since sample A is a material sample (and a preparation), it can be
deaccessioned and marked as discarded.


Remarks
~~~~~~~

This is probably not a very common scenario, but an important one to
support in order to minimize errors in biological collections.


Sending part of a preparation on loan
-------------------------------------

Background/Motivation
~~~~~~~~~~~~~~~~~~~~~

Some collections send only part of the stored thing on loan. This is
often the case when there are many specimens of the same kind.
Creating separate preparations for every loaned object would require
much space and a lot of extra work for the curators.


Use case description
~~~~~~~~~~~~~~~~~~~~

#. A researcher captures two fishes of the same species during
   a single collecting event, and places them in a jar of alcohol.
#. At the museum, a curator labels the jar with a catalog number.
#. Another researcher then send a loan request for one of the two fishes.
#. The curator pick one fish from the jar, label it with an ID-tag,
   and send it out on loan.
#. When the loaned material is returned, the curator put it back
   into the original jar again.


Model treatment: nrm
~~~~~~~~~~~~~~~~~~~~

Each fish represents one material sample and one identifiable unit.
The two identifiable units belong to the same individual group and
thus share the determination. The two material samples belong to the
same preparation, which is the jar and its content.

The material sample corresponding to the fish sent out on loan constitutes
the transaction unit. This means that no new preparation need to be created 
in order to complete the loan. When the material comes back, the loan is
closed and the fish is put back into its original preparation, i.e. the jar.

Remarks
~~~~~~~
