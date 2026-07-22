# ADR-001: Layered modules over a utility plugin

## Status

Accepted

## Context

Early server plugins often collapse into a single pile of commands and listeners. That style does not scale when towns, economy, production, and combat coexist.

## Decision

Split by domain package and enforce command → service → repository → DB layering.

## Consequences

More files and ceremony. Better testability and change isolation as the platform grows.
