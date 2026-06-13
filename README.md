# REFrACT — Refactoring Actions Shapes Library

**URI:** `https://semanticweb.tools/ont/refract` \
**Persistent URI:** `https://w3id.org/refract` \
**Version:** 1.0.0 \
**Licence:** [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)

REFrACT is a vocabulary for describing and validating a Transformation Manifest File (TMF). A TMF records the metadata and refactoring actions associated with an ontology transformation process, including refactoring, evolution, transformation, and localisation. REFrACT has been aligned to the DASH Data Shapes Vocabulary, which in turn imports the Shapes Constraint Language (SHACL).

## Repository Contents

- [Ontologies](Ontologies/README.md) — ontology files including local copies of DASH and SHACL
- [Refactoring Actions](RefactoringActions/README.md) — example TMFs and shapes graphs per action
- [Use Cases](UseCases/README.md) — worked examples across four ontology change processes
- [Definitions](Definitions/README.md) — definitions of key terms used in this repository

## DASH and SHACL

REFrACT imports DASH and SHACL via locally hosted copies at `https://semanticweb.tools/ont/dash` and `https://semanticweb.tools/ont/shacl` respectively. The published W3C SHACL ontology contains a known inconsistency which causes the ontology to be reported as inconsistent. The published DASH ontology imports the W3C SHACL ontology, propagating this inconsistency. To address this, the `owl:imports` assertion for SHACL has been removed from the local copy of DASH, and a corrected local copy of SHACL is imported directly by REFrACT instead. Both files are available in the [Ontologies](Ontologies/README.md) folder.

## Contact

For questions or to report discrepancies, please contact Frances Gillis-Webber at fgilliswebber@cs.uct.ac.za.
