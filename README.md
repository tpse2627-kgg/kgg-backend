# kgg-core

Python core of the Knowledge Graph Generator (TPSE 2026/27, TU Darmstadt).

```
core/             Python package, plain logic without Django (pyproject.toml)
docs/
├── minutes/      minutes of all meetings (AG, jour fixe, retros, TB)
├── decisions/    architecture and process decisions
├── spec/         specification document (source + submitted PDFs)
└── process/      how we work (process.md)
```

The Django app lives in [kgg-django](https://github.com/tpse2627-kgg/kgg-django), the React UI in [kgg-frontend](https://github.com/tpse2627-kgg/kgg-frontend).

## Branching

We use [git-flow](https://nvie.com/posts/a-successful-git-branching-model/) (to be confirmed by the team):

| Branch | Purpose |
|---|---|
| `main` | Released versions only (what the AG gets), each release tagged (`v0.1.0`, …) |
| `develop` | Integration branch; the default branch, all feature work is merged here |
| `feature/<issue>-<name>` | One per issue, branched from `develop`, merged back via pull request |
| `release/<version>` | Prepares a release from `develop`, merged into `main` and `develop` |
| `hotfix/<version>` | Urgent fix branched from `main`, merged into `main` and `develop` |

## Commit messages

We follow the [Karma commit convention](https://karma-runner.github.io/6.3/dev/git-commit-msg.html) / [semantic commit messages](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716) (to be confirmed by the team):

```
<type>(<scope>): <subject>

<body: what and why, wrapped at 80 characters>

<footer: Closes #12, BREAKING CHANGE: ...>
```

- **type:** `feat` (new feature), `fix` (bug fix), `docs`, `style` (formatting, no code change), `refactor`, `perf`, `test`, `build`, `ci`, `chore` (tooling, no production code)
- **scope:** optional, the part of the code, e.g. `extract`, `api`, `review-ui`
- **subject:** imperative, present tense, lowercase, no period, first line at most 70 characters
- Example: `feat(extract): add ontology-guided label extractor`
