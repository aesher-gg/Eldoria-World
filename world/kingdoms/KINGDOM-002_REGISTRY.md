# ELDORIA WORLD — KINGDOM-002 REGISTRY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-002 — Kerajaan Brannor
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi identitas, parent hierarchy, geography reference, population model, dan Canon boundaries Kingdom-002.

## 1. Kingdom Identity
```text
KINGDOM_ID: KINGDOM-002
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Brannor
TYPE: Kerajaan Highland-Mineral
CAPITAL: Durnhaven
CONTINENT: Benua Utama Eldoria
STATUS: ACTIVE CANON
BOUNDARY: Wilayah dataran tinggi dan pegunungan di luar heartland Valedorn; detail batas fisik dibangun melalui Region Canon
CURRENT_STATE: Stabil secara administratif; kondisi politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang sebagai pusat dataran tinggi, sumber daya mineral, dan jalur lintas pegunungan; detail pendirian = ???
HISTORY: ???
```

## 2. Kingdom Function

Brannor merupakan kerajaan dataran tinggi dan pegunungan di bawah Kekaisaran Valthera. Fungsi geografis dan ekonominya berpusat pada:

- dataran tinggi dan pegunungan,
- sumber daya mineral,
- pertambangan dan pengolahan bahan mentah,
- jalur lintas pegunungan,
- perdagangan lintas wilayah,
- transportasi frontier.

Karakter regional Canon: **keras, mandiri, strategis, dan berorientasi sumber daya**.

Fungsi tersebut tidak menentukan ras, Class, Skill, Faction, kepribadian, moralitas, atau nasib individu.

## 3. Administrative Hierarchy

```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-002 — Kerajaan Brannor
    ├── REGION-005 — Pegunungan Durn
    │   └── CITY-005 — Durnhaven
    │       ├── SETTLEMENT-009 — Stonepass
    │       └── SETTLEMENT-010 — Highmere
    ├── REGION-006 — Lembah Kharven
    │   └── CITY-006 — Kharhold
    │       ├── SETTLEMENT-011 — Valecrest
    │       └── SETTLEMENT-012 — Ironbrook
    ├── REGION-007 — Punggung Besi
    │   └── CITY-007 — Ferren
    │       ├── SETTLEMENT-013 — Blackridge
    │       └── SETTLEMENT-014 — Redstone
    └── REGION-008 — Perbatasan Frostpine
        └── CITY-008 — Frostwatch
            ├── SETTLEMENT-015 — Pinewatch
            └── SETTLEMENT-016 — Coldmere
```

## 4. Region Registry

```text
REGION-005 → Pegunungan Durn → KINGDOM-002
REGION-006 → Lembah Kharven → KINGDOM-002
REGION-007 → Punggung Besi → KINGDOM-002
REGION-008 → Perbatasan Frostpine → KINGDOM-002
```

Detail lengkap Region → City → Settlement → Population Model berada di:

`world/kingdoms/KINGDOM-002_GEOGRAPHY.md`

## 5. City Registry

```text
CITY-005 → Durnhaven → REGION-005 → KINGDOM-002
CITY-006 → Kharhold → REGION-006 → KINGDOM-002
CITY-007 → Ferren → REGION-007 → KINGDOM-002
CITY-008 → Frostwatch → REGION-008 → KINGDOM-002
```

## 6. Settlement Registry

```text
SETTLEMENT-009 → Stonepass → CITY-005 → REGION-005 → KINGDOM-002
SETTLEMENT-010 → Highmere → CITY-005 → REGION-005 → KINGDOM-002
SETTLEMENT-011 → Valecrest → CITY-006 → REGION-006 → KINGDOM-002
SETTLEMENT-012 → Ironbrook → CITY-006 → REGION-006 → KINGDOM-002
SETTLEMENT-013 → Blackridge → CITY-007 → REGION-007 → KINGDOM-002
SETTLEMENT-014 → Redstone → CITY-007 → REGION-007 → KINGDOM-002
SETTLEMENT-015 → Pinewatch → CITY-008 → REGION-008 → KINGDOM-002
SETTLEMENT-016 → Coldmere → CITY-008 → REGION-008 → KINGDOM-002
```

