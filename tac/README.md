# Threat Actor Context Technical Committee Repository
The *OASIS Threat Actor Context Technical Committee* (TAC-TC) is chartered to create an ontology for expressing the rich context around Threat Actors. The OASIS TAC-TC is a separate Technical Committee from the OASIS CTI-TC, it will *embrace and extend* the CTI-TC's release of the STIX 2.1 standard.

This repositiory is for TAC-TC members to collaborate on the development of the ontologies necessary for supporting Threat Analysts to assert facts into a graph knowledgebase and formally reason over those facts.


### TAC Semantic Graph Importing STIX Semantic Extension Graph (tac.owl)
This third layer of representation will add the concepts of the TAC-TC members.

1. tac.owl
	1. stix-semex.owl   
	1. stix-semex-context.owl

# Editing Style and Syntax Normalization
Developers have their own preferences when in comes to ontology editors and writing styles. This causes dificulties in managing a common repository used by multiple ontology contributors. To resolve the problem, all ontology content submitted and persisted in the TAC ontology repository must be ***Normalized*** with a utility called the **RDF Toolkit**. This utility puts the submitted content into a standardized form. It removes any stylistic differences between contributors.

 

