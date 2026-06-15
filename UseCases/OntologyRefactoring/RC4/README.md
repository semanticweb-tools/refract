# Naming convention change – deprecation of a class
## Artefacts
- Dummy ontology: [Source](Files/source.ttl) | [Target](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeRefactoring](../../ShapesGraphs/ShapeRefactoring/README.md)
  - Micro: [ShapeDeprecateClassWithSuccessor](../../RefactoringActions/DeprecateClassWithSuccessor/ShapeDeprecateClassWithSuccessor.ttl) | [ShapeDeprecateClass](../../RefactoringActions/DeprecateClass/ShapeDeprecateClass.ttl) | [ShapeAddClass](../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddAnnotation](../../RefactoringActions/AddAnnotation/ShapeAddAnnotation.ttl)

## Description
This is a real-world scenario where the name of a department at the University of Cape Town was changed from 'School of Library Studies' to 'Department of Knowledge and Information Stewardship'. A dummy ontology has been created to represent this knowledge prior to and post-refactoring. This example is more extensive than RC1 because it is not just a change to the fragment identifier(s). The changes required include the introduction of a new class with a corresponding label and provenance metadata, as well as the deprecation of an old class.

## Competency Questions
**CQ1:** Is `uct:SchoolOfLibraryStudies` marked as deprecated?
- Target: Yes

**CQ2:** Does `uct:DepartmentOfKnowledgeAndInformationStewardship` exist as a class?
- Target: Yes

**CQ3:** What is the superclass of `uct:DepartmentOfKnowledgeAndInformationStewardship`?
- Target: `uct:HumanitiesFaculty`

## Evaluation
- Shapes graph validation: [Using SHACL meta-validation](Evaluation/ShapesGraphValidation.md)
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology refactoring
- _Same viewpoint_ - UCT's organisational structure perspective is unchanged
- _Same URI_ - updated in place, versioned
- _Structural change only_ - the department is renamed via a new class identifier and updated label, with the deprecated class preserved for backwards compatibility. The organisational concept itself has not changed - the same entity now has a new name.
