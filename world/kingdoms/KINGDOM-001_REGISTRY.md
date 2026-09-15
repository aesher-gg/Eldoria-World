# ELDORIA WORLD — KINGDOM-001 REGISTRY

> **Authority:** Admin
> **Canon:** Admin Canon v1.0
> **Kingdom:** KINGDOM-001 — Kerajaan Valedorn
> **Purpose:** Registry resmi identitas, parent hierarchy, geography reference, population model, dan Canon boundaries Kingdom-001.

## 1. Kingdom Identity

```text
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Valedorn
TYPE: Kerajaan Heartland Agraris-Riverine
CAPITAL: Varenhold
CONTINENT: Benua Utama Eldoria
STATUS: ACTIVE CANON
BOUNDARY: Heartland tengah Valthera; detail batas fisik dibangun melalui Region Canon
CURRENT_STATE: Stabil; detail politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang sebagai kerajaan agraris dan jalur sungai yang kemudian berada di bawah struktur Kekaisaran Valthera; detail sejarah pendirian = ???
HISTORY: ???
```

## 2. Kingdom Function

Valedorn merupakan salah satu kerajaan utama di bawah Kekaisaran Valthera. Fungsi geografis dan ekonominya berpusat pada:

- heartland pangan,
- pertanian skala regional,
- perdagangan darat,
- koridor sungai,
- distribusi hasil pertanian,
- konektivitas antarkawasan.

Karakter regional Canon: **subur, produktif, terhubung, dan pragmatis**.

Fungsi tersebut tidak menentukan ras, Class, Skill, Faction, kepribadian, moralitas, atau nasib individu.

## 3. Administrative Hierarchy

```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-001 — Kerajaan Valedorn
    ├── REGION-001 — Cekungan Varenhold
    │   └── CITY-001 — Varenhold
    │       ├── SETTLEMENT-001 — Bellmere
    │       └── SETTLEMENT-002 — Oakrest
    ├── REGION-002 — Koridor Sungai Averen
    │   └── CITY-002 — Averen
    │       ├── SETTLEMENT-003 — Rivergate
    │       └── SETTLEMENT-004 — Millhaven
    ├── REGION-003 — Dataran Ladang Emas
    │   └── CITY-003 — Goldmere
    │       ├── SETTLEMENT-005 — Wheatcross
    │       └── SETTLEMENT-006 — Sunfield
    └── REGION-004 — Perbatasan Hutan Thorn
        └── CITY-004 — Thornwick
            ├── SETTLEMENT-007 — Briarford
            └── SETTLEMENT-008 — Greenhollow
```

## 4. Region Registry

```text
REGION-001 → Cekungan Varenhold → KINGDOM-001
REGION-002 → Koridor Sungai Averen → KINGDOM-001
REGION-003 → Dataran Ladang Emas → KINGDOM-001
REGION-004 → Perbatasan Hutan Thorn → KINGDOM-001
```

Detail lengkap Region → City → Settlement → Population Model berada di:

`world/kingdoms/KINGDOM-001_GEOGRAPHY.md`

## 5. City Registry

```text
CITY-001 → Varenhold → REGION-001 → KINGDOM-001
CITY-002 → Averen → REGION-002 → KINGDOM-001
CITY-003 → Goldmere → REGION-003 → KINGDOM-001
CITY-004 → Thornwick → REGION-004 → KINGDOM-001
```

## 6. Settlement Registry

```text
SETTLEMENT-001 → Bellmere → CITY-001 → REGION-001 → KINGDOM-001
SETTLEMENT-002 → Oakrest → CITY-001 → REGION-001 → KINGDOM-001
SETTLEMENT-003 → Rivergate → CITY-002 → REGION-002 → KINGDOM-001
SETTLEMENT-004 → Millhaven → CITY-002 → REGION-002 → KINGDOM-001
SETTLEMENT-005 → Wheatcross → CITY-003 → REGION-003 → KINGDOM-001
SETTLEMENT-006 → Sunfield → CITY-003 → REGION-003 → KINGDOM-001
SETTLEMENT-007 → Briarford → CITY-004 → REGION-004 → KINGDOM-001
SETTLEMENT-008 → Greenhollow → CITY-004 → REGION-004 → KINGDOM-001
```

## 7. Population Model

```text
POPULATION_MODEL_ID: POP-VAL-001
TOTAL_POPULATION: RANGE 650,000–900,000
URBANIZATION: MODERATE
PRIMARY_POPULATION_BASE: AGRICULTURAL + RIVERINE
SEASONAL_MOBILITY: MODERATE
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
EXACT_OCCUPATIONAL_PERCENTAGES: ???
STATUS: ACTIVE
```

Regional distribution model:

```text
REGION-001 → 20–25%
REGION-002 → 20–25%
REGION-003 → 35–40%
REGION-004 → 15–20%
```

Population is represented as an aggregate model. It does not require an individual record for every inhabitant.

## 8. Race Boundary

- Only active Race Canon IDs from `races/CANON_REGISTRY.md` may be used.
- Exact race percentages remain `???` until separately Canonized.
- No settlement is race-exclusive unless explicitly established by Admin Canon.
- Race does not determine Class, profession, Faction, personality, morality, loyalty, or outcome.
- Migration involving race must be evidence-based and compatible with Population Model and world history.

## 9. Canon Geography Reference

The existing detailed geography file remains authoritative for the Region → City → Settlement → Population structure:

`world/kingdoms/KINGDOM-001_GEOGRAPHY.md`

This registry does **not** replace, rewrite, or duplicate the detailed Geography Canon. It establishes the Kingdom-level registry and references the existing geography file.

## 10. Governance / Faction Boundary

```text
GOVERNANCE_SYSTEM: ???
RULER: ???
ROYAL_ADMINISTRATION: ???
MAJOR_FACTIONS: ???
MILITARY_STRUCTURE: ???
LEGAL_STRUCTURE: ???
ECONOMIC_POLICY: ???
DIPLOMATIC_RELATIONS: ???
```

These values remain unresolved until the appropriate Faction/Governance Canon is established. AI GM must not invent them as existing Canon.

## 11. Canon NPC Gate

Kingdom-001 satisfies the geography and population prerequisites for Canon NPC construction.

```text
KINGDOM REGISTRY
→ GEOGRAPHY
→ POPULATION MODEL
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum Canon NPC coverage for Kingdom-001:

```text
DESA / SETTLEMENT → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KINGDOM → ≥ 10 Canon NPC
```

No Canon NPC is defined by this registry.

## 12. Integrity Rules

1. `KINGDOM-001` must always resolve to `EMPIRE-001`.
2. Every Region must resolve to `KINGDOM-001`.
3. Every City must resolve to both a valid Region and `KINGDOM-001`.
4. Every Settlement must resolve to both a valid City/Region and `KINGDOM-001`.
5. Population Model `POP-VAL-001` belongs to `KINGDOM-001`.
6. Geography detail remains in `KINGDOM-001_GEOGRAPHY.md`.
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
GEOGRAPHY_FILE: EXISTING / UNMODIFIED
FACTION_GOVERNANCE_CONTEXT: PENDING
CANON_NPC: PENDING
```

> **Admin Canon Principle:** Registry menetapkan identitas dan hubungan administratif Kingdom. Detail geography tetap berada pada file Geography khusus; detail governance/faction dan Canon NPC dibangun pada tahap berikutnya.