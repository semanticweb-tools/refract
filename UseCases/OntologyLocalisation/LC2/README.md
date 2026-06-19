# Western to South Africa viewpoint – the concepts' Traditional Healer and Traditional Medicine
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Medical Subject Headings (MeSH)](https://bioportal.bioontology.org/ontologies/MESH)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq) | [CQ3](Files/CQ3.rq) | [CQ4](Files/CQ4.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeLocalisation](../../../ShapesGraphs/ShapeLocalisation/README.md)
  - Micro: [ShapeChangeAnnotationValue](../../../RefactoringActions/ChangeAnnotationValue/ShapeChangeAnnotationValue.ttl) | [ShapeAddClass](../../../RefactoringActions/AddClass/ShapeAddClass.ttl) | [ShapeAddSuperclassAssertion](../../../RefactoringActions/AddSuperclassAssertion/ShapeAddSuperclassAssertion.ttl) | [ShapeAddAnnotationLangString](../../../RefactoringActions/AddAnnotationLangString/ShapeAddAnnotationLangString.ttl)

## Description
The goal is to transform the MeSH representation of traditional medicine practitioners to reflect the South African legal and cultural context, where traditional healers are a distinct and legally recognised category of health personnel with specific subcategories.

## Competency Questions
**CQ1:** What is the `skos:prefLabel` of `mesh:D000095083`?
- Source: 'Traditional Medicine Practitioners'
- Target: 'Traditional Healer'

**CQ2:** What are the subclasses of `mesh:D000095083`?
- Source: Empty result set
- Target: `meshza:Sangoma`, `meshza:Herbalist`, `meshza:TraditionalBirthAttendant`, `meshza:TraditionalSurgeon`

**CQ3:** Does `meshza:MedicineSouthAfricanTraditional` exist as a class?
- Source: No
- Target: Yes

**CQ4:** What are the superclasses of `meshza:MedicineSouthAfricanTraditional`?
- Target: `mesh:D016488` and `mesh:D013812`

## Evaluation
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology localisation
- _Different viewpoint_ - the target ontology adopts a South African political community viewpoint, which (partially) reflects the legal context of traditional healers in South Africa.
- _Different URI_ - the target is published to a new URI, reflecting the new viewpoint.
- _Semantic change driven by a community-specific viewpoint_ - South African law recognises traditional healers as a distinct category of health personnel with specific subcategories (Sangoma, Herbalist, Traditional Birth Attendant, Traditional Surgeon) not present in the source ontology. The addition of Medicine, South African Traditional as a subclass of Medicine, Traditional African reflects the community-specific framing of traditional medicine practice.
