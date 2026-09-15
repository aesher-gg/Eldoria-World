# ELDORIA WORLD — KINGDOM-003 REGISTRY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-003 — Kerajaan Mariselle
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi identitas, parent hierarchy, geography reference, population model, dan Canon boundaries Kingdom-003.

## 1. Kingdom Identity
```text
KINGDOM_ID: KINGDOM-003
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Mariselle
TYPE: Kerajaan Coastal-Maritime
CAPITAL: Port Aureon
CONTINENT: Benua Utama Eldoria
STATUS: ACTIVE CANON
BOUNDARY: Wilayah pesisir dan kepulauan yang terhubung dengan Benua Utama Eldoria; detail batas fisik dibangun melalui Region Canon
CURRENT_STATE: Stabil secara administratif; kondisi politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang dari pusat pelabuhan, pelayaran, dan perdagangan laut; detail pendirian = ???
HISTORY: ???
```

## 2. Kingdom Function
Mariselle merupakan kerajaan pesisir-maritim di bawah Kekaisaran Valthera. Fungsi geografis dan ekonominya berpusat pada:

- pelabuhan dan perdagangan laut,
- perikanan,
- pelayaran,
- galangan kapal,
- perdagangan pesisir,
- konektivitas antarpantai dan kepulauan.

Karakter regional Canon: **maritim, terhubung, perdagangan-oriented, dan bergantung pada kondisi pesisir**.

Fungsi tersebut tidak menentukan ras, Class, Skill, Faction, kepribadian, moralitas, atau nasib individu.

## 3. Administrative Hierarchy
```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-003 — Kerajaan Mariselle
    ├── REGION-009 — Teluk Aureon
    │   └── CITY-009 — Port Aureon
    │       ├── SETTLEMENT-017 — Seabridge
    │       └── SETTLEMENT-018 — Tidemere
    ├── REGION-010 — Pantai Selatan
    │   └── CITY-010 — Southport
    │       ├── SETTLEMENT-019 — Saltmere
    │       └── SETTLEMENT-020 — Gullhaven
    ├── REGION-011 — Kepulauan Azure
    │   └── CITY-011 — Azurehold
    │       ├── SETTLEMENT-021 — Pearlwatch
    │       └── SETTLEMENT-022 — Windrest
    └── REGION-012 — Pesisir Barat
        └── CITY-012 — Westhaven
            ├── SETTLEMENT-023 — Driftwood
            └── SETTLEMENT-024 — Stormbay
```

## 4. Region Registry
```text
REGION-009 → Teluk Aureon → KINGDOM-003
REGION-010 → Pantai Selatan → KINGDOM-003
REGION-011 → Kepulauan Azure → KINGDOM-003
REGION-012 → Pesisir Barat → KINGDOM-003
```

Detail lengkap Region → City → Settlement → Population Model berada di:
`world/kingdoms/KINGDOM-003_GEOGRAPHY.md`

## 5. City Registry
```text
CITY-009 → Port Aureon → REGION-009 → KINGDOM-003
CITY-010 → Southport → REGION-010 → KINGDOM-003
CITY-011 → Azurehold → REGION-011 → KINGDOM-003
CITY-012 → Westhaven → REGION-012 → KINGDOM-003
```

## 6. Settlement Registry
```text
SETTLEMENT-017 → Seabridge → CITY-009 → REGION-009 → KINGDOM-003
SETTLEMENT-018 → Tidemere → CITY-009 → REGION-009 → KINGDOM-003
SETTLEMENT-019 → Saltmere → CITY-010 → REGION-010 → KINGDOM-003
SETTLEMENT-020 → Gullhaven → CITY-010 → REGION-010 → KINGDOM-003
SETTLEMENT-021 → Pearlwatch → CITY-011 → REGION-011 → KINGDOM-003
SETTLEMENT-022 → Windrest → CITY-011 → REGION-011 → KINGDOM-003
SETTLEMENT-023 → Driftwood → CITY-012 → REGION-012 → KINGDOM-003
SETTLEMENT-024 → Stormbay → CITY-012 → REGION-012 → KINGDOM-003
```

## 7. Population Model
```text
KINGDOM_ID: KINGDOM-003
POPULATION_MODEL_ID: POP-MAR-001
TOTAL_POPULATION: RANGE 500,000–800,000
URBANIZATION: MODERATE
PRIMARY_POPULATION_BASE: MARITIME TRADE + FISHERIES + COASTAL AGRICULTURE + SHIPBUILDING
SEASONAL_MOBILITY: HIGH
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
EXACT_OCCUPATIONAL_PERCENTAGES: ???
STATUS: ACTIVE
```

Regional distribution model:
```text
REGION-009 → 25–30%
REGION-010 → 25–30%
REGION-011 → 15–20%
REGION-012 → 20–25%
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
`world/kingdoms/KINGDOM-003_GEOGRAPHY.md`

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

Minimum Canon NPC coverage for Kingdom-003:
```text
DESA / SETTLEMENT → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KINGDOM → ≥ 10 Canon NPC
```

No Canon NPC is defined by this registry.

## 12. Integrity Rules
1. `KINGDOM-003` must always resolve to `EMPIRE-001`.
2. Every Region must resolve to `KINGDOM-003`.
3. Every City must resolve to both a valid Region and `KINGDOM-003`.
4. Every Settlement must resolve to both a valid City/Region and `KINGDOM-003`.
5. Population Model `POP-MAR-001` belongs to `KINGDOM-003`.
6. Geography detail remains in `KINGDOM-003_GEOGRAPHY.md`.
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
