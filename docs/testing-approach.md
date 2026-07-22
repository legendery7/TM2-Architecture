# Testing Approach

Summary of the testing strategy used for TM2 domain logic.

## Philosophy

Mirror the production layering:

| Layer | Test focus |
|-------|------------|
| Domain services | Business rules, formulas, validations |
| Repositories | Persistence contracts (where valuable) |
| Commands / UI | Thin — prefer testing services they call |
| Paper API | Mock — do not re-test the runtime |

## Tools

- JUnit 5
- Mockito
- Maven Surefire

## Patterns

1. **Pure logic tests** — reputation, formatting, policy decisions with no Bukkit objects  
2. **Service + mocks** — placement/economy services with mocked repositories  
3. **Config-driven tests** — production profile registries loading YAML from test resources  
4. **Pipeline tests** — production/worker flows where sequencing matters  

## Explicit non-goals

- Paper/Spigot internals
- Raw JDBC driver behavior
- Third-party library internals (test only wrappers)

## Naming

- Class: `ClassUnderTestTest`
- Method: `scenario_expectedResult` (or `@DisplayName` for readability)
