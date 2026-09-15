# ELDORIA WORLD — KINGDOM-004 REGISTRY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-004 — Kerajaan Sylvaran
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi identitas, parent hierarchy, geography reference, population model, dan Canon boundaries Kingdom-004.

## 1. Kingdom Identity
```text
KINGDOM_ID: KINGDOM-004
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Sylvaran
TYPE: Kerajaan Forest-Border
CAPITAL: Elaris
CONTINENT: Benua Utama Eldoria
STATUS: ACTIVE CANON
BOUNDARY: Wilayah hutan luas dan perbatasan darat di bagian lain Benua Utama Eldoria; detail batas fisik dibangun melalui Region Canon
CURRENT_STATE: Stabil secara administratif; kondisi politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang dari jaringan permukiman hutan, jalur darat, dan pusat pengelolaan sumber daya hutan; detail pendirian = ???
HISTORY: ???
```

## 2. Kingdom Function
Sylvaran merupakan kerajaan hutan dan perbatasan ekologis di bawah Kekaisaran Valthera. Fungsi geografis dan ekonominya berpusat pada:

- hutan dan hasil hutan,
- pertanian berbasis lahan terbuka/clearing yang terkontrol,
- sungai hulu,
- perburuan dan pemanfaatan sumber daya hutan,
- kerajinan,
- jalur darat dan frontier ekologis.

Karakter regional Canon: **berhutan, berorientasi sumber daya, tersebar, dan frontier-sensitive**.

Fungsi tersebut tidak menentukan ras, Class, Skill, Faction, kepribadian, moralitas, atau nasib individu.

## 3. Administrative Hierarchy
```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-004 — Kerajaan Sylvaran
    ├── REGION-013 — Hutan Elaris
    │   └── CITY-013 — Elaris
    │       ├── SETTLEMENT-025 — Greenford
    │       └── SETTLEMENT-026 — Mossvale
    ├── REGION-014 — Lembah Silvan
    │   └── CITY-014 — Sylford
    │       ├── SETTLEMENT-027 — Oakmere
    │       └── SETTLEMENT-028 — Fernwatch
    ├── REGION-015 — Sungai Elden
    │   └── CITY-015 — Riverwyn
    │       ├── SETTLEMENT-029 — Brookrest
    │       └── SETTLEMENT-030 — Alderbank
    └── REGION-016 — Perbatasan Wildmere
        └── CITY-016 — Wildmere
            ├── SETTLEMENT-031 — Pinecross
            └── SETTLEMENT-032 — Thornrest
```

## 4. Region Registry
```text
REGION-013 → Hutan Elaris → KINGDOM-004
REGION-014 → Lembah Silvan → KINGDOM-004
REGION-015 → Sungai Elden → KINGDOM-004
REGION-016 → Perbatasan Wildmere → KINGDOM-004
```

Detail lengkap Region → City → Settlement → Population Model berada di:
`world/kingdoms/KINGDOM-004_GEOGRAPHY.md`

## 5. City Registry
```text
CITY-013 → Elaris → REGION-013 → KINGDOM-004
CITY-014 → Sylford → REGION-014 → KINGDOM-004
CITY-015 → Riverwyn → REGION-015 → KINGDOM-004
CITY-016 → Wildmere → REGION-016 → KINGDOM-004
```

## 6. Settlement Registry
```text
SETTLEMENT-025 → Greenford → CITY-013 → REGION-013 → KINGDOM-004
SETTLEMENT-026 → Mossvale → CITY-013 → REGION-013 → KINGDOM-004
SETTLEMENT-027 → Oakmere → CITY-014 → REGION-014 → KINGDOM-004
SETTLEMENT-028 → Fernwatch → CITY-014 → REGION-014 → KINGDOM-004
SETTLEMENT-029 → Brookrest → CITY-015 → REGION-015 → KINGDOM-004
SETTLEMENT-030 → Alderbank → CITY-015 → REGION-015 → KINGDOM-004
SETTLEMENT-031 → Pinecross → CITY-016 → REGION-016 → KINGDOM-004
SETTLEMENT-032 → Thornrest → CITY-016 → REGION-016 → KINGDOM-004
```

## 7. Population Model
```text
KINGDOM_ID: KINGDOM-004
POPULATION_MODEL_ID: POP-SYL-001
TOTAL_POPULATION: RANGE 400,000–650,000
URBANIZATION: LOW-MODERATE
PRIMARY_POPULATION_BASE: FORESTRY + AGRICULTURE + RIVER TRADE + CRAFTS
SEASONAL_MOBILITY: MODERATE
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
EXACT_OCCUPATIONAL_PERCENTAGES: ???
STATUS: ACTIVE
```

Regional distribution model:
```text
REGION-013 → 25–30%
REGION-014 → 25–30%
REGION-015 → 25–30%
REGION-016 → 15–20%
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
`world/kingdoms/KINGDOM-004_GEOGRAPHY.md`

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
```text
KINGDOM REGISTRY
→ GEOGRAPHY
→ POPULATION MODEL
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum Canon NPC coverage for Kingdom-004:
```text
DESA / SETTLEMENT → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KINGDOM → ≥ 10 Canon NPC
```

No Canon NPC is defined by this registry.

## 12. Integrity Rules
1. `KINGDOM-004` must always resolve to `EMPIRE-001`.
2. Every Region must resolve to `KINGDOM-004`.
3. Every City must resolve to both a valid Region and `KINGDOM-004`.
4. Every Settlement must resolve to both a valid City/Region and `KINGDOM-004`.
5. Population Model `POP-SYL-001` belongs to `KINGDOM-004`.
6. Geography detail remains in `KINGDOM-004_GEOGRAPHY.md`.
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
