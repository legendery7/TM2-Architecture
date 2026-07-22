# Module Catalog

High-level catalog of TM2 domain modules. Details evolve; this list reflects the modular decomposition of the private platform.

## Core domain

| Module | Purpose |
|--------|---------|
| `town` | Town aggregate, tech, effects, pathing helpers, cleanup |
| `building` | Building lifecycle: config, placement, preview, upgrade, workers, GUI, protection, siege hooks |
| `economy` | Economy subsystem: tax, mint, bonuses |
| `warehouse` | Shared storage semantics and inventory access rules |
| `claim` | Territory claims |
| `rent` | Capital chunk rent before permanent claims |
| `road` | Road network: build, zones, protection, snapshots, visuals |
| `production` | Production profiles and chains |
| `processing` | Resource processing pipelines |
| `combat` | Attack policies and strike resolution |
| `auction` | Auction model, commands, GUI, listeners |
| `mine` / `mineshaft` | Mining-related systems |
| `profile` | Player/team profile concerns |
| `townbank` / `townban` / `townspawn` | Banking, bans, spawn related town services |

## Platform / delivery

| Module | Purpose |
|--------|---------|
| `command` | Command API surface including admin tools |
| `config` | Configuration loading |
| `db` | Database access infrastructure |
| `lang` | Localization |
| `ui` | Action bar / map UI |
| `map` | Map-related helpers |
| `placeholder` | PlaceholderAPI bridge |
| `broadcast` / `banner` / `chat` / `title` | Communication & presentation |
| `world` | World-level rules/helpers |
| `util` | Shared utilities |
| `color` | Color/formatting helpers |

## Building subsystem (deeper)

The `building` module is intentionally large and further split, for example:

- `animation`, `barracks`, `cards`, `crafts`, `effects`
- `embassy`, `farm`, `foundation`, `hq`, `mill`, `tavern`
- `placement`, `preview`, `protection`, `removal`
- `repo`, `service`, `siege`, `spawn`, `tech`, `upgrade`, `worker`
- `fawe` integration for schematic/world-edit flows

This depth is a deliberate response to domain complexity — not a flat “god package”.
