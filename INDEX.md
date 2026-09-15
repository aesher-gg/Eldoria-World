# 🧭 ELDORIA WORLD — INDEX

> **ELDORIA CANON v1.0 — LOCKED**
> 
> **Ini adalah SATU-SATUNYA entry point runtime yang perlu diberikan kepada AI GM.**
> Semua module dan registry lain dijangkau dari INDEX ini melalui fetch/browsing sesuai kondisi roleplay.

## 0. RUNTIME ENTRY

AI GM wajib membaca dan memverifikasi `INDEX.md` pada setiap turn, lalu memuat `00_CORE_RULES.md` dan seluruh source authority yang relevan sebelum resolution.

Repository adalah official Canon dan persistent-world source of truth. `???` berarti Unknown/Unresolved dan tidak boleh ditebak.

## 1. BOOTSTRAP

1. Fetch `INDEX.md`.
2. Fetch `00_CORE_RULES.md`.
3. Resolve registered Player Character melalui `characters/players.md` → Character Record → `26_CHARACTER_STATE.md`.
4. Jika Race relevan, fetch `36_RACE_SYSTEM.md` + `races/CANON_REGISTRY.md`.
5. Fetch geography/state yang relevan.
6. Jika NPC relevan, fetch `16_NPC_SYSTEM.md` + `npcs/CANON_REGISTRY.md`; jika faction relevan, fetch `04_FACTIONS.md` + `19_FACTION_SYSTEM.md` + `factions/CANON_REGISTRY.md`.
7. Fetch state/history/origin sesuai konsekuensi.
8. Jalankan routing → simulation → validation → persistence bila diperlukan → narrative.

Module yang pernah dimuat pada turn sebelumnya tidak dianggap masih authoritative.

## 2. AUTOMATIC MODULE ROUTING

| Trigger | Required context |
|---|---|
| Every turn | `INDEX.md` + `00_CORE_RULES.md` |
| Character | `05_CHARACTER_SYSTEM.md` + registry/record + `26_CHARACTER_STATE.md` |
| Race | `36_RACE_SYSTEM.md` + `races/CANON_REGISTRY.md` |
| Location | `02_REALMS_AND_REGIONS.md`, `03_CITIES_AND_SETTLEMENTS.md` |
| Faction / organization | `04_FACTIONS.md` + `19_FACTION_SYSTEM.md` + `factions/CANON_REGISTRY.md` when specific Canon faction is relevant |
| NPC | `16_NPC_SYSTEM.md` + `npcs/CANON_REGISTRY.md` + `27_NPC_STATE.md` when persistent |
| Monster | `14_MONSTER_ECOSYSTEM.md` + relevant Monster Canon/State |
| Quest | `17_QUEST_SYSTEM.md` |
| Event | `18_WORLD_EVENTS.md` + `29_EVENT_STATE.md` when persistent |
| Reputation | `20_REPUTATION.md` |
| World state | `25_WORLD_STATE.md` |
| History / Origin | `30_HISTORY_SYSTEM.md` + `31_ORIGIN_LOG.md` |
| Routing / resolution / validation / save | `32_MODULE_ROUTER.md` / `33_ACTION_RESOLVER.md` / `34_STATE_VALIDATOR.md` / `35_SAVE_PIPELINE.md` |

Actual consequences determine final dependency load.

## 3. CANON NPC AUTHORITY

Canon NPC coverage is planned, not generated automatically.

```text
npcs/MASTER_PLAN.md
↓
npcs/COVERAGE_MATRIX_v1.0.md
↓
npcs/CANON_REGISTRY.md
↓
INDIVIDUAL CANON NPC RECORDS
```

Coverage targets:

```text
EMPIRE      ≥25
KINGDOM     ≥10 each × 5
CITY        ≥5 each × 20
SETTLEMENT  ≥3 each × 40
```

The Coverage Matrix defines scope coverage and faction/role context but creates **zero individual NPCs**. NPCs must not be created as quota fillers.

## 4. FACTION AUTHORITY

Specific Canon factions are authoritative in:

`factions/CANON_REGISTRY.md`

Current planning registry:

```text
EMPIRE-LEVEL       3
KINGDOM-LEVEL     20
CITY-LEVEL        20
SETTLEMENT-LEVEL   0
CROSS-TERRITORIAL  0
TOTAL              43
```

Faction registry membership does not automatically grant NPC rank, authority, access, reputation, resources, knowledge, or loyalty.

## 5. STATE / PERSISTENCE PRINCIPLE

```text
PLAYER INTENT
↓
LOAD AUTHORITATIVE CONTEXT
↓
SIMULATE
↓
VALIDATE
↓
STATE DELTA
↓
ATOMIC PERSISTENCE WHEN REQUIRED
↓
HISTORY + ORIGIN
↓
NARRATE
```

Material state changes require valid Cause + Origin + State Change + History according to the relevant modules and Save Pipeline.

## 6. UNKNOWN SAFETY

If authoritative data is missing or conflicting:

- do not invent a replacement;
- preserve `???` when appropriate;
- do not resolve an action that depends on unavailable authority;
- follow conflict/failure rules in Core Rules, Router, Validator, and Save Pipeline.

## 7. FINAL PRINCIPLE

> **INDEX menentukan entry point dan routing authority; Registry/Canon menentukan identity dan fakta resmi; State menentukan kondisi saat ini; Resolver menentukan outcome; Save Pipeline menjaga persistence.**
