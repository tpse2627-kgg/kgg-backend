# Knowledge Graph Generator: Specification

**Teamprojekt Softwareentwicklung 2026/27, TU Darmstadt · Team 080**
**Client:** Ning Xia, Research Data Management Group, Chair of Fluid Systems, TU Darmstadt
**Team:** Surkhabjit Singh, Mahdi Rafiei, Mohammad Riad Loutfi, Arian Faruqui, Denis Ücyildiz, M Adel Zitouni
**Version:** 13.11.2026

## 1. Project Description

### Vision

Our client is building an information retrieval system that collects mostly unstructured data from different sources and makes it searchable. Knowledge graphs store its relations in a structured, queryable way, but building them by hand takes time and expert knowledge and leads to inconsistencies. The Knowledge Graph Generator (KGG) manages graphs built from raw data and a given ontology: their triples can be stored, read, edited and updated, and every change is saved as a version so it can be traced. When the system cannot decide something, a human decides. In the long term, the client wants the KGG to run permanently in the institute's backend as its own project that they keep developing.

### Current and Target State

The institute runs a search portal with a React frontend and a Django backend that uses several databases, among them the graph database Fuseki. Contrary to the call for projects, the client made clear that generating the graph is not the focus, because it is still mostly a research problem. Instead, the KGG receives ready-made triples and manages and versions them, so that a generation step can be added later. New triples are checked against the existing graph to avoid duplicate entities, and unclear cases go to a reviewer. We agreed with the client that the KGG gets its own backend with a Python core, called by the institute's backend over a REST API, plus a simple frontend for the reviewer. Since the institute's backend uses Django, we propose to build ours as a Django app that the institute could also install directly. The client values software the institute can maintain and extend, and code the team fully understands.

### Domain

A knowledge graph stores facts as triples of subject, predicate and object. RDF is a standard format for these triples, and an ontology defines the allowed classes and relations. Linked Data Event Streams (LDES) describe changes to an RDF graph as a stream of versions, so older states can be restored. Human-in-the-loop means that a person, the reviewer, decides when the system is not sure. Three roles work with the KGG: the client system, currently the institute's backend, sends triples over our REST API and gets the results back; the reviewer decides unclear cases in the frontend; the maintainers, developers at the institute, run, integrate and further develop the KGG. Other stakeholders are the client, who sets priorities and accepts requirements, and our course supervisor.

### Architecture

![Architecture of the Knowledge Graph Generator](architecture.png)

*Figure 1: Planned architecture. The split into three repositories is our proposal and still has to be confirmed by the client.*
