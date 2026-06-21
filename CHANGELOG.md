## [1.0.1] - 2026-06-21

### Ontology
- Renamed `dc:title` from "Refactoring Actions Shapes Library (REFrACT)" to "REFrACT: Refactoring Actions Vocabulary".
- Updated `dcterms:bibliographicCitation` to match the new title and the new DOI.
- Corrected the `bibo:doi` URI (was incorrectly using the `w3id.org` domain instead of `doi.org`) and switched both `bibo:doi` and `dcterms:bibliographicCitation` to reference Zenodo's concept DOI (`20742084`), which always resolves to the latest version, rather than the version-specific DOI for `v1.0.0`.
- Revised `rdfs:comment` for `fract:CompositeAction` to clarify that a composite action represents a batch of changes in a single action, rather than a single logical change.
- Added `rdfs:seeAlso` annotation to every refactoring action, referencing its corresponding page in the REFrACT GitHub repository.
- Added reified `owl:Axiom` annotations preserving the cross-reference between `fract:DeprecateClass` and `fract:DeprecateClassWithSuccessor`.
- Version bump: `owl:versionIRI` and `owl:versionInfo` updated to `1.0.1`, `owl:priorVersion` added pointing to `1.0.0`, `dcterms:modified` updated.

### Repository
- Added `CITATION.cff` and `CITATIONS.md`, providing separate citations for the GitHub repository and the REFrACT vocabulary respectively.
- Added `~Governance/ReleaseProcess.md`, documenting the release workflow.
- Updated `README.md`: renamed to "REFrACT: Refactoring Actions Artefact Repository", updated the version number and DOI badge, and renamed the DASH/SHACL section heading.
