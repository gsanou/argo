ARGO – Guidelines for Automatically recognising and Repairing OWL 2 profile violations
==============

## Working draft 29 March 2017

**Editors**:

Nicolas Matentzoglu, Manchester University

**Edit history:**

| Version | Date | Contributors | Changes |
|---|---|---|---|
| 0.0.1 | 29.03.2017 | Nicolas Matentzoglu | First version |
----

# Summary 
This document contains the guidelines for recognising and repairing OWL 2 profile violations. The purpose is to determine through community discussion what constitutes a profile violation (definition), how to recognise it (recognition) and whether there should be an automated repair strategy (repair). One part of the definition of ARGO is to properly group the violations, which is also up for community discussion. The basic grouping, using the four main OWL 2 profiles (DL, EL, RL, QL) and general OWL 2 violations, serves to better localise the violations for those interested in one particular profile. It should be noted that, in order to be valid EL, RL and QL, the ontology needs to be valid OWL 2 DL. In order to be valid OWL 2 DL, the ontology needs to be valid OWL 2. We are working closely with the developers of the OWL API in order to provide a consistent and community-accredited implementation of the guidelines. 

# Basic definitions

|  | Specification |
|---|---|
| **O** | The ontology under consideration excluding its imports. |
| **O'** | The ontology under consideration including its full imports closure. |
| **S(O):** | The signature of O, i.e. the set of all class names, object property names, data property names and individual names occuring across any **logical** axiom in O (including declarations). |
| **SA(O):** | The signature of O, i.e. the set of all class names, object property names, data property names, **annotation property names** and individual names occuring across **any** axiom in O. |
----

# General OWL 2 Violations

# OWL 2 DL Violations

## Declaration Failure

### Use of undeclared class

|  | Specification |
|---|---|
| **Definition:** | A class name A from S(O) has been used as part of an OWL axiom in O but has not been declared. |
| **Recognition:** |  |
| **Repair:** | Inject a class [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | Class names in annotations? S(O) vs S(O')? O or O'? |
| **OWL API:** | [UseOfUndeclaredClass](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredClass.html) |
----

### Use of undeclared object property

### Use of undeclared data property

### Use of undeclared annotation property

### Use of undeclared data type

## Misuse of reserved vocabulary

## Inherent Violation of OWL DL Profile

## Syntax violations

# OWL 2 EL Violations

# OWL 2 RL Violations

# OWL 2 QL Violations



