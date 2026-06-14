# Add comment for deprecation
**URI:** `https://semanticweb.tools/ont/refract#AddCommentForDeprecation`

**Type:** [Annotation action](../../Definitions/AnnotationAction.md) · [Atomic action](../../Definitions/AtomicAction.md) \
**Scope:** [Local action](../../Definitions/LocalAction.md)

An annotation action that adds a deprecation comment and optionally a 'see also' reference to the deprecated class as part of a 'Deprecate class with successor class' composite action. If 'target annotation value' is omitted, the algorithm generates the comment from a template. This action is not intended to be used standalone.

For full documentation including parameters, see the [REFrACT vocabulary](https://semanticweb.tools/ont/refract#AddCommentForDeprecation).

## Shapes graph
- [ShapeAddCommentForDeprecation.ttl](ShapeAddCommentForDeprecation.ttl) (local instance)
- URI: `https://semanticweb.tools/rdf/shapes/ShapeAddCommentForDeprecation.ttl`

## Examples
- [Example TMF](TMFAddCommentForDeprecation.ttl)

## Used in use cases
- Ontology Refactoring: [RC4](../../UseCases/OntologyRefactoring/RC4/README.md)

---
<sub>The example TMF and shapes graph were generated with the assistance of Claude Sonnet 4.6 by Anthropic. If you identify any discrepancies, please see the [project README](../../README.md).</sub>
