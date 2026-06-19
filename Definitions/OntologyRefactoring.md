# Ontology Refactoring

**Definition type:** OWL Class \
**Fragment identifier:** `fract:OntologyRefactoringProcess` \
**URI:** `https://w3id.org/refract#OntologyRefactoringProcess`

The transformation of a source ontology O_S with viewpoint V_S, where changes are structural only and the process is meaning-preserving. The ontology may be published to the same (versioned) URI as O_S, or to a new URI as O_Si, in order to maintain downstream compatibility with existing resources. The viewpoint is expected to remain unchanged from that of V_S.

## Use cases

* [**RC1**](/UseCases/OntologyRefactoring/RC1) - Normalisation of naming conventions – renaming of class name(s)
* [**RC2**](/UseCases/OntologyRefactoring/RC2) - Decidability repair – change of OWL profile from OWL Full to OWL DL
* [**RC3**](/UseCases/OntologyRefactoring/RC3) - Lexical enrichment – making an ontology multilingual
* [**RC4**](/UseCases/OntologyRefactoring/RC4) - Hierarchical restructuring – regrouping of university Course classes into a different hierarchy

## Position in hierarchy

`owl:Thing` → `rdfs:Class` → `fract:TransformationProcess` → `fract:OntologyRefactoringProcess`

## See also

* [Ontology Evolution](OntologyEvolution.md)
* [Ontology Transformation](OntologyTransformation.md)
* [Ontology Localisation](OntologyLocalisation.md)
