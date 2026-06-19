# English to French viewpoint – the concept lexicalised as 'river'
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Semantic Web for Earth and Environment Technology Ontology (SWEET)](https://bioportal.bioontology.org/ontologies/SWEET)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq) | [CQ4](Files/CQ4.rq) | [CQ5](Files/CQ5.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeLocalisation](../../../ShapesGraphs/ShapeLocalisation/README.md)
  - Micro: [ShapeDeleteClass](../../../RefactoringActions/DeleteClass/ShapeDeleteClass.ttl) | [ShapeAddClass](../../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddSemanticAxiom](../../../RefactoringActions/AddSemanticAxiom/ShapeAddSemanticAxiom.ttl) | [ShapeAddAnnotationLangString](../../../RefactoringActions/AddAnnotationLangString/ShapeAddAnnotationLangString.ttl)

## Description
The English concept of 'river' maps to two distinct concepts in French: `sweetfr:Riviere` (a river that flows into another river) and `sweetfr:Fleuve` (a river that flows into the sea). The transformation replaces the single English class `sweet:River` with two sibling French classes, capturing the conceptual distinction inherent to the French language viewpoint.

## Competency Questions
**CQ1:** Does `sweetfr:Riviere` exist as a class?
- Source: No
- Target: Yes

**CQ2:** Does `sweetfr:Fleuve` exist as a class?
- Source: No
- Target: Yes

**CQ3:** Does `sweet:River` exist as a class?
- Source: Yes
- Target: No

**CQ4:** Is there an `owl:disjointWith` assertion between `sweetfr:Riviere` and `sweetfr:Fleuve`?
- Target: Yes

**CQ5:** What is the superclass of `sweetfr:Riviere`?
- Target: Yes

## Evaluation
- Shapes graph validation: [Using SHACL meta-validation](Evaluation/ShapesGraphValidation.md)
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology localisation
- _Different viewpoint_ - the target ontology adopts a French language viewpoint, replacing the English viewpoint of the source ontology.
- _Different URI_ - the target is published to a new URI, reflecting the new viewpoint.
- _Semantic change driven by a community-specific viewpoint_ - the French conceptualisation of rivers differs to that of the English language conceptualisation.
