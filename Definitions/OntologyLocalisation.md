# Ontology Localisation

**Definition type:** OWL Class \
**Fragment identifier:** `fract:OntologyLocalisationProcess` \
**URI:** `https://w3id.org/refract#OntologyLocalisationProcess`

A specialised form of [Ontology Transformation](OntologyTransformation.md), where the target viewpoint V_T is specific to a community. The viewpoint always changes from V_S to V_T.

## Use cases

* [**LC1**](/UseCases/OntologyLocalisation/LC1) - English to French viewpoint – the concept lexicalised as 'river'
* [**LC2**](/UseCases/OntologyLocalisation/LC2) - Western to South Africa viewpoint – the concepts Traditional Healer, Traditional Medicine, and Alternative & Complementary Health Practitioners
* [**LC3**](/UseCases/OntologyLocalisation/LC3) - Western to New Zealand viewpoint – the concept of Whales as recognised legal persons

## Position in hierarchy

`owl:Thing` → `rdfs:Class` → `fract:TransformationProcess` → `fract:OntologyTransformationProcess` → `fract:OntologyLocalisationProcess`

## See also

* [Ontology Transformation](OntologyTransformation.md)
* [Ontology Refactoring](OntologyRefactoring.md)
* [Ontology Evolution](OntologyEvolution.md)
* [Viewpoint](Viewpoint.md)
