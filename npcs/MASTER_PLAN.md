# ELDORIA WORLD — CANON NPC MASTER PLAN

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Scope

Master planning layer for Canon NPC. Dokumen ini tidak membuat NPC individual.

## 2. Authority Chain

```text
CANON GEOGRAPHY
↓
POPULATION MODEL
↓
GOVERNANCE / FACTION CONTEXT
↓
FACTION CANON REGISTRY
↓
NPC COVERAGE MATRIX
↓
INDIVIDUAL CANON NPC
```

## 3. Coverage Requirements

- Empire ≥25
- setiap Kingdom ≥10
- setiap City ≥5
- setiap Settlement ≥3

Total kebutuhan adalah ≥295 **scope coverage**, bukan 295 NPC unik.

## 4. Faction Dependency

NPC menggunakan faction Canon dari `factions/CANON_REGISTRY.md` bila relevan. Faction tidak otomatis memberikan membership, rank, authority, access, resources, reputation, knowledge, atau loyalty.

## 5. Design Rules

1. NPC bukan quota filler.
2. NPC harus memiliki fungsi/kepentingan material dan agency.
3. Race wajib berasal dari Race Canon aktif.
4. Dynamic NPC tidak otomatis menjadi Canon.
5. Canon NPC tidak boleh duplicate.
6. Identity/lore Canon terpisah dari Current State.
7. Knowledge boundary wajib jelas.

## 6. Individual NPC Schema

```text
NPC_ID
NPC_CLASS: CANON
NAME
RACE_CANON_ID
ROLE / TYPE
SETTLEMENT_ID
CITY_ID
REGION_ID
KINGDOM_ID
EMPIRE_ID
BACKGROUND
ORIGIN
GOALS
CORE_RELATIONSHIPS
CAPABILITIES
KNOWLEDGE_BOUNDARY
FACTION
CANON_ORIGIN
CANON_STATUS
```

## 7. Creation Order

```text
EMPIRE → KINGDOM → CITY → SETTLEMENT
↓
FACTION ASSIGNMENT
↓
NPC IDENTITY
↓
RELATIONSHIPS / GOALS / CAPABILITIES
↓
VALIDATION
↓
PERSISTENT RECORD
```

## 8. Validation Gate

```text
[ ] Geography authoritative
[ ] Population context available
[ ] Governance context available
[ ] Faction context available
[ ] Race Canon available
[ ] Coverage need justified
[ ] Role is not quota filler
[ ] No duplicate
[ ] Knowledge boundary defined
[ ] Origin traceable
```

## 9. Current Status

```text
EMPIRE TARGET: ≥25
KINGDOM TARGET: ≥10 each × 5
CITY TARGET: ≥5 each × 20
SETTLEMENT TARGET: ≥3 each × 40
TOTAL SCOPE COVERAGE TARGET: ≥295

NPC COVERAGE MATRIX: npcs/COVERAGE_MATRIX_v1_0.md
INDIVIDUAL CANON NPC CREATED BY THIS PLAN: 0
```

> Canon NPC dibuat karena penting bagi dunia; Coverage Matrix mengatur pemerataan kebutuhan, bukan menciptakan alasan palsu untuk NPC.
