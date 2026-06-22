# Local Action

**Definition type:** OWL Class \
**Fragment identifier:** `fract:LocalAction` \
**URI:** `https://w3id.org/refract#LocalAction`

A local action is a refactoring action that operates on individual ontology elements, such as a class, object property, label, etc, or a concept, represented by one or more ontology elements. This is in contrast to [global actions](GlobalAction.md), which act on the ontology as a whole.

Local actions can be classified as either [atomic](AtomicAction.md) or [composite](CompositeAction.md). If atomic, the action cannot be decomposed into smaller refactoring actions. If composite, the action is composed of two or more atomic refactoring actions. There are three types of atomic actions: [structural actions](StructuralAction.md), [semantic actions](SemanticAction.md), and [annotation actions](AnnotationAction.md).

Local actions include:

* Atomic
   * Annotation
      * [AddAnnotation](../RefactoringActions/AddAnnotation)
      * [AddAnnotationLangString](../RefactoringActions/AddAnnotationLangString)
      * [AddCommentForDeprecation](../RefactoringActions/AddCommentForDeprecation)
      * [ChangeAnnotation](../RefactoringActions/ChangeAnnotation)
      * [ChangeAnnotationLangString](../RefactoringActions/ChangeAnnotationLangString)
      * [ChangeAnnotationValue](../RefactoringActions/ChangeAnnotationValue)
      * [DeleteAnnotation](../RefactoringActions/DeleteAnnotation)
   * Semantic
      * [AddClass](../RefactoringActions/AddClass)
      * [AddEquivalentClassSet](../RefactoringActions/AddEquivalentClassSet)
      * [AddInstance](../RefactoringActions/AddInstance)
      * [AddInstancePropertyAssertion](../RefactoringActions/AddInstancePropertyAssertion)
      * [AddPropertyDomainRange](../RefactoringActions/AddPropertyDomainRange)
      * [AddPropertyRestriction](../RefactoringActions/AddPropertyRestriction)
      * [AddSemanticAxiom](../RefactoringActions/AddSemanticAxiom)
      * [AddSemanticAxiomUnary](../RefactoringActions/AddSemanticAxiomUnary)
      * [AddSubPropertyChainOf](../RefactoringActions/AddSubPropertyChainOf)
      * [AddSuperclassAssertion](../RefactoringActions/AddSuperclassAssertion)
      * [ChangeInstanceAssertion](../RefactoringActions/ChangeInstanceAssertion)
      * [ChangeSuperclassAssertion](../RefactoringActions/ChangeSuperclassAssertion)
      * [DeleteCardinalityRestriction](../RefactoringActions/DeleteCardinalityRestriction)
      * [DeleteClass](../RefactoringActions/DeleteClass)
      * [DeleteInstance](../RefactoringActions/DeleteInstance)
      * [DeleteInstancePropertyAssertion](../RefactoringActions/DeleteInstancePropertyAssertion)
      * [DeletePropertyDomainRange](../RefactoringActions/DeletePropertyDomainRange)
      * [DeletePropertyRestriction](../RefactoringActions/DeletePropertyRestriction)
      * [DeleteSemanticAxiom](../RefactoringActions/DeleteSemanticAxiom)
      * [DeleteSuperclassAssertion](../RefactoringActions/DeleteSuperclassAssertion)
      * [DeprecateClass](../RefactoringActions/DeprecateClass)
   * Structural
      * [AddAnnotationProperty](../RefactoringActions/AddAnnotationProperty)
      * [AddDataProperty](../RefactoringActions/AddDataProperty)
      * [AddObjectProperty](../RefactoringActions/AddObjectProperty)
      * [DeleteAnnotationProperty](../RefactoringActions/DeleteAnnotationProperty)
      * [DeleteDataProperty](../RefactoringActions/DeleteDataProperty)
      * [DeleteObjectProperty](../RefactoringActions/DeleteObjectProperty)
      * [RenameClass](../RefactoringActions/RenameClass)
      * [RenameProperty](../RefactoringActions/RenameProperty)
* Composite
   * [DeprecateClassWithSuccessor](../RefactoringActions/DeprecateClassWithSuccessor)

## Position in class hierarchy

`owl:Thing` → `rdfs:Class` → `prov:Activity` → `fract:RefactoringAction` → `fract:LocalAction`

## See also

* [Global Action](GlobalAction.md)
* Local Action > [Atomic Action](AtomicAction.md)
* Local Action > [Composite Action](CompositeAction.md)
