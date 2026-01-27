# Contributing to Bookshelf

Thank you for your interest in contributing to Bookshelf. This repository uses GitHub Issue Forms to collect structured requests and follows a branching strategy that combines GitLab Flow environments with Git Flow–style release and hotfix branches.

## Table of contents

- [How to get help / ask questions](#how-to-get-help--ask-questions)
- [Before you start](#before-you-start)
- [Creating issues](#creating-issues)
- [Branch strategy](#branch-strategy)
- [Development workflow](#development-workflow)
- [Pull request expectations](#pull-request-expectations)
- [Labeling and triage workflow](#labeling-and-triage-workflow)
- [Security issues](#security-issues)

## How to get help / ask questions

For usage questions, support, broad design discussions, or “is this a good idea?” conversations, use GitHub Discussions:

- https://github.com/hamashou74/bookshelf/discussions

## Before you start

- Be respectful and constructive in all interactions.
- Keep changes scoped and reviewable (small PRs are easier to review and ship).
- Avoid including secrets (tokens, credentials) in issues/PRs/logs.

## Creating issues

Blank issues are disabled. Please use one of the Issue Forms under `/.github/ISSUE_TEMPLATE/`:

- **Feature**: new feature or enhancement
- **Fix (Bug)**: defect/regression
- **Chore**: maintenance/refactor/dependencies/tooling
- **Release**: release planning & tracking
- **Hotfix**: urgent production fix

Each form requests a **Suggested branch name** that follows the repository branch rules (see below). Please fill it in—maintainers may use it as-is.

### Issue form “Affected area” → label mapping

Issue forms ask for “Affected area” using human-friendly options. In PRs/issues, we use these labels:

- Frontend (Next.js) → `area: frontend`
- Backend (Django REST Framework) → `area: backend`
- API contract → `area: api`
- Database → `area: database`
- CI/CD & DevOps → `area: ci-cd`
- Documentation → `area: docs`

## Branch strategy

### Long-lived branches

- `master`: integration branch (default target for most PRs)
- `production`: production-ready branch (deployed)

### Short-lived branches

Create branches using the following prefixes:

- `feature/*` from `master`
- `fix/*` from `master`
- `chore/*` from `master`
- `release/*` from `master`
- `hotfix/*` from `production`

### Branch naming convention

Use the convention required by the Issue Forms:

- `feature/<issue-number>-<short-slug>`
- `fix/<issue-number>-<short-slug>`
- `chore/<issue-number>-<short-slug>`
- `release/<version>`
- `hotfix/<issue-number>-<short-slug>`

## Development workflow

1. **Open an issue first** (recommended)
   - Use the Issue Forms so we get the necessary context and can triage quickly.
2. **Create a branch**
   - Follow the prefix + “created from” rules above.
3. **Implement with tests**
   - Frontend (Next.js): keep UI changes covered by appropriate tests where feasible.
   - Backend (Django/DRF): include/adjust tests and migrations when applicable.
4. **Keep changes focused**
   - Split unrelated work into separate PRs.
5. **Prepare for review**
   - Run linters/tests locally where available.
   - Update docs when behavior changes.

> Note: Repository-specific setup commands vary by environment. If a `README` exists, follow it as the source of truth for local setup. Typical stacks use Node.js tooling for Next.js and Python tooling for Django/DRF.

## Pull request expectations

- Use the repository **Pull Request Template**.
- Prefer PRs that are:
  - Small and scoped
  - Clearly explained (what/why/how)
  - Easy to verify (explicit test plan)
- Target branches:
  - `feature/*`, `fix/*`, `chore/*` → PR into `master`
  - `release/*` → PR into `master` for release preparation; final merge/promotion to `production` as part of release execution
  - `hotfix/*` → PR into `production` for urgent deployment, then back-merge into `master` to keep branches aligned

## Labeling and triage workflow

Issues created via forms will receive default labels (for example, `type: feature` and `status: triage`). Maintainers will update:

- `status:*` as the work progresses (`status: ready` → `status: in-progress` → `status: review` → `status: done`)
- `priority:*` based on impact/urgency (`priority: P0`..`priority: P3`)
- `area:*` based on impacted components

Please **do not rename labels**. If you think a label is missing, propose it in Discussions.

## Security issues

Do **not** open public issues for potential vulnerabilities.
Please follow the instructions in `SECURITY.md` (private reporting via Security Advisories).
