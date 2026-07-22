# ADR-004: Warehouse storage priority

## Status

Accepted

## Context

Multiple storage locations (HQ mini-storage vs city warehouse) confuse automation and commands.

## Decision

Single priority rule: ready warehouse if present; else HQ storage; else empty state for workers.

## Consequences

Predictable automation. Requires migration logic when towns upgrade.
