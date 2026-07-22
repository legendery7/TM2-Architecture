# C4 Context

System context for TM2.

![Context diagram](assets/tm2-c4-context.png)

```mermaid
flowchart TB
  player[Player]
  admin[Operator]
  paper[Paper Runtime]
  tm2[TM2 Platform]
  mysql[(MySQL)]
  we[WorldEdit / FAWE]
  papi[PlaceholderAPI]
  bluemap[BlueMap]

  player --> paper
  admin --> tm2
  paper --> tm2
  tm2 --> mysql
  tm2 --> we
  tm2 --> papi
  tm2 --> bluemap
```

## Actors

| Actor | Intent |
|-------|--------|
| Player | Participates in multiplayer sessions, builds, progresses with a team |
| Operator | Configures rules, moderates, operates the deployment |

## External systems

| System | Role |
|--------|------|
| Paper Runtime | Real-time simulation and networking host |
| MySQL | Primary persistent store |
| WorldEdit / FAWE | Schematic and structural world operations |
| PlaceholderAPI | Text placeholders for UI/integrations |
| BlueMap | Optional map visualization |
