# Ontology Evolution

**Definition type:** OWL Class \
**Fragment identifier:** `fract:OntologyEvolutionProcess` \
**URI:** `https://w3id.org/refract#OntologyEvolutionProcess`

The changes made to a source ontology O_S in response to a change in the domain or belief system. O_S is an input to the evolution process, and the output is the revised ontology O_Si. O_Si is expected to be published to the same (versioned) URI, but as with ontology refactoring, it may also be published to a new URI in order to maintain downstream compatibility with existing resources. The viewpoint is expected to remain unchanged from that of V_S.

## Use cases

* [**EC1**](/UseCases/OntologyEvolution/EC1) - Semantic drift – the term 'cloud' shifting from a meteorological event to a computing infrastructure concept
* [**EC2**](/UseCases/OntologyEvolution/EC2) - Legal changes – removal of UK from European Union
* [**EC3**](/UseCases/OntologyEvolution/EC3) - New knowledge – adding mRNA vaccine as a sub-class of Vaccine

## Position in class hierarchy

`owl:Thing` → `rdfs:Class` → `fract:TransformationProcess` → `fract:OntologyEvolutionProcess`

## See also

* [Ontology Refactoring](OntologyRefactoring.md)
* [Ontology Transformation](OntologyTransformation.md)
* [Ontology Localisation](OntologyLocalisation.md)
* [Viewpoint](Viewpoint.md)
