# C4 Container

Container view of a typical TM2 deployment.

![Container diagram](assets/tm2-c4-container.png)

```mermaid
flowchart LR
  players[Players]
  subgraph runtime [Paper Server Process]
    api[Paper API / Events]
    tm2[TM2 Domain Modules]
    cfg[YAML configs and schematics]
  end
  pool[HikariCP]
  db[(MySQL)]

  players --> api
  api --> tm2
  tm2 --> cfg
  tm2 --> pool --> db
```

## Containers

| Container | Responsibility |
|-----------|----------------|
| Paper process | Hosts networking, worlds, scheduling, plugin lifecycle |
| TM2 modules | Domain logic: towns, buildings, economy, combat, … |
| Config / schematics | Content and structural definitions |
| HikariCP + MySQL | Pooled persistence for durable state |

TM2 is loaded as a modular plugin into the Paper process. Persistence is externalized so server restarts do not discard progression state.
