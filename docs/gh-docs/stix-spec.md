# An Ontology of the STIX 2.1 Specification

## Overview Documents
1. [STIX Specification Ontology](/docs/gh-docs/stix-spec.md)
2. [STIX Semantic Extension Ontology](/docs/gh-docs/stix-semex.md)
3. [Threat Actor Context Ontology](/docs/gh-docs/tac.md)

# Overview
## Why?
The short answer is *Semantic Interoperability*. It is not suficient today to limit ourselves to _operability_, because the volumes and volocity of data to be considered mandates we use computers to keep up!

### Interoperability vs. Semantic Interoperability
There is a difference between _syntactic_ interoperability and _semantic_ interoperability. *_Syntactic_* interoperability does provide partial disambiguation, in that variables with the same syntax can be matched between different computer applications. However, just because we use the exact same syntax, does not guarantee that they have the same meaning to two different applications. Consider as an example, the variable *size*, it is possible that to or more applications use this syntax, yet remain prblematic. Size may mean a precise metric of length, widthe, and girth, whereas to another application it can mean a value from an enumeration such as { "small", "medium", "large" }

# Tightly Coupled to the Specification
The STIX 2.1 Specification ontolgy (stix-spec.owl) is meant to be as true of a ontology representation to the OASIS STIX 2.1 Specification document as possible. 

## STIX Relationship Objects (SROs)
In the STIX 2.1 Specification, The CTI-TC members implemented some relationships between STIX Domain Objects (SDOs) with additional nodes called SRO objects. Therefore the STIX Specification has a different way of representing a *_predicate_* and its value.

This makes the representation of STIX similar to a _propery_ _graph_ rather than a semantic graph.

A Description Logics Reasoner is meant to interpret semantic graphs, not property graphs.

## Domains and Restrictions
To facilitate the representation of STIX 2.1 as a semantic graph, we must be able to represent the SROs with owl:objectProperty predicates. This is the purpose of the [STIX Semantic Extension](https://github.com/oasis-tcs/tac-ontology/docs/gh-docs/stix-semex.md)

We have represented the domain assertions and the predicate object restrictions in separate files so that they do not need to be imported into the STIX Semantic Extension ontology.




