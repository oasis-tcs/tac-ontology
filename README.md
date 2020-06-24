# README

Members of the [OASIS Threat Actor Context (TAC) TC](https://www.oasis-open.org/committees/tac/) create and manage technical content in this TC GitHub repository (https://github.com/oasis-tcs/tac-ontology/) as part of the TC's chartered work (the program of work and deliverables described in its [charter](https://www.oasis-open.org/committees/tac/charter.php).

OASIS TC GitHub repositories, as described in [GitHub Repositories for OASIS TC Members' Chartered Work](https://www.oasis-open.org/resources/tcadmin/github-repositories-for-oasis-tc-members-chartered-work), are governed by the OASIS [TC Process](https://www.oasis-open.org/policies-guidelines/tc-process), [IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr), and other policies. While they make use of public GitHub repositories, these repositories are distinct from [OASIS Open Repositories](https://www.oasis-open.org/resources/open-repositories), which are used for development of open source [licensed](https://www.oasis-open.org/resources/open-repositories/licenses) content.

## Description

The purpose of this repository is to manage Ontology Web Language (OWL) representations of the Threat Actor Context Technical Committee's (TAC-TC) work.
Additionally, TAC TC work products related to the ontologies will be in this
repository, such as documentation, user guides, and utilities.

## Contributions

As stated in this repository's [CONTRIBUTING](https://github.com/oasis-tcs/tac-ontology/blob/master/CONTRIBUTING.md) file, contributors to this repository must be Members of the OASIS TAC TC for any substantive contributions or change requests. Anyone wishing to contribute to this GitHub project and [participate](https://www.oasis-open.org/join/participation-instructions) in the TC's technical activity is invited to join as an OASIS TC Member. Public feedback is also accepted, subject to the terms of the [OASIS Feedback License](https://www.oasis-open.org/policies-guidelines/ipr#appendixa). 

## Licensing

Please see the [LICENSE](https://github.com/oasis-tcs/tac-ontology/blob/master/LICENSE.md) file for description of the license terms and OASIS policies applicable to the TC's work in this GitHub project. Content in this repository is intended to be part of the TAC TC's permanent record of activity, visible and freely available for all to use, subject to applicable OASIS policies, as presented in the repository [LICENSE](https://github.com/oasis-tcs/tac-ontology/blob/master/LICENSE.md). 

# Threat Actor Context Technical Committee Repository
The *OASIS Threat Actor Context Technical Committee* (TAC-TC) is chartered to create an ontology for expressing the rich context around Threat Actors. The OASIS TAC-TC is a separate Technical Committee from the OASIS CTI-TC, it will *embrace and extend* the CTI-TC's release of the STIX 2.1 standard.

This repositiory is for TAC-TC members to collaborate on the development of the ontologies necessary for supporting Threat Analysts to assert facts into a graph knowledgebase and formally reason over those facts.

## Embrace & Extend
In order to extend the STIX 2.1 standard in a *semantically interoperable* way, the TAC-TC will develop and use a formal ontological representation of the specification. This representation will expose multiple levels of semantics.

The adoption of multiple models, including the STIX 2.1 specification, will be a benefit of adopting the TAC Ontology.

## Property Graphs and Semantic Graphs
The TAC-TC is providing a solution built upon the semantic technologies, in specific, a **Semantic Graph** based solution. Rather than attempt to provide a background on Property Graphs and Semantic Graphs in this readme.md file, the reader can investigate many discussions such as [this article on LinkedIn.](https://www.linkedin.com/pulse/semantic-knowledge-graphs-versus-property-andreas-blumauer/)

The STIX 2.1 specification content more closely aligns with a Property Graph representation rather than a Semantic Graph representation. This is due to the use of **Relationship** nodes between STIX Objects. This is a perfectly legitimate structure choice, but does not afford us with the full set of semantic tools we would like. Therefore, a series of representations to represent the STIX 2.1 standard as a full Semantic Graph have been taken.

## Multilayered Approach
The TAC Github repository contains content which is subject to change as development progresses. The tac-ontology repository has the following structure:

1. **tac-ontology** *(the root repository directory)*
	1. **etc** *(directory with an example pre-commit script and suggested .gitignore file)*
	1. **img** *(images directory)*
	1. **stix-spec** *(directory with the OWL files that define the STIX 2.1 Specification in RDF/XML)*
	1. **stem-semex** *(semantic extension (semex) directory with the OWL files that extend the stix-spec ontology with ObjectProperties to map the Relationship Objects (SROs))*
	1. **tac** *(directory with the extension of the stix-semex ontology to add the Threat Actor Context concepts)*
	
![Directory Structure](/img/main/tac-ontology-folder-structure.png)

### STIX as a Property Graph (stix-spec.owl)
This representation will be as close as possible to the STIX 2.1 Specification.

1. **stix-spec**
	1. stix.owl
	1. stix-spec.owl
	1. **core** 
	1. **cyber-observables**
	1. **meta-objects**
	1. **threat intel**
	1. **vocabularies**
	
#### STIX-SPEC.OWL imports STIX.OWL
To represent all the content of the STIX 2.1 Specification we have separated many of the Domain assertions and Restrictions into separate files. As you examine the files you may observe this as _pairs_ of files. For example:

***directory.owl*** and ***directory-context.owl***

Where the domain assertions are restrictions as defined in the STIX 2.1 specification are asserted in the directory-context.owl file.

### STIX Semantic Extension Graph (stix-semex.owl)
This representation will extend the stix.owl representation with the ObjectProperty and DataProperty predicates encapsulated in the *Relationship* objects in the STIX 2.1 specification.
 
1. **stix-semex**
	1. stix-semex.owl
	1. **sro-properties**
	
#### STIX-SEMEX Imports STIX.OWL
Because of the modularization, we can import only the part of the STIX 2.1 Specification as needed for semantic extension. Hence stix-semex.owl imports stix.owl, but not stix-spec.owl. The reason for this is a topic that should be examined in depth. It is not possible to fully explain why this is true in this *README* file. However, it can be noted that it has to do with how a formal Description Logics Reasoner interprets domain, range, restriction, and cardinality assertions. 

### TAC Semantic Graph Importing STIX Semantic Extension Graph (tac.owl)
This third layer of representation will add the concepts of the TAC-TC members.

1. **tac**
	1. tac.owl
	
The TAC ontology imports the stix-semex.owl file.

# Editing Style and Syntax Normalization
Developers have their own preferences when in comes to ontology editors and writing styles. This causes dificulties in managing a common repository used by multiple ontology contributors. To resolve the problem, all ontology content submitted and persisted in the TAC ontology repository must be ***Normalized*** with a utility called the **RDF Toolkit**. This utility puts the submitted content into a standardized form. It removes any stylistic differences between contributors.

## Use of **pre-commit** script
In the tac-ontology/etc/ directory is an example githook script. This **pre-commit** script will allow the user to edit the ontology with their preferred ontology editor, and when they commit the changes, the pre-commit script _normalizes_ the ontology content. 

## Contact

Please send questions or comments about [OASIS TC GitHub repositories](https://www.oasis-open.org/resources/tcadmin/github-repositories-for-oasis-tc-members-chartered-work) to the [OASIS TC Administrator](mailto:tc-admin@oasis-open.org).  For questions about content in this repository, please contact the TC Chair or Co-Chairs as listed on the the TAC TC's [home page](https://www.oasis-open.org/committees/tac/).

 

