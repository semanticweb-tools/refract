# Regional change – change in measurement from metric to imperial
## Artefacts
- Dummy ontology: [Source](Files/source.ttl) | [Target](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq) | [CQ4](Files/CQ4.rq) | [CQ5](Files/CQ5.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeTransformation](../../../ShapesGraphs/ShapeTransformation/README.md)
  - Micro: [ShapeAddClass](../../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddAnnotation](../../../RefactoringActions/AddAnnotation/ShapeAddAnnotation.ttl) | [ShapeDeleteClass](../../../RefactoringActions/DeleteClass/ShapeDeleteClass.ttl)

## Description
The goal is to transform a metric measurement ontology to an imperial measurement ontology, replacing metric units with their imperial equivalents and capturing the conversion factors between the two systems.

## Competency Questions
**CQ1:** Does `recipeim:ImperialUnit` exist?
- Source: No
- Target: Yes

**CQ2:** What is the superclass of `recipeim:Ounce`?
- Target: `recipeim:ImperialUnit`

**CQ3:** Does `recipe:Gram` exist?
- Source: Yes
- Target: No

**CQ4:** What is the `qudt:conversionMultiplier` for `recipeim:Ounce`?
- Target: `28.3495`

**CQ5:** What are the `qudt:conversionMultiplier` and `qudt:conversionOffset` for `recipeim:Fahrenheit`?
- Target: `1.8` and `32`

## Evaluation
- Shapes graph validation: [Using SHACL meta-validation](Evaluation/ShapesGraphValidation.md)
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology transformation
- _Different viewpoint_ - the target ontology adopts a North American imperial measurement viewpoint, replacing the metric viewpoint of the source ontology.
- _Different URI_ - the target is published to a new URI, reflecting the new viewpoint.
- _Semantic change driven by viewpoint change_ - the measurement units are not just renamed but replaced with conceptually different units that reflect a different system of measurement. The conversion factors capture the relationship between the two viewpoints.
