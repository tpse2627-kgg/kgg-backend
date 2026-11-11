# Knowledge Graph Generator: Specification

**Bachelor-Praktikum 2026/27, TU Darmstadt · Team 080**
**Client:** Ning Xia, Research Data Management Group, Chair of Fluid Systems, TU Darmstadt
**Team:** Surkhabjit Singh, Mahdi Rafiei, Mohammad Riad Loutfi, Arian Faruqui, Denis Ücyildiz, M Adel Zitouni
**Version:** 11.11.2026

## 1. Project Description

### Vision

Our client, the Research Data Management Group at the Chair of Fluid Systems, is building an information retrieval system that collects data from different sources and makes it searchable. This data is spread over many places, comes in different forms and is mostly unstructured. Knowledge graphs store the relations in such data in a structured way, for example in RDF, so they can be queried. Building them by hand takes a lot of time and expert knowledge and easily leads to inconsistencies. The Knowledge Graph Generator (KGG) manages graphs that are built from raw data and a given ontology. Their triples can be stored, read, edited and updated, and every change is saved as a version so it can be traced later. When the system cannot decide something, a human decides. In the long term, the client wants the KGG to run permanently in the institute's backend as its own project that they keep developing.

### Current and Target State

Right now the institute has a web application that works like a search portal, with a React frontend and a Django backend that uses several databases, among them the graph database Fuseki. Generating knowledge graphs automatically is still mostly a research problem. That is why our focus is not the generation itself but what comes after it: storing, reading, editing, updating and versioning the triples. For versioning we use Linked Data Event Streams (LDES). New triples are checked against the existing graph with reasoning so that no duplicate entities are created, and unclear cases go to the reviewer. We agreed with the client that the KGG gets its own Django backend with a Python core, which the institute's backend calls over a REST API, plus a simple frontend for the reviewer. For now the results stay in a local database. The backend has priority, a graph visualisation is optional. The software will be published as open source.

### Domain

A knowledge graph stores facts as triples of subject, predicate and object. RDF is a standard format for these triples, and an ontology defines which classes and relations are allowed. LDES describes changes to an RDF graph as a stream of versions, so older states of the graph can be restored. Human-in-the-loop means that a person, the reviewer, decides when the system is not sure. Three roles work with the KGG. The client system is software, currently the institute's backend. It calls our REST API, sends the data, which will probably be plain text or ready-made triples, and gets the results back. The reviewer uses the frontend to decide unclear assignments. The maintainers are developers at the institute who administer and run the KGG, integrate it into their software if possible and keep developing it. Other stakeholders are the client, who sets priorities and accepts requirements, and our course supervisor. The client's current data is freely available and not confidential.

### Architecture

*Figure 1: The client system (the existing institute backend) sends data to the KGG over a REST API. Our planned system has three repositories: kgg-django provides the REST API and stores the data, kgg-core contains the logic for managing and versioning the graph, and kgg-frontend is used by the reviewer. The maintainers run and develop the system. The split into these three repositories is our proposal and still has to be confirmed by the client.*
