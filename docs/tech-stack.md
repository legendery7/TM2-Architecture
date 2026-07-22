# Technology Stack

| Layer | Choice | Role |
|-------|--------|------|
| Language | Java 21 | Primary implementation language |
| Runtime platform | Paper API | Real-time multiplayer host |
| Build | Maven | Compile, test, shade |
| DB access | HikariCP + MySQL connector | Pooled persistence |
| Test | JUnit 5, Mockito | Domain and service tests |
| World edit | WorldEdit / FAWE (provided) | Schematics & structural ops |
| Integrations | PlaceholderAPI, BlueMap API (provided) | UI/map ecosystem hooks |

Minecraft-related APIs are **platform dependencies**, not the product identity. The product is the modular multiplayer domain system.
