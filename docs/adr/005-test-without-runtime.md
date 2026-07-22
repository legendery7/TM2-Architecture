# ADR-005: Test domain logic without booting Paper

## Status

Accepted

## Context

Full server boot is slow and brittle for unit feedback.

## Decision

Keep pure rules testable with JUnit and Mockito. Mock Paper types. Do not re-test the runtime or JDBC drivers.

## Consequences

Faster feedback on combat, production, and reputation rules. Integration tests reserved for pipelines that need them.
