# Atomic Action

**Definition type:** OWL Class \
**Fragment identifier:** `fract:AtomicAction` \
**URI:** `https://w3id.org/refract#AtomicAction`

A micro-level local refactoring action that cannot be decomposed into smaller refactoring actions. An atomic action may operate on a single ontology element, a set of ontology elements, or a concept represented by one or more ontology elements.

There are three types of atomic actions: [structural actions](StructuralAction.md), [semantic actions](SemanticAction.md), and [annotation actions](AnnotationAction.md).

For the list of atomic actions, see [Local Action](LocalAction.md).

## Position in class hierarchy

`owl:Thing` → `rdfs:Class` → `prov:Activity` → `fract:RefactoringAction` → `fract:LocalAction` → `fract:AtomicAction`

## See also

* Local Action > [Composite Action](CompositeAction.md)
* Atomic Action > [Structural Action](StructuralAction.md)
* Atomic Action > [Semantic Action](SemanticAction.md)
* Atomic Action > [Annotation Action](AnnotationAction.md)
