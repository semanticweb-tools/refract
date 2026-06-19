# New knowledge – adding mRNA vaccine as a sub-class of Vaccine
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Vaccine Ontology (VO)](https://bioportal.bioontology.org/ontologies/VO)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq) | [CQ4](Files/CQ4.rq) | [CQ5](Files/CQ5.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeEvolution](../../../ShapesGraphs/ShapeEvolution/README.md)
  - Micro: [ShapeAddClass](../../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddSuperclassAssertion](../../../RefactoringActions/AddSuperclassAssertion/ShapeAddSuperclassAssertion.ttl) | [ShapeAddPropertyRestriction](../../../RefactoringActions/AddPropertyRestriction/ShapeAddPropertyRestriction.ttl) | [ShapeAddAnnotationLangString](../../../RefactoringActions/AddAnnotationLangString/ShapeAddAnnotationLangString.ttl) | [ShapeAddInstance](../../../RefactoringActions/AddInstance/ShapeAddInstance.ttl)

## Description
The emergence of mRNA vaccine technology as a recognised and distinct vaccine platform necessitates the addition of `ex:mRNAVaccine` as a new subclass of `vo:VO_0000001` (vaccine), along with the Pfizer-BioNTech COVID-19 vaccine as a named individual.

## Competency Questions
**CQ1:** Does `ex:mRNAVaccine` exist?
- Source: No
- Target: Yes

**CQ2:** What is the superclass of `ex:mRNAVaccine`?
- Target: `vo:VO_0000001` (vaccine)

**CQ3:** Is `vo:VO_0005198` (COVID-19 RNA vaccine) a subclass of `ex:mRNAVaccine`?
- Source: No
- Target: Yes

**CQ4:** Does `ex:mRNAVaccine` have `hasRole 'RNA vaccine role'`?
- Target: Yes

**CQ5:** Is `ex:PfizerBioNTech` an instance of `ex:mRNAVaccine`?
- Target: Yes

## Evaluation
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology evolution
- _Same viewpoint_ - VO's biomedical perspective is unchanged.
- _Same URI_ - updated in place, versioned.
- _Semantic change driven by domain change_ - the emergence of mRNA vaccine technology as a recognised and distinct vaccine platform, and the approval of the Pfizer-BioNTech COVID-19 vaccine as a named individual, represent new domain knowledge that requires the ontology to be updated to reflect this.
