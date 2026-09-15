# ELDORIA WORLD — CANON NPC MASTER PLAN

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Purpose:** Menetapkan arsitektur, prioritas, dan coverage plan Canon NPC sebelum pembuatan record NPC individual.

## 1. Scope

Dokumen ini adalah master planning layer untuk Canon NPC. Dokumen ini tidak membuat NPC individual.

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

NPC tidak boleh digunakan untuk mengisi kekosongan geography, governance, atau faction.

## 3. Coverage Requirements

| Scope | Minimum Canon NPC |
|---|---:|
| Empire | ≥25 |
| Setiap Kingdom | ≥10 |
| Setiap City | ≥5 |
| Setiap Settlement | ≥3 |

Coverage adalah scope relevance, bukan kewajiban membuat jumlah NPC unik yang sama dengan total coverage. Target total scope coverage ditetapkan dalam `npcs/COVERAGE_MATRIX_v1.0.md`.

## 4. Faction Dependency

NPC harus menggunakan konteks faction dari `factions/CANON_REGISTRY.md` bila faction relevan. Faction tidak otomatis memberikan membership, rank, authority, access, resources, reputation, knowledge, atau loyalty kepada NPC.

## 5. Design Rules

1. Tidak ada NPC yang dibuat hanya untuk memenuhi angka coverage.
2. NPC harus memiliki fungsi atau kepentingan material.
3. NPC harus memiliki agency sendiri.
4. Race wajib menggunakan `RACE_CANON_ID` aktif dari Race Registry.
5. Race tidak menentukan morality, personality, class, faction, atau outcome secara otomatis.
6. Canon NPC tidak boleh duplicate dari Canon NPC atau Persistent Dynamic NPC yang sudah ada.
7. Dynamic NPC tidak otomatis menjadi Canon NPC.
8. Identity/lore Canon tidak berubah hanya karena narrative runtime.
9. Current state berada pada state layer terpisah.
10. Knowledge boundary harus eksplisit.

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

Field yang memang belum ditetapkan tetap `???`.

## 7. Creation Order

```text
EMPIRE CONTEXT
↓
KINGDOM CONTEXT
↓
CITY CONTEXT
↓
SETTLEMENT CONTEXT
↓
FACTION ASSIGNMENT
↓
NPC IDENTITY
↓
RELATIONSHIPS / GOALS / CAPABILITIES
↓
CANON VALIDATION
↓
PERSISTENT RECORD
```

## 8. Validation Gate

Sebelum individual NPC creation:

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

## 9. Current Planning Status

```text
EMPIRE COVERAGE TARGET: ≥25
KINGDOM COVERAGE TARGET: ≥10 each × 5
CITY COVERAGE TARGET: ≥5 each × 20
SETTLEMENT COVERAGE TARGET: ≥3 each × 40
TOTAL SCOPE COVERAGE TARGET: ≥295

NPC COVERAGE MATRIX: npcs/COVERAGE_MATRIX_v1.0.md
INDIVIDUAL CANON NPC CREATED BY THIS PLAN: 0
```

## 10. Final Principle

> **Canon NPC dibuat karena mereka penting bagi dunia; Coverage Matrix mengatur pemerataan dan validasi kebutuhan, bukan menciptakan alasan palsu untuk keberadaan NPC.**
