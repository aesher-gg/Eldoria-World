# ELDORIA WORLD — KINGDOM-005 REGISTRY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-005 — Kerajaan Sahrad
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi identitas, parent hierarchy, geography reference, population model, dan Canon boundaries Kingdom-005.

## 1. Kingdom Identity
```text
KINGDOM_ID: KINGDOM-005
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Sahrad
TYPE: Kerajaan Arid-Steppe
CAPITAL: Qasrane
CONTINENT: Benua Utama Eldoria
STATUS: ACTIVE CANON
BOUNDARY: Wilayah kering, padang rumput, dan koridor oasis di Benua Utama Eldoria; detail batas fisik dibangun melalui Region Canon
CURRENT_STATE: Stabil secara administratif; kondisi politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang dari jaringan oasis, jalur kafilah, peternakan, dan perdagangan lintas wilayah; detail pendirian = ???
HISTORY: ???
```

## 2. Kingdom Function
Sahrad merupakan kerajaan arid-steppe dan koridor perdagangan darat di bawah Kekaisaran Valthera. Fungsi geografis dan ekonominya berpusat pada:

- oasis dan sumber air,
- padang rumput kering dan pastoralism,
- jalur kafilah,
- perdagangan jarak jauh,
- pertanian oasis,
- kerajinan dan jasa frontier.

Karakter regional Canon: **kering, mobil, berorientasi jalur dagang, dan bergantung pada sumber daya air**.

Fungsi tersebut tidak menentukan ras, Class, Skill, Faction, kepribadian, moralitas, atau nasib individu.

## 3. Administrative Hierarchy
```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-005 — Kerajaan Sahrad
    ├── REGION-017 — Oasis Qasrane
    │   └── CITY-017 — Qasrane
    │       ├── SETTLEMENT-033 — Wellspring
    │       └── SETTLEMENT-034 — Datehaven
    ├── REGION-018 — Padang Rumput Sahr
    │   └── CITY-018 — Sarakh
    │       ├── SETTLEMENT-035 — Grassrest
    │       └── SETTLEMENT-036 — Herdwatch
    ├── REGION-019 — Koridor Kafilah Timur
    │   └── CITY-019 — Caravanser
    │       ├── SETTLEMENT-037 — Dustgate
    │       └── SETTLEMENT-038 — Redwell
    └── REGION-020 — Perbatasan Sunscar
        └── CITY-020 — Sunscar
            ├── SETTLEMENT-039 — Sandmere
            └── SETTLEMENT-040 — Farwatch
```

## 4. Region Registry
```text
REGION-017 → Oasis Qasrane → KINGDOM-005
REGION-018 → Padang Rumput Sahr → KINGDOM-005
REGION-019 → Koridor Kafilah Timur → KINGDOM-005
REGION-020 → Perbatasan Sunscar → KINGDOM-005
```

Detail lengkap Region → City → Settlement → Population Model berada di:
`world/kingdoms/KINGDOM-005_GEOGRAPHY.md`

## 5. City Registry
```text
CITY-017 → Qasrane → REGION-017 → KINGDOM-005
CITY-018 → Sarakh → REGION-018 → KINGDOM-005
CITY-019 → Caravanser → REGION-019 → KINGDOM-005
CITY-020 → Sunscar → REGION-020 → KINGDOM-005
```

## 6. Settlement Registry
```text
SETTLEMENT-033 → Wellspring → CITY-017 → REGION-017 → KINGDOM-005
SETTLEMENT-034 → Datehaven → CITY-017 → REGION-017 → KINGDOM-005
SETTLEMENT-035 → Grassrest → CITY-018 → REGION-018 → KINGDOM-005
SETTLEMENT-036 → Herdwatch → CITY-018 → REGION-018 → KINGDOM-005
SETTLEMENT-037 → Dustgate → CITY-019 → REGION-019 → KINGDOM-005
SETTLEMENT-038 → Redwell → CITY-019 → REGION-019 → KINGDOM-005
SETTLEMENT-039 → Sandmere → CITY-020 → REGION-020 → KINGDOM-005
SETTLEMENT-040 → Farwatch → CITY-020 → REGION-020 → KINGDOM-005
```

## 7. Population Model
```text
KINGDOM_ID: KINGDOM-005
POPULATION_MODEL_ID: POP-SAH-001
TOTAL_POPULATION: RANGE 300,000–500,000
URBANIZATION: LOW
PRIMARY_POPULATION_BASE: CARAVAN TRADE + PASTORALISM + OASIS AGRICULTURE + CRAFTS
SEASONAL_MOBILITY: HIGH
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
EXACT_OCCUPATIONAL_PERCENTAGES: ???
STATUS: ACTIVE
```

Regional distribution model:
```text
REGION-017 → 25–30%
REGION-018 → 25–30%
REGION-019 → 25–30%
REGION-020 → 15–20%
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
`world/kingdoms/KINGDOM-005_GEOGRAPHY.md`

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

Minimum Canon NPC coverage for Kingdom-005:
```text
DESA / SETTLEMENT → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KINGDOM → ≥ 10 Canon NPC
```

No Canon NPC is defined by this registry.

## 12. Integrity Rules
1. `KINGDOM-005` must always resolve to `EMPIRE-001`.
2. Every Region must resolve to `KINGDOM-005`.
3. Every City must resolve to both a valid Region and `KINGDOM-005`.
4. Every Settlement must resolve to both a valid City/Region and `KINGDOM-005`.
5. Population Model `POP-SAH-001` belongs to `KINGDOM-005`.
6. Geography detail remains in `KINGDOM-005_GEOGRAPHY.md`.
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
GEOGRAPHY_FILE: EXISTING / REQUIRES NORMALIZATION
FACTION_GOVERNANCE_CONTEXT: PENDING
CANON_NPC: PENDING
```
