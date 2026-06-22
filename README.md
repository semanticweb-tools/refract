# REFrACT: Refactoring Actions Artefact Repository
Supporting artefacts for REFrACT (Refactoring Actions Vocabulary), including SHACL shapes, example transformation manifest files, and use cases.

## Ontology Metadata
**Persistent URI:** `https://w3id.org/refract` \
**Redirects to:** `https://semanticweb.tools/ont/refract`

**Recommended prefix:** `fract: <https://w3id.org/refract#>`

**Version:** 1.0.2 \
**Licence:** [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20742084.svg)](https://doi.org/10.5281/zenodo.20742084)

REFrACT is a lightweight OWL ontology for describing and validating a Transformation Manifest File (TMF). A TMF records the metadata and refactoring actions associated with an ontology transformation process, including refactoring, evolution, transformation, and localisation. REFrACT has been aligned to the [DASH Data Shapes Vocabulary](https://datashapes.org/dash), which in turn imports the Shapes Constraint Language (SHACL).

## Repository Contents

- [Ontologies](Ontologies/README.md) — ontology files including local copies of DASH and SHACL
- [Refactoring Actions](RefactoringActions) — example TMFs and shapes graphs per action
- [Shapes Graphs](ShapesGraphs/README.md) — SHACL shapes graphs for validating Transformation Manifest Files
- [Use Cases](UseCases/README.md) — worked examples across four ontology change processes
- [Definitions](Definitions) — definitions of key terms used in this repository

## A Note About DASH and SHACL

REFrACT imports DASH and SHACL via locally hosted copies at `https://semanticweb.tools/ont/dash` and `https://semanticweb.tools/ont/shacl` respectively. The published W3C SHACL ontology contains a [known bug](https://github.com/w3c/data-shapes/issues/208) in which `sh:namespace` is declared as a plain string literal rather than `xsd:anyURI`, violating SHACL's own range constraint on that property and causing the ontology to be reported as inconsistent by some reasoners. The fix was committed to the W3C data-shapes repository in [PR #244](https://github.com/w3c/data-shapes/pull/244) (February 2025), but has not yet been published to the canonical W3C URI. The locally hosted copy of SHACL uses this corrected version. Additionally, the `owl:imports` assertion for SHACL has been removed from the local copy of DASH to prevent the published W3C version from being fetched. Both corrected files are available in the [Ontologies](Ontologies/README.md) folder.

## Contact

For questions or to report discrepancies, please contact Frances Gillis-Webber at fgilliswebber@cs.uct.ac.za.
