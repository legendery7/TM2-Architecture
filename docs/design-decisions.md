# Design Decisions

Selected architectural decisions for TM2. Written for engineering review.

## ADR-001 — Layered modules over a single utility plugin

**Context:** Early plugins often become a single class pile of commands and listeners.

**Decision:** Split by domain package (`town`, `building`, `economy`, …) and enforce command → service → repository → DB layering.

**Consequences:** More files and ceremony; much better testability and long-term change isolation.

## ADR-002 — Config-driven building and production definitions

**Context:** Balance and content change faster than code.

**Decision:** Represent building types, production profiles, and reputation gates primarily in YAML; code interprets rules.

**Consequences:** Designers can iterate on content; validation and schema discipline become mandatory.

## ADR-003 — Reputation milestones as progression spine

**Context:** Need a comprehensible player journey from temporary capital rent to city-scale systems.

**Decision:** Use landmark buildings + reputation thresholds (HQ → town hall → city) as the spine; unlock claims, menus, and warehouse by milestone.

**Consequences:** Clear UX story; requires careful rules for demolition and reputation rollback.

## ADR-004 — Warehouse priority over fragmented storage

**Context:** Multiple storage locations (HQ mini-storage vs city warehouse) confuse workers and commands.

**Decision:** Single priority rule: warehouse if ready, else HQ storage, else empty state.

**Consequences:** Predictable automation; migration logic when towns upgrade.

## ADR-005 — Test domain logic without booting Paper

**Context:** Full server boot is slow and brittle for unit feedback.

**Decision:** Keep pure rules testable with JUnit/Mockito; mock Paper types; do not re-test the runtime.

**Consequences:** Faster feedback on combat/production/reputation rules; integration tests reserved for pipelines that need them.

## ADR-006 — Keep implementation private; publish architecture

**Context:** The platform is proprietary / not ready for open source, but the engineering story matters for collaboration and interviews.

**Decision:** Publish architecture, diagrams, and design rationale in this repository without source.

**Consequences:** Transparency of thinking without exposing implementation or operational secrets.
