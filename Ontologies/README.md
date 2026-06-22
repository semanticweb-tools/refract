# Ontologies

This folder contains the REFrACT vocabulary and locally hosted copies of DASH and SHACL.

## REFrACT

**Persistent URI:** `https://w3id.org/refract` \
**Redirects to:** `https://semanticweb.tools/ont/refract`

**Recommended prefix:** `fract: <https://w3id.org/refract#>`

**Version:** [See CHANGELOG](../CHANGELOG.md) \
**Licence:** [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20742084.svg)](https://doi.org/10.5281/zenodo.20742084)

- [refract.ttl](refract.ttl)

> The canonical version of the vocabulary is hosted at `https://semanticweb.tools/ont/refract`. \
This file is provided here for version control purposes.

## DASH and SHACL

- [dash.ttl](dash.ttl)
- [shacl.ttl](shacl.ttl)

> REFrACT imports DASH and SHACL via locally hosted copies at `https://semanticweb.tools/ont/dash` and `https://semanticweb.tools/ont/shacl` respectively. The published W3C SHACL ontology contains a [known bug](https://github.com/w3c/data-shapes/issues/208) in which `sh:namespace` is declared as a plain string literal rather than `xsd:anyURI`, violating SHACL's own range constraint on that property and causing the ontology to be reported as inconsistent by some reasoners. The fix was committed to the W3C data-shapes repository in [PR #244](https://github.com/w3c/data-shapes/pull/244) (February 2025), but has not yet been published to the canonical W3C URI. The locally hosted copy of SHACL uses this corrected version. Additionally, the `owl:imports` assertion for SHACL has been removed from the local copy of DASH to prevent the published W3C version from being fetched.
