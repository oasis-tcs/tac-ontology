# Threat Actor Context Technical Committee Repository
The *OASIS Threat Actor Context Technical Committee* (TAC-TC) is chartered to create an ontology for expressing the rich context around Threat Actors. The OASIS TAC-TC is a separate Technical Committee from the OASIS CTI-TC, it will *embrace and extend* the CTI-TC's release of the STIX 2.1 standard.

This repositiory is for TAC-TC members to collaborate on the development of the ontologies necessary for supporting Threat Analysts to assert facts into a graph knowledgebase and formally reason over those facts.

## Embrace & Extend
In order to extend the STIX 2.1 standard in a *semantically interoperable* way, the TAC-TC will develop and use a formal ontological representation of the specification. This representation will expose multiple levels of semantics.

The adoption of multiple models, including the STIX 2.1 specification, will be a benefit of adopting the TAC Ontology.

## Property Graphs and Semantic Graphs
The TAC-TC is providing a solution built upon the semantic technologies, in specific, a **Semantic Graph** based solution. Rather than attempt to provide a background on Property Graphs and Semantic Graphs in this readme.md file, the reader can investigate many discussions such as [this article on LinkedIn.](https://www.linkedin.com/pulse/semantic-knowledge-graphs-versus-property-andreas-blumauer/)

The STIX 2.1 specification content more closely aligns with a Property Graph representation rather than a Semantic Graph representation. This is due to the use of **Relationship** nodes between STIX Objects. This is a perfectly legitimate structure choice, but does not afford us with the full set of semantic tools we would like. Therefore, a series of representations to represent the STIX 2.1 standard as a full Semantic Graph have been taken.


### STIX Semantic Extension Graph (stix-semex.owl)
This representation will extend the stix.owl representation with the ObjectProperty and DataProperty predicates encapsulated in the *Relationship* objects in the STIX 2.1 specification.
 
1. stix-semex.owl   
	1. stix-spec.owl
	1. marking.owl
1. stix-semex-context.owl

# Editing Style and Syntax Normalization
Developers have their own preferences when in comes to ontology editors and writing styles. This causes dificulties in managing a common repository used by multiple ontology contributors. To resolve the problem, all ontology content submitted and persisted in the TAC ontology repository must be ***Normalized*** with a utility called the **RDF Toolkit**. This utility puts the submitted content into a standardized form. It removes any stylistic differences between contributors.

 

