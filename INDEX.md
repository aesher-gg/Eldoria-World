# 🧭 ELDORIA WORLD — INDEX

> **ELDORIA CANON v1.0 — LOCKED**
>
> **SATU-SATUNYA entry point runtime AI GM.** Module, registry, state, history, dan origin dijangkau dari INDEX sesuai kondisi turn.

## 0. RUNTIME ENTRY

AI GM wajib fetch dan verifikasi `INDEX.md` pada setiap turn, lalu memuat `00_CORE_RULES.md` dan source authority yang relevan sebelum resolution.

Repository adalah official Canon/persistent-world source of truth. `???` = Unknown/Unresolved dan tidak boleh ditebak.

## 1. BOOTSTRAP

1. Fetch `INDEX.md`.
2. Fetch `00_CORE_RULES.md`.
3. Resolve registered Player Character melalui registry → Character Record → `26_CHARACTER_STATE.md`.
4. Jika Race relevan, fetch `36_RACE_SYSTEM.md` + `races/CANON_REGISTRY.md`.
5. Fetch geography/state yang relevan.
6. Jika NPC relevan, fetch `16_NPC_SYSTEM.md` + `npcs/CANON_REGISTRY.md`.
7. Jika faction relevan, fetch `04_FACTIONS.md` + `19_FACTION_SYSTEM.md` + `factions/CANON_REGISTRY.md`.
8. Jika law, authority, succession, title, Noble House, domain, inheritance, atau royal governance relevan, fetch `38_LAW_SYSTEM.md` + `37_NOBILITY_SYSTEM.md` bila noble context + governance/faction context + relevant Canon records.
9. Jika magic relevan, fetch `09_MAGIC_SYSTEM.md` + relevant magic identity/state.
10. Fetch state/history/origin sesuai konsekuensi.
11. Routing → simulation → validation → persistence bila diperlukan → narrative.

Module yang pernah dimuat pada turn sebelumnya tidak dianggap masih authoritative.

## 2. CANON NPC PLANNING

```text
npcs/MASTER_PLAN.md
↓
npcs/COVERAGE_MATRIX_v1_0.md
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
TOTAL       ≥295 scope coverage
```

Coverage Matrix adalah planning layer dan membuat **zero individual NPC**. Jangan membuat NPC sebagai quota filler.

## 3. FACTION AUTHORITY

Specific Canon factions berada di `factions/CANON_REGISTRY.md`. Registry tersebut menyediakan identity/context faction spesifik; Module 04 mengatur identity/framework dan Module 19 operational behavior.

Membership, rank, authority, access, reputation, resources, knowledge, dan loyalty tidak diwariskan otomatis dari faction registry.

## 4. AUTOMATIC MODULE ROUTING

| Trigger | Required context |
|---|---|
| Every turn | `INDEX.md` + `00_CORE_RULES.md` |
| Character | Character system/registry/record + `26_CHARACTER_STATE.md` |
| Race | `36_RACE_SYSTEM.md` + Race Registry |
| Location | `02_REALMS_AND_REGIONS.md`, `03_CITIES_AND_SETTLEMENTS.md` |
| Faction | `04_FACTIONS.md` + `19_FACTION_SYSTEM.md` + `factions/CANON_REGISTRY.md` bila specific faction relevan |
| Law / Authority / Succession | `38_LAW_SYSTEM.md` + `GOVERNANCE_FACTION_MASTER.md` + relevant state; `37_NOBILITY_SYSTEM.md` bila noble context |
| Nobility / Title / Noble House / Domain / Inheritance | `37_NOBILITY_SYSTEM.md` + `38_LAW_SYSTEM.md` + `GOVERNANCE_FACTION_MASTER.md` + relevant faction/NPC/state |
| Magic | `09_MAGIC_SYSTEM.md` + relevant magic identity/state |
| NPC | `16_NPC_SYSTEM.md` + `npcs/CANON_REGISTRY.md` + `27_NPC_STATE.md` bila persistent |
| Combat | `13_COMBAT.md` + relevant state |
| Trade | `11_ECONOMY.md` + relevant item/NPC/faction/state context |
| Quest | `17_QUEST_SYSTEM.md` + relevant NPC/faction/event context |
| Event | `18_WORLD_EVENTS.md` + `29_EVENT_STATE.md` bila persistent |
| Reputation | `20_REPUTATION.md` + relevant faction/NPC state |
| World state | `25_WORLD_STATE.md` |
| History / Origin | `30_HISTORY_SYSTEM.md` + `31_ORIGIN_LOG.md` |
| Routing / resolution / validation / save | `32_MODULE_ROUTER.md` / `33_ACTION_RESOLVER.md` / `34_STATE_VALIDATOR.md` / `35_SAVE_PIPELINE.md` |

Actual consequences menentukan dependency load final.

## 5. STATE / PERSISTENCE

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

Material state changes require valid Cause + Origin + State Change + History according to relevant modules.

## 6. UNKNOWN SAFETY

Jika authority hilang atau konflik tidak dapat diselesaikan:

- jangan mengarang replacement;
- pertahankan `???` bila sesuai;
- jangan resolve action yang bergantung pada authority yang tidak tersedia;
- ikuti failure/conflict rules Core Rules, Router, Validator, dan Save Pipeline.

> **INDEX menentukan entry point/routing; Registry/Canon menentukan identity/fakta resmi; Law menentukan legal authority; State menentukan kondisi saat ini; Resolver menentukan outcome; Save Pipeline menjaga persistence.**
