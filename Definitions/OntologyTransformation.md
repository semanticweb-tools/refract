# Ontology Transformation

**Definition type:** OWL Class \
**Fragment identifier:** `fract:OntologyTransformationProcess` \
**URI:** `https://w3id.org/refract#OntologyTransformationProcess`

The adaptation of a source ontology O_S with viewpoint V_S to a target viewpoint V_T, where V_T differs from V_S. Changes are made in the semantic layer of the ontology, with possible changes in the structural layer as well. The output O_T is published to a different URI to that of the source.

## Use cases

* [**TC1**](/UseCases/OntologyTransformation/TC1) - Regional change – change in measurement from metric to imperial
* [**TC2**](/UseCases/OntologyTransformation/TC2) - Provenance reframing – change of cultural heritage ontology from acquisition to contested heritage
* [**TC3**](/UseCases/OntologyTransformation/TC3) - Complexity downgrading – change of OWL profile from OWL DL to OWL EL

## Position in class hierarchy

`owl:Thing` → `rdfs:Class` → `fract:TransformationProcess` → `fract:OntologyTransformationProcess`

## See also

* [Ontology Refactoring](OntologyRefactoring.md)
* [Ontology Evolution](OntologyEvolution.md)
* [Ontology Localisation](OntologyLocalisation.md)
* [Viewpoint](Viewpoint.md)
  
