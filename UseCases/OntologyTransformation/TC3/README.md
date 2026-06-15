# Decidability repair – partial change of OWL profile from OWL2 DL to OWL2 RL
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Model for Language Annotation (MoLA)](https://semanticweb.tools/ont/mola)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeTransformation](../../ShapesGraphs/ShapeTransformation/README.md)
  - Micro: [ShapeDeleteCardinalityRestriction](../../RefactoringActions/DeleteCardinalityRestriction/ShapeDeleteCardinalityRestriction.ttl) | [ShapeDeletePropertyDomainRange](../../RefactoringActions/DeletePropertyDomainRange/ShapeDeletePropertyDomainRange.ttl) | [ShapeAddPropertyDomainRange](../../RefactoringActions/AddPropertyDomainRange/ShapeAddPropertyDomainRange.ttl)

## Description
The goal is to transform a fragment of MoLA from OWL2 DL to OWL2 RL by removing a cardinality restriction on `mola:Region` and replacing the union domain expression of `mola:hasMember` with two separate domain assertions.

## Competency Questions
**CQ1:** Does `mola:Region` have a `owl:minQualifiedCardinality` restriction?
- Source: Yes
- Target: No

**CQ2:** What are the `rdfs:domain` values for `mola:hasMember`?
- Source: A blank node identifier would be returned
- Target: `mola:DialectCluster` and `mola:LanguageFamily`

**CQ3:** Does `mola:hasMember` have an `owl:unionOf` domain expression?
- Source: True
- Target: False

## Evaluation
- Shapes graph validation: [Using SHACL meta-validation](Evaluation/ShapesGraphValidation.md)
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology transformation
- _Different viewpoint_ - the target ontology adopts an OWL2 RL technical context viewpoint, replacing the OWL DL viewpoint of the source ontology.
- _Different URI_ - the target is published to a new URI, reflecting the new technical context.
- _Semantic change driven by viewpoint change_ - removing the cardinality restriction on `mola:Region` and replacing the union domain of `mola:hasMember` with two separate domain assertions weakens the ontological commitments of the source ontology to comply with the OWL2 RL profile.
