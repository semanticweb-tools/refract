# Decidability repair – partial change of OWL profile from OWL2 DL to OWL2 RL
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Model for Language Annotation (MoLA)](https://semanticweb.tools/ont/mola)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeRefactoring](../../../ShapesGraphs/ShapeRefactoring/README.md)
  - Micro: [ShapeDeleteSuperclassAssertion](../../../RefactoringActions/DeleteSuperclassAssertion/ShapeDeleteSuperclassAssertion.ttl)

## Description
For 6 of the 7 classes which are a sub-class of `owl:Thing`, the assertion was made explicit, which is a violation for OWL2 RL. To address this, the explicit assertions need to be removed.

_Example fragment:_ \
For `https://semanticweb.tools/ont/mola#LanguageCode`, remove the axiom `<rdfs:subClassOf rdf:resource="http://www.w3.org/2002/07/owl#Thing"/>`.

## Competency Questions
**CQ1:** Does `mola:LanguageCode` exist as a class (in the ontology)?
- Source: Yes
- Target: Yes

**CQ2:** Is there an explicit `SubClassOf(mola:LanguageCode owl:Thing)` assertion?
- Source: Yes
- Target: No

## Evaluation
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology refactoring
- _Same viewpoint_ - MoLA's language annotation perspective is unchanged
- _Same URI_ - updated in place, versioned.
- _Structural change only_ - the explicit `rdfs:subClassOf owl:Thing` assertions are removed, with no change to the meaning of the classes or their position in the hierarchy. The implicit subclass relationship to `owl:Thing` is preserved.
