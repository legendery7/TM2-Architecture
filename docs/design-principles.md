# Design Principles

Principles that guide TM2 design. Not slogans — constraints used when adding features.

## 1. Design before code

Progression rules, storage priority, and unlock milestones are written down before UI and edge cases expand. Design docs are part of the system, not an afterthought.

## 2. Domain modules over feature dumps

New behavior belongs in a domain module (`town`, `building`, `economy`, …). Cross-cutting utilities stay thin. A “god plugin class” is treated as technical debt.

## 3. Layering

```
Command / Listener → Service → Repository → Database
```

Commands orchestrate. Services own rules. Repositories own persistence. This keeps domain logic testable without booting the game runtime.

## 4. Config for content, code for invariants

Building types, production profiles, and reputation gates live in configuration where possible. Code enforces invariants and workflows that must stay consistent.

## 5. Prefer explicit trade-offs

Every major choice should answer: what becomes easier, what becomes harder, and what we refuse to support. See [ADRs](adr/README.md).

## 6. Test the rules that change behavior

Reputation math, combat policy, production profiles, and placement validation must be unit-testable. Do not re-test the host runtime.
