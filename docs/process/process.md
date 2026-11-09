# Our process

Applies to **both repos**, [kgg-backend](https://github.com/tpse2627-kgg/kgg-backend) and [kgg-frontend](https://github.com/tpse2627-kgg/kgg-frontend): same branching model, commit convention, pull request and review rules.

## Iterations

Two-week iterations, tracked with the **Iteration** field in the [GitHub Project](https://github.com/orgs/tpse2627-kgg/projects/1). Course deadlines are GitHub **milestones** (same names in both repos).

1. **AG meeting** (every two weeks, Zoom): live demo, acceptance against the acceptance criteria, new requirements, the AG sets priorities.
2. **Planning** (same or next day): estimate new stories with pointing poker (story points → **Estimate**), pick what fits our velocity, assign issues.
3. **Build:** feature branches and pull requests; pair programming for hard or unfamiliar parts.
4. **QA:** reviews, tests, pairing.
5. **Retrospective** at the end of the iteration (what went well, what we change); minutes in `docs/minutes/`.

## Requirements

- Every requirement is a GitHub issue written as a user story: *As a <role> I want <goal> so that <reason>*, plus testable acceptance criteria.
- Project fields: **Status** (Planning → Ready → Building → Review → Delivered), **Priority** (set by the AG), **Size**, **Estimate** (story points), **Iteration**, **Epic**, **Milestone**.
- Accepted by the AG: comment with the date and a link to the minutes, then close the issue.

## Branches, commits, pull requests

- Branching: git-flow, see the [README](../../README.md#branching). Feature branches `feature/<issue>-<name>` from `develop`.
- Commit messages: Karma / semantic convention, see the [README](../../README.md#commit-messages).
- No direct pushes to `main` or `develop`; everything goes through a pull request into `develop`.
- Every pull request is reviewed by someone who didn't write it; reviewers rotate.
- Merge when the reviewer approved, all conversations are resolved and the checks are green.

## Definition of Done

A story is done when:

- [ ] all acceptance criteria are met and shown to the AG
- [ ] the code is merged into `develop` via a reviewed pull request
- [ ] tests cover the new behaviour and pass
- [ ] user-facing docs / README are updated
- [ ] the AG accepted it in the iteration meeting (comment with date + link to the minutes)

## Meetings

- **Jour fixe** (internal, at least once per iteration): rotating moderation and minutes.
- **AG meeting** every two weeks via Zoom: we lead it, send the agenda a day before and the minutes afterwards.
- Minutes: `docs/minutes/YYYY-MM-DD-<type>.md` (`ag`, `jourfixe`, `retro`, `tb`).

## Time tracking

Everyone logs all project hours with a category in the team time sheet: <https://docs.google.com/spreadsheets/d/1mPX6G1EuQ7C9JWnfxB6Ccsp0O6WIMkB1NZs531iJvsE/edit>
Categories: Implementation · QA – Tests · QA – Code Reviews · QA – Pair Programming · Meetings & Organisation · Documentation · Talks & Trainings · Research & Onboarding.
