# Coding Guidelines

> Coding Guidelines define the engineering standards used throughout the Pairly project.

The goal is to keep the codebase consistent, maintainable and easy to understand regardless of who contributes to the
project.

---

# General Principles

- Write code for humans first, computers second.
- Prefer readability over cleverness.
- Keep classes and methods focused on a single responsibility.
- Avoid premature optimization.
- Follow the Boy Scout Rule: leave the code cleaner than you found it.

---

# Technology Stack

| Technology  | Version       |
|-------------|---------------|
| Java        | 25            |
| Spring Boot | 4.x           |
| Gradle      | Latest Stable |
| PostgreSQL  | Latest Stable |
| Docker      | Latest Stable |
| Redis       | Latest Stable |

---

# Project Structure

- Follow Package by Feature architecture.
- Avoid Package by Layer.
- Keep related classes together.
- Each feature should be self-contained whenever possible.

Example:

```
timeline/
    TimelineController
    TimelineService
    TimelineRepository
    TimelineMapper
    TimelineDto
```

---

# Naming

## Classes

- PascalCase
- Nouns for domain objects.
- No `@Data` from Lombok
- Services end with `Service`.
- Controllers end with `Controller`.
- Repositories end with `Repository`.
- No magic numbers or strings
- Use Clock instead of `LocalDateTime.now()`

## Methods

- camelCase
- Use verbs.

Examples:

```
createMemory()

findTimeline()

updateRelationship()

deleteEvent()
```

---

# Dependency Injection

- Use constructor injection only.
- Field injection is forbidden expect tests.

✅

```
@RequiredArgsConstructor
class MemoryService {

    private final MemoryRepository repository;

}
```

❌

```
@Autowired
private MemoryRepository repository;
```

---

# DTO

- Never expose JPA entities outside the domain layer.
- Use DTOs for API communication.
- Prefer Java Records for immutable DTOs.

---

# Validation

- Use Bean Validation.
- Validate input as early as possible.
- Never trust client input.

---

# Exceptions

- Use domain-specific exceptions.
- Never catch Exception.
- Return RFC7807 Problem Details.

---

# Logging

- Log meaningful business events.
- Never log passwords, tokens or secrets.
- Avoid excessive logging.

---

# Testing

- Every new feature should include tests.
- Unit tests are mandatory.
- Integration tests for critical paths.
- Test names should describe behaviour.

Example:

```
shouldCreateMemory()

shouldRejectInvalidRelationship()

shouldReturn404WhenMemoryDoesNotExist()
```

---

# Formatting

- Spotless is mandatory.
- Code must be automatically formatted before commit.
- No formatting-only commits.

---

# Comments

- Prefer expressive code to comments.
- Explain "why", never "what".
- Remove outdated comments immediately.

---

# Git

- Follow Conventional Commits.
- Work on feature branches.
- Every change should go through a Pull Request.

---

# Pull Requests

Every Pull Request should:

- have a meaningful title;
- describe the purpose of the change;
- remain focused on a single concern;
- satisfy the Definition of Done.

---

# Quality Gates

Code cannot be merged unless:

- All tests pass.
- CI pipeline succeeds.
- Spotless passes.
- Build succeeds.
- Definition of Done is satisfied.

---

# Continuous Improvement

These guidelines are a living document.

Whenever the team identifies a better practice, this document should be updated.