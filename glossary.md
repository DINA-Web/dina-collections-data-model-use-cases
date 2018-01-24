# Definition of Terms used in Use Cases

Brief definitions of terms in the use case documents. Contains links to related [DarwinCore terms](http://tdwg.github.io/dwc/terms/) (although we are not making committment to using DwC terms or any assertions about using DwC terms in exactly the same way).

## Autonym
A subspecies or variety name that is the duplicate of the specific epithet. Autonyms are formed when a new subspecies or variety is described by an author. Autonyms carry the name of the author of the species and are based on the original type specimen; they do not require a new description. Source: Northern Ontario Flora

## Basionym
“Basionym provides the final epithet, name, or stem of the new combination or name at new rank” (ICN Art. 6.10 & Art. 41). It is the orginal combination of a name as viewed from a new combination. The basionym is therefore always relative to a new combination. Source: CoL+

## Classification
Hierarchy of [Taxon](#taxon) where each of them has a rank.

## Collection manager
The person responsible for the collection.

## Collection assistant
An assistant to the [Collection manager](#collection-manager).

## Collector
The person who collected the physical [specimen](#specimen), i.e. removed it from the natural habitat. See DwC [recordedBy](http://tdwg.github.io/dwc/terms/#recordedBy).

## Curator
A person with scientific expertise who works with the [specimens](#specimen) in the collection.

## Data capture person
A person who enters data about the collection into the information management system. May not have scientific expertise about the collection.

## Determination
Making a taxonomic determination (e.g., assignment of a specimen to a taxon). Synonym of [identification](#identification). See DarwinCore  [Identification](http://rs.tdwg.org/dwc/terms/#Identification).

## Determiner
A person making the assignment of a specimen to a taxon.

## Homotypic synonym
(nomenclatural synonym). A name based on the same type as that of another name (Art. 14.4); termed an “objective synonym” in the International Code of Zoological Nomenclature and the International Code of Nomenclature of Bacteria (Bacteriological Code) (Art. 14.4 footnote). Source:  International Association for Plant Taxonomy

## Heterotypic synonym
(taxonomic synonym). A name based on a type different from that of another name referring to the same taxon (Art. 14.4); termed a “subjective synonym” in the International Code of Zoological Nomenclature and the International Code of Nomenclature of Bacteria (Bacteriological Code) (Art. 14.4 footnote). Source:  International Association for Plant Taxonomy

## Identification
Synonym of [determination](#determination).

## Individual
One single organism (one genome in one body). Two specimens from the same species might be from the same individual, or from different individuals.

## Observation
A single piece of data about a specimen made at a particular time, e.g. a taxonomic identification, weight, size.

## Preparation
The type of specimen, or the process used to preserve the specimen, e.g. fossil, cast, skeleton, whole animal, etc. See DwC [preparations](http://tdwg.github.io/dwc/terms/#preparations). Can this also be used with samples?

## Pro parte
Indicates that the name (as a synonym) has been used in a broad concept to include the correct, currently accepted name under which it is listed, as well as at least one other correct, currently accepted name. In other words, it means that some, but not all, individuals identified as this species are synonymous with the accepted species.

## Sample
Part of a specimen, removed / extracted for downstream analysis (e.g. DNA sequencing). Does not correspond exactly to any Darwin Core term (would also be considered [MaterialSample](http://rs.tdwg.org/dwc/terms/#MaterialSample)?)

## Specimen
A physical item in a natural history collection. Primary unit in a collections management system. May include one or more taxa.

See DwC [MaterialSample](http://rs.tdwg.org/dwc/terms/#MaterialSample).

## Synonym
General term to represent an alternative [Taxon Name](#taxon_name) that applies to the same [Taxon](#taxon) as another (different) [Taxon Name](#taxon_name). A synonym can be caused by a taxonomic change (which may be subjective to a taxonomic viewpoint) or a change made to comply with the rules of nomenclature. See also [Homotypic synonym](#homotypic-synonym) and [Heterotypic synonym](#heterotypic-synonym).

## Taxon
A group of organisms (sensu http://purl.obolibrary.org/obo/OBI_0100026) considered by taxonomists to form a homogeneous unit.
Taxa are placed at specific ranks in taxonomic hierarchie ([Classification](#classification)) and their description is expressed as [Taxon Concept](#taxon_concept).

See DwC [Taxon](http://rs.tdwg.org/dwc/terms/index.htm#Taxon)

## Taxon Concept
"Taxonomic concepts (sensu Berendsohn) embody the underlying meanings of scientific names as stated in a particular publication ..."
Source: N.M. Franz and R.K. Peet. (2009) Perspectives: Towards a language for mapping relationships among taxonomic concepts https://doi.org/10.1017/S147720000800282X

"Classification and the rules of nomenclature frequently cause species names to be changed or redefined. To be clear what we mean by a taxon name, we should refer to the name and the reference to the publication in which the species is described."
Source: TDWG, TCS Executive Summary (2005). Retrieved from http://www.tdwg.org/fileadmin/subgroups/tnc/Exec_summary_TCS.pdf

See TDWG [Taxon Concept Schema](http://www.tdwg.org/fileadmin/subgroups/tnc/Exec_summary_TCS_Appendix.pdf) appendix

## Taxon Name
Names given to a [Taxon](#taxon) that could be independent of its classification (e.g. if rank is above the rank of genus).
Taxon Names are labels in accordance with the rules of Biological Codes of Nomenclature.

See DwC [scientificName](http://rs.tdwg.org/dwc/terms/index.htm#scientificName)
