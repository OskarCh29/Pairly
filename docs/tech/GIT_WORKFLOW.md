- [1. Purpose](#purpose)
- [2. Branching Strategy](#branching-strategy)
- [3. Branch Naming](#branch-naming)
- [4. Development Flow](#development-flow)
- [5. Commit Convention](#commit-convention)
- [6. Versioning](#versioning)

# Purpose

This document defines the Git workflow used throughout the Pairly project.

The goal is to keep development predictable, maintain a clean Git history and ensure every change meets the project's
quality standards.

# Branching Strategy

```text
                  main
               ▲   ▲   ▲
               │   │   │
        feature/*  │  hotfix/*
               │   │
         bugfix/*  │
               │   │
               └───┘
```

# Branch Naming

- feature/timeline
- feature/shared-calendar
- bugfix/login
- hotfix/security-token
- docs/arch-documentation
- release/0.4.0

## Rule:

`feature/{bounded-context}-{feature}` - `feature/timeline-photo-upload`

# Development Flow

```text
┌──────────────┐
│ Create Issue │
└──────┬───────┘
       │
       ▼
┌────────────────┐
│ Create Branch  │
└──────┬─────────┘
       │
       ▼
┌──────────────────────┐
│ Implement Feature    │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Write / Update Tests │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Run Spotless & Build │
└──────┬───────────────┘
       │
       ▼
┌──────────────┐
│ Commit Code  │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Push Branch  │
└──────┬───────┘
       │
       ▼
┌──────────────────────┐
│ Open Pull Request    │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Code Review & CI     │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Squash & Merge       │
└──────┬───────────────┘
       │
       ▼
┌──────────────────────┐
│ Delete Feature Branch│
└──────────────────────┘
```

# Commit Convention

| Prefix   | Description                                         | Example                                       |
|----------|-----------------------------------------------------|-----------------------------------------------|
| feat     | Introduces a new feature                            | `feat(chat): add message reactions`           |
| fix      | Fixes a bug                                         | `fix(auth): prevent token expiration issue`   |
| docs     | Documentation only changes                          | `docs(readme): update installation guide`     |
| refactor | Internal code improvements without behavior changes | `refactor(user): simplify validation logic`   |
| test     | Adds or updates tests                               | `test(chat): add websocket integration tests` |
| style    | Formatting, whitespace or code style changes        | `style: apply Spotless formatting`            |
| perf     | Performance improvements                            | `perf(search): optimize database query`       |
| build    | Build system or dependency changes                  | `build: upgrade Gradle to 9.0`                |
| ci       | Continuous Integration changes                      | `ci: add GitHub Actions workflow`             |
| chore    | Miscellaneous maintenance tasks                     | `chore: update .gitignore`                    |


## Commit Message Format

Every commit should follow the Conventional Commits specification:

```text
<prefix>: <short description>
```

Examples:

```text
feat: add message reactions

fix: validate expired JWT

docs: update roadmap

refactor: extract reminder service

test: add integration tests
```
---

# Versioning
## Semantic Versioning

Pairly follows Semantic Versioning (SemVer).

```text
MAJOR.MINOR.PATCH
```

Example:

```text
1.4.2
│ │ └── Patch
│ └──── Minor
└────── Major
```

### MAJOR

Increment when introducing incompatible API or architectural changes.

Examples:

- removing public endpoints
- breaking database migrations
- incompatible API contracts

```
1.0.0 → 2.0.0
```

---

### MINOR

Increment when introducing new backwards-compatible functionality.

Examples:

- new Timeline feature
- new Calendar module
- AI suggestions
- achievements

```
1.2.0 → 1.3.0
```

---

### PATCH

Increment for backwards-compatible bug fixes.

Examples:

- fix authentication bug
- improve validation
- fix websocket reconnect

```
1.3.1 → 1.3.2
```