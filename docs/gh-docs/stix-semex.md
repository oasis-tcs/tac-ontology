# STIX 2.1 Represented as a Semantic Graph

## Overview Documents
1. [STIX Specification Ontology](/docs/gh-docs/stix-spec.md)
2. [STIX Semantic Extension Ontology](/docs/gh-docs/stix-semex.md)
3. [Threat Actor Context Ontology](/docs/gh-docs/tac.md)
 
# Overview
A primary reason for representing STIX 2.1 as a semantic graph is that knowledgebases can be examined by a Description Logics Reasoner. This means that known facts asserted into a knowledgebase can be used in combination with domain knowledge to infer new facts. This is known as [entailment](https://www.vocabulary.com/dictionary/entailment#:~:text=An%20entailment%20is%20a%20deduction,the%20others%20are%20also%20true.).

Frankly, the ability for a computational method to draw conclusions or making formal logical judgements is needed to keep pace with the volocity of data Threat Analysts must analyze.

There are many good articles comparing Property Graphs with Semantic Graphs. 
Dave McComb in October of 2019 wrote:
[Property Graphs: Training Wheels on the way to Knowledge Graphs](https://www.semanticarts.com/property-graphs-training-wheels-on-the-way-to-knowledge-graphs/) which I found to be interesting given my bias toward semantic graphs.

# SRO to owl:ObjectProperty

## The STIX Semantic Extension OWL:ObjectProperty
The stix-semex.owl ontology has added owl:ObjectProperty definitions for each of the SROs.

Hence, when an SRO is expressed in a STIX report, it can be expressed as a semantic graph governed by the STIX Semantic Extension ontology.

