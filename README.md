ARGO – Guidelines for Automatically recognising and Repairing OWL 2 profile violations
==============

## Working draft 29 March 2017

**Editors**:

Nicolas Matentzoglu, Manchester University

**Edit history:**

| Version | Date | Contributors | Changes |
|---|---|---|---|
| 0.0.1 | 29.03.2017 | Nicolas Matentzoglu | First version: reflecting the state of the OWL API 4.3.1. |
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

# General points of discussions

* Profile checking against O vs O'

# General OWL 2 Violations

### OntologyIRINotAbsolute

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonAbsoluteIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### LexicalNotInLexicalSpace

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfDefinedDatatypeInDatatypeRestriction

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalFacetRestriction

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfUndeclaredDatatype

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

# OWL 2 DL Violations

## Declaration Failure

### Use of undeclared class

|  | Specification |
|---|---|
| **Definition:** | A class name A from S(O') has been used as part of an OWL axiom in O' but is neither built-in vocabulary nor has been declared. |
| **Recognition:** | Given a class A in S(O'), A is considered undeclared if it is not built-in vocabulary and there exists no declaration axiom Declaration(A). |
| **Repair:** | Inject a class [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | [Entity names in annotations?](https://github.com/owlcs/argo/issues/1) |
| **OWL API:** | [UseOfUndeclaredClass](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredClass.html) |
| **OWL API Support:** | 4.3.1 |
----

### Use of undeclared object property

|  | Specification |
|---|---|
| **Definition:** | An object property name P from S(O') has been used as part of an OWL axiom in O' but is neither built-in vocabulary nor has been declared. |
| **Recognition:** | Given an object property P in S(O'), P is considered undeclared if it is not built-in vocabulary and there exists no declaration axiom Declaration(P). |
| **Repair:** | Inject an object property [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | See [use of undeclared class](#use-of-undeclared-class) |
| **OWL API:** | [UseOfUndeclaredObjectProperty](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredObjectProperty.html) |
| **OWL API Support:** | 4.3.1 |
----


### Use of undeclared data property

|  | Specification |
|---|---|
| **Definition:** | A data property name P from S(O') has been used as part of an OWL axiom in O' but is neither built-in vocabulary nor has been declared. |
| **Recognition:** | Given a data property P in S(O'), P is considered undeclared if it is not built-in vocabulary and there exists no declaration axiom Declaration(P). |
| **Repair:** | Inject an data property [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | See [use of undeclared class](#use-of-undeclared-class) |
| **OWL API:** | [UseOfUndeclaredDataProperty](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredDataProperty.html) |
| **OWL API Support:** | 4.3.1 |
----


### Use of undeclared annotation property

|  | Specification |
|---|---|
| **Definition:** | An annotation property name P from S(O') has been used as part of an OWL axiom in O' but is neither built-in vocabulary nor has been declared. |
| **Recognition:** | Given an annotation property P in S(O'), P is considered undeclared if it is not built-in vocabulary and there exists no declaration axiom Declaration(P). |
| **Repair:** | Inject an annotation property [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | See [use of undeclared class](#use-of-undeclared-class) |
| **OWL API:** | [UseOfUndeclaredAnnotationProperty](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredAnnotationProperty.html) |
| **OWL API Support:** | 4.3.1 |
----

### Use of undeclared data type

|  | Specification |
|---|---|
| **Definition:** | A datatype has been used as part of an OWL axiom in O' but is neither built-in vocabulary, nor the top datatype, nor has been declared. |
| **Recognition:** | Given a datatype DT used in an axiom in O, DT is considered undeclared if it is not built-in vocabulary, not the top datatype, and there exists no declaration axiom Declaration(P). |
| **Repair:** | Inject an annotation property [declaration](https://www.w3.org/TR/owl2-syntax/#Entity_Declarations_and_Typing) axiom into the ontology. |
| **Debate:** | See [use of undeclared class](#use-of-undeclared-class) |
| **OWL API:** | [UseOfUndeclaredDatatype](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredDatatype.html) |
| **OWL API Support:** | 4.3.1 |
----

## Misuse of reserved vocabulary

### UseOfReservedVocabularyForOntologyIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForVersionIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForClassIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForObjectPropertyIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForDataPropertyIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForAnnotationPropertyIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfBuiltInDatatypeInDatatypeDefinition

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfReservedVocabularyForIndividualIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

## Inherent Violation of OWL DL Profile

### UseOfUnknownDatatype

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### DatatypeIRIAlsoUsedAsClassIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### DatatypeIRIAlsoUsedAsClassIRI

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### CycleInDatatypeDefinition

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### IllegalPunning

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfTopDataPropertyAsSubPropertyInSubPropertyAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInCardinalityRestriction

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInObjectHasSelf

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInFunctionalPropertyAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInInverseFunctionalObjectPropertyAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInIrreflexivePropertyAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInAsymmetricObjectPropertyAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSimplePropertyInDisjointPropertiesAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfPropertyInChainCausesCycle

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

## Syntax violations

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### EmptyOneOfAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### InsufficientOperands

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### InsufficientPropertyExpressions

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### InsufficientIndividuals

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

# OWL 2 EL Violations

### UseOfIllegalDataRange

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfAnonymousIndividual

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfObjectPropertyInverse

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalDataRange

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfObjectOneOfWithMultipleIndividuals

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfDataOneOfWithMultipleLiterals

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### LastPropertyInChainNotInImposedRange

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

# OWL 2 RL Violations

### UseOfNonSubClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSuperClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonEquivalentClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalDataRange

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

# OWL 2 QL Violations

### Use of illegal data range

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfAnonymousIndividual

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalAxiom

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfIllegalDataRange

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSubClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonSuperClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----

### UseOfNonAtomicClassExpression

|  | Specification |
|---|---|
| **Definition:** | Tbd. |
| **Recognition:** | Tbd. |
| **Repair:** | Tbd. |
| **Debate:** | Tbd. |
| **OWL API:** | [OntologyIRINotAbsolute](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/OntologyIRINotAbsolute.html) |
| **OWL API Support:** | 4.3.1 |
----
