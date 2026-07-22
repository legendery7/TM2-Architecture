# ER Overview

Logical persistence sketch (not a full vendor schema dump). Names illustrate ownership boundaries.

```mermaid
erDiagram
  TEAM ||--o{ TEAM_MEMBER : has
  TEAM ||--o{ TOWN : owns
  TOWN ||--o{ CLAIM : claims
  TOWN ||--o{ BUILDING : builds
  TOWN ||--o{ WAREHOUSE_SLOT : stores
  TEAM ||--o{ ECONOMY_LEDGER : records
  BUILDING ||--o{ PRODUCTION_JOB : runs
  TEAM ||--o{ AUCTION_LOT : lists

  TEAM {
    long id PK
    string name
    int reputation
  }
  TEAM_MEMBER {
    long team_id FK
    uuid player_id
    string role
  }
  TOWN {
    long id PK
    long team_id FK
    string status
  }
  CLAIM {
    long town_id FK
    int chunk_x
    int chunk_z
  }
  BUILDING {
    long id PK
    long town_id FK
    string type
    string state
  }
  WAREHOUSE_SLOT {
    long town_id FK
    string item_key
    int amount
  }
  ECONOMY_LEDGER {
    long id PK
    long team_id FK
    string reason
    long delta
  }
  PRODUCTION_JOB {
    long building_id FK
    string profile
    string status
  }
  AUCTION_LOT {
    long id PK
    long team_id FK
    string item_key
    long price
  }
```

## Notes

- Reputation and milestone buildings drive unlocks (HQ → town hall → city).
- Storage access follows priority: city warehouse if ready, else HQ mini-storage.
- Exact table names and columns evolve; this diagram communicates **relationships**, not a frozen DDL.
