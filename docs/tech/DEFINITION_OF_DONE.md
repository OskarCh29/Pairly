# Definition of Done

> Every feature merged into the `main` branch must satisfy the following requirements.

---

# Purpose

The Definition of Done ensures that every completed task meets the same quality standards.

A feature is considered **Done** only when it is fully implemented, tested, documented and ready for production.

---

# Functional Requirements

- [ ] Business requirements are fully implemented.
- [ ] Acceptance criteria are satisfied.
- [ ] No unfinished functionality remains.
- [ ] Feature behaves correctly in edge cases.

---

# Code Quality

- [ ] Code follows the project Coding Guidelines.
- [ ] No duplicated logic without justification.
- [ ] No unnecessary complexity.
- [ ] No commented-out code.
- [ ] No temporary hacks or debug code.
- [ ] Meaningful naming is used.

---

# Testing

- [ ] Unit tests added or updated.
- [ ] Existing tests pass.
- [ ] Manual testing completed.
- [ ] Edge cases verified.
- [ ] Pipeline finishes without errors

---

# Documentation

- [ ] Public API documented.
- [ ] Swagger/OpenAPI updated (if applicable).
- [ ] Documentation updated if behavior changed.
- [ ] Domain Model updated when introducing new concepts.

---

# Security

- [ ] Input validation implemented.
- [ ] Authorization verified.
- [ ] No sensitive information exposed.
- [ ] Secrets are not hardcoded.

---

# Observability

- [ ] Proper logging added.
- [ ] Errors return meaningful responses.
- [ ] Metrics updated (if required).

---

# Performance

- [ ] No unnecessary database queries.
- [ ] No obvious performance regressions.
- [ ] Caching considered where appropriate.

---

# Git

- [ ] Branch is up to date.
- [ ] Commit messages follow Conventional Commits.
- [ ] Pull Request created.
- [ ] Pull Request reviewed (if applicable).

---

# Final Checklist

A feature can be merged only if:

- [ ] All Definition of Done items are completed.
- [ ] The implementation aligns with the Product Vision.
- [ ] The implementation does not violate the Domain Model.
- [ ] The feature is production-ready.
---
---

# Pairly Quality Questions

Before merging a feature, ask yourself:

- Does this feature support the Product Vision?
- Does it enrich the couple's shared story?
- Does it respect the Relationship First principle?
- Is it the simplest possible solution?
- Would I be proud to maintain this code in one year?