ARGO – **G**uidelines for **a**utomatically recognising and **r**epairing **O**WL 2 profile violations
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
This document contains the guidelines for recognising and repairing OWL 2 profile violations. The purpose is to determine through community discussion what constitutes a profile violation (definition), how to recognise it (recognition) and whether there should be an automated repair strategy (repair). One part of the definition of ARGO is to properly group the violations, which is also up for discussion. We are working closely with the developers of the OWL API in order to provide a consistent and community-accredited implementation of the guidelines.

# Basic definitions

|  | Specification |
|---|---|
| **O** | The ontology under consideration excluding its imports. |
| **O'** | The ontology under consideration including its full imports closure. |
| **S(O):** | The signature of O, i.e. the set of all class names, object property names, data property names and individual names occuring across any **logical** axiom in O (including declarations). |
| **SA(O):** | The signature of O, i.e. the set of all class names, object property names, data property names, **annotation property names** and individual names occuring across **any** axiom in O. |
----


# Guidelines


## Declaration Failure

### Use of undeclared class

|  | Specification |
|---|---|
| **Definition:** | A class name A from S(O) has been used as part of an OWL axiom in O but has not been declared. |
| **Recognition:** |  |
| **Repair:** | Gene Ontology (GO), v2.13; Foundational Model of Anatomy Ontology (FMA), v4.22; |
| **Debate:** | Class names in annotations? S(O) vs S(O')? O or O'? |
| **OWL API:** | [UseOfUndeclaredClass](http://owlcs.github.io/owlapi/apidocs_5/org/semanticweb/owlapi/profiles/violations/UseOfUndeclaredClass.html) |
----