## 7. Population Model

```text
KINGDOM_ID: KINGDOM-002
POPULATION_MODEL_ID: POP-BRA-001
TOTAL_POPULATION: RANGE 450,000–700,000
URBANIZATION: LOW-MODERATE
PRIMARY_POPULATION_BASE: MINING + HIGHLAND AGRICULTURE + TRADE + FORESTRY
SEASONAL_MOBILITY: MODERATE-HIGH
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
EXACT_OCCUPATIONAL_PERCENTAGES: ???
STATUS: ACTIVE
```

Regional distribution model:

```text
REGION-005 → 20–25%
REGION-006 → 25–30%
REGION-007 → 30–35%
REGION-008 → 15–20%
```

Population is represented as an aggregate model. It does not require an individual record for every inhabitant.

## 8. Race Boundary

- Only active Race Canon IDs from `races/CANON_REGISTRY.md` may be used.
- Exact race percentages remain `???` until separately Canonized.
- No settlement is race-exclusive unless explicitly established by Admin Canon.
- Race does not determine Class, profession, Faction, personality, morality, loyalty, or outcome.
- Migration involving race must be evidence-based and compatible with Population Model and world history.

## 9. Canon Geography Reference

The detailed geography remains authoritative for the Region → City → Settlement → Population structure:

`world/kingdoms/KINGDOM-002_GEOGRAPHY.md`

This registry does not replace or duplicate detailed Geography Canon. It establishes Kingdom-level registry relationships and references the geography file.

## 10. Governance / Faction Boundary

```text
GOVERNANCE_SYSTEM: Kerajaan otonom di bawah hukum kekaisaran
RULER: ???
ROYAL_ADMINISTRATION: ???
MAJOR_FACTIONS: ???
MILITARY_STRUCTURE: ???
LEGAL_STRUCTURE: ???
ECONOMIC_POLICY: ???
DIPLOMATIC_RELATIONS: ???
```

Unresolved governance/faction values remain `???`; AI GM must not invent them as existing Canon.

## 11. Canon NPC Gate

Kingdom-002 satisfies the geography and population prerequisites for Canon NPC construction.

```text
KINGDOM REGISTRY
→ GEOGRAPHY
→ POPULATION MODEL
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum Canon NPC coverage for Kingdom-002:

```text
DESA / SETTLEMENT → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KINGDOM → ≥ 10 Canon NPC
```

No Canon NPC is defined by this registry.

## 12. Integrity Rules

1. `KINGDOM-002` must always resolve to `EMPIRE-001`.
2. Every Region must resolve to `KINGDOM-002`.
3. Every City must resolve to both a valid Region and `KINGDOM-002`.
4. Every Settlement must resolve to both a valid City/Region and `KINGDOM-002`.
5. Population Model `POP-BRA-001` belongs to `KINGDOM-002`.
6. Geography detail remains in `KINGDOM-002_GEOGRAPHY.md`.
7. Unknown information is represented by `???`, never by an invented default.
8. Canon NPC identity must not be created by AI GM without Admin Canon authorization.
9. Changes to Kingdom identity or parent hierarchy require Admin authority.

## 13. Canon Status

```text
KINGDOM_REGISTRY: COMPLETE
KINGDOM_IDENTITY: CANON
PARENT_EMPIRE: VERIFIED
REGION_REFERENCE: VERIFIED
CITY_REFERENCE: VERIFIED
SETTLEMENT_REFERENCE: VERIFIED
POPULATION_MODEL: VERIFIED
GEOGRAPHY_FILE: EXISTING / NORMALIZED
FACTION_GOVERNANCE_CONTEXT: PENDING
CANON_NPC: PENDING
```
