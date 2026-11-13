## 2. Deliverables

**User interface.** The main interface of the Knowledge Graph Generator (KGG) is a REST API, through which the client's backend sends data and receives the results. The REST API is part of a Django app (kgg-django) that the institute can also install directly in its own backend. The graph logic is a Python package without Django (kgg-core). For human-in-the-loop, a reviewer uses a simple React web application (kgg-frontend).

**Development environment and tools.** We develop in Python with Django and in React. We plan with GitHub issues and Projects and merge every change through a reviewed pull request. All repositories follow git-flow and the Karma commit convention.

**Hardware.** No special hardware is needed. Every team member works on their own computer, and the client offers the institute's PC pool and servers if needed.

**Testing.** The core logic and the REST API are covered by automated tests. A pull request is merged only after another team member has reviewed it and all checks pass. At the end of each two-week iteration, the client accepts finished requirements in a demo against their acceptance criteria. The client provides freely available sample data as test data.

**Target environment.** In the long term, the KGG runs on the institute's server as part of its Django-based backend. During the project, it runs locally with a local database. If needed, the client provides a Dockerfile or a virtual machine.

**Artefacts.** We deliver the source code of all three repositories with their automated tests. Every requirement comes with tests for its new behaviour and updated user documentation, and each repository has a README on setup and usage. Releases are tagged on the main branch. kgg-core also holds this specification, all meeting minutes and our process documentation.

**Form of delivery.** All artefacts are in our public GitHub organisation, visible to the client at any time. At the end, we push all repositories to the institute's GitLab. The software will be published as open source.

**Change requests.** Change requests come via the iteration meeting or Discord. We record each one as a GitHub issue with acceptance criteria and estimate it. The client sets its priority, and we plan it into a coming iteration. The minimum scope only changes by mutual agreement, recorded in the minutes.

**Minimum scope.** The client named storing, reading, editing, updating and versioning triples as the main focus. The project is passed when the client's backend can send triples over the REST API, the KGG stores them in a local database, they can be read, edited and updated over the API, and every change is recorded as a version with Linked Data Event Streams (LDES). A reviewer can also accept or reject triples marked as unclear in the web frontend. A graph visualisation and Neo4j compatibility are not required but desirable.

**Use of AI.** The client allows us to generate code with AI if it is reviewed and the team understands it and can answer any question about it. The institute provides no AI tools.
