# Legal changes – removal of UK from European Union
## Artefacts
- Source ontology: [fragment](Files/source.ttl) from [Medical Subject Headings (MeSH)](https://bioportal.bioontology.org/ontologies/MESH)
- Target ontology: [revised fragment](Files/target.ttl)
- SPARQL for CQs: [CQ1](Files/CQ1.rq) | [CQ2](Files/CQ2.rq)
- TMF for target viewpoint: [JSON-LD](Files/TMF.json) | [Turtle](Files/TMF.ttl)
- Shapes graphs:
  - Macro: [ShapeEvolution](../../../ShapesGraphs/ShapeEvolution/README.md)
  - Micro: [ShapeChangeAnnotationValue](../../../RefactoringActions/ChangeAnnotationValue/ShapeChangeAnnotationValue.ttl) | [ShapeAddAnnotationLangString](../../../RefactoringActions/AddAnnotationLangString/ShapeAddAnnotationLangString.ttl) | [ShapeAddAnnotation](../../../RefactoringActions/AddAnnotation/ShapeAddAnnotation.ttl)

## Description
The goal is to remove the United Kingdom from the list of countries given in `skos:definition` for `mesh:D005062`, to record the date this class was modified, and to add another annotation - `skos:historyNote` - to describe the change.

## Competency Questions
**CQ1:** What is the `skos:definition` of `mesh:D005062`?
- Source: The definition with the UK
- Target: The updated definition without the UK

**CQ2:** Does `mesh:D005062` have a `skos:historyNote`?
- Target: Yes

## Evaluation
- TMF validation: [Using SHACL](Evaluation/TMFValidation.md)

---
## Rationale for classification as ontology evolution
- _Same viewpoint_ - MeSH's biomedical/bibliographic perspective is unchanged.
- _Same URI_ - updated in place, versioned.
- _Semantic change driven by domain change_ - Brexit altered the real-world composition of the EU, requiring the ontology to be updated to reflect this.
