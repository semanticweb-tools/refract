# Semantic drift – expansion of 'intelligence' to include distributed human-AI cognition

## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Experimental Factor Ontology (EFO)](https://bioportal.bioontology.org/ontologies/EFO)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq) | [CQ4](Files/CQ4.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeEvolution](../../../ShapesGraphs/ShapeEvolution/README.md)
  - Micro: [ShapeAddClass](../../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddEquivalentClassSet](../../../RefactoringActions/AddEquivalentClassSet/ShapeAddEquivalentClassSet.ttl) | [ShapeAddAnnotationLangString](../../../RefactoringActions/AddAnnotationLangString/ShapeAddAnnotationLangString.ttl)

## Description

In EFO, 'intelligence' is a human cognitive ability. However, with the advent of AI, a human and AI can form a joint cognitive system, where the cognitive ability belongs to this human-AI partnership, where one can say that intelligence is distributed, instead of being solely attributed to the human.

The goal is to update EFO with a new class `efo:DistributedIntelligence` as a sibling of `'intelligence'`, to add a new class `efo:ArtificialIntelligence` as a sub-class of `'planned process'`, and then to update `efo:DistributedIntelligence` as a union of `'intelligence'` and `efo:ArtificialIntelligence`.

## Competency Questions

**CQ1:** Does `ex:ArtificialIntelligence` exist?
- Source: No
- Target: Yes

**CQ2:** What is the superclass of `ex:ArtificialIntelligence`?
- Target: `efo:EFO_0004542` (Planned process)

**CQ3:** Does `ex:DistributedIntelligence` exist as a class?
- Target: Yes

**CQ4:** What is the equivalent class expression for `ex:DistributedIntelligence`?
- Target: `owl:unionOf (efo:EFO_0004337 ex:ArtificialIntelligence)`

## Evaluation

- Shapes graph validation: [Using SHACL meta-validation](Evaluation/ShapesGraphValidation.md)
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---

## Rationale for classification as ontology evolution

- _Same viewpoint_ - EFO's biomedical perspective is unchanged.
- _Same URI_ - updated in place, versioned.
- _Semantic change driven by domain/belief system change_ - the scientific understanding of intelligence has expanded beyond its traditional biological scope, driven by the emergence of AI. This necessitates new classes to represent the broader conceptualisation of intelligence.
