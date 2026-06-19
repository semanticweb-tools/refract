# Annotation Action

**Definition type:** OWL Class \
**Fragment identifier:** `fract:AnnotationAction` \
**URI:** `https://w3id.org/refract#AnnotationAction`

An [atomic action](AtomicAction.md) that adds, modifies, or removes an annotation on an ontology element using an existing annotation property. Annotations are ignored by reasoners and do not affect the structure or semantic meaning of the ontology. To add or delete an annotation property, see [Structural Action](StructuralAction.md).

For the list of annotation actions, see [Local Action](LocalAction.md).

## Position in class hierarchy

`owl:Thing` → `rdfs:Class` → `prov:Activity` → `fract:RefactoringAction` → `fract:LocalAction` → `fract:AtomicAction` → `fract:AnnotationAction`

## See also

* [Atomic Action](AtomicAction.md)
* Atomic Action > [Structural Action](StructuralAction.md)
* Atomic Action > [Semantic Action](SemanticAction.md)
