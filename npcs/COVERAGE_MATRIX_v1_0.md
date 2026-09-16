# ELDORIA WORLD — CANON NPC COVERAGE MATRIX v1.0

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Master coverage matrix untuk merencanakan kebutuhan Canon NPC berdasarkan struktur Empire → Kingdom → City → Settlement dan konteks Faction/Noble House tanpa membuat NPC individual.
> **Scope:** Planning / coverage only. File ini tidak mendaftarkan identitas NPC.

## Scope Targets
| Scope | Units | Minimum each | Minimum coverage |
|---|---:|---:|---:|
| Empire | 1 | ≥25 | ≥25 |
| Kingdom | 5 | ≥10 | ≥50 |
| City | 20 | ≥5 | ≥100 |
| Settlement | 40 | ≥3 | ≥120 |
| **Total official scope coverage** | **66** | — | **≥295** |

`Faction / Noble House` adalah kolom assignment tambahan. v1.0 tidak menetapkan target numerik terpisah untuk faction/house, sehingga assignment-nya dilaporkan tetapi tidak dimasukkan ke denominator 295.

**295 = scope coverage, bukan 295 NPC unik.** Satu NPC boleh memiliki beberapa assignment scope jika hubungan tersebut benar-benar didukung Canon. Geographic containment saja tidak cukup untuk membuat assignment tambahan.

## Coverage Calculation Rule
```text
NPC
├── EMPIRE_ID       → Empire coverage
├── KINGDOM_ID      → Kingdom coverage
├── CITY_ID         → City coverage
├── SETTLEMENT_ID   → Settlement coverage
└── FACTION / HOUSE → Faction / Noble House assignment
```
`???` tidak dihitung sebagai coverage.

## Current Audited Coverage — 2026-09-16
| Coverage column | Actual | Target | Gap |
|---|---:|---:|---:|
| Empire | **26** | ≥25 | **0** |
| Kingdom | **20** | ≥50 | **30** |
| City | **14** | ≥100 | **86** |
| Settlement | **5** | ≥120 | **115** |
| Faction / Noble House | **31 assignments** | No numeric target in v1.0 | — |
| **Official scope coverage** | **70** | **≥295** | **225** |

**Official scope coverage progress: 70 / 295 = 23.73%.**

## Empire Coverage
| ID | Name | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| EMPIRE-001 | Kekaisaran Valthera | 25 | 26 | 0 | NPC-001–026 |

## Kingdom Coverage
| ID | Kingdom | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| KINGDOM-001 | Valedorn | 10 | 4 | 6 | NPC-006, 012, 017, 022 |
| KINGDOM-002 | Brannor | 10 | 4 | 6 | NPC-007, 013, 018, 023 |
| KINGDOM-003 | Mariselle | 10 | 4 | 6 | NPC-008, 014, 019, 024 |
| KINGDOM-004 | Sylvaran | 10 | 4 | 6 | NPC-009, 015, 020, 025 |
| KINGDOM-005 | Sahrad | 10 | 4 | 6 | NPC-010, 016, 021, 026 |
| **TOTAL** | | **50** | **20** | **30** | |

## City Coverage — 20 Scope Units
| ID | City | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| CITY-001 | Varenhold | 5 | 1 | 4 | NPC-012 |
| CITY-002 | Averen | 5 | 1 | 4 | NPC-022 |
| CITY-003 | Goldmere | 5 | 1 | 4 | NPC-006 |
| CITY-004 | Thornwick | 5 | 0 | 5 | — |
| CITY-005 | Durnhaven | 5 | 1 | 4 | NPC-013 |
| CITY-006 | Kharhold | 5 | 1 | 4 | NPC-023 |
| CITY-007 | Ferren | 5 | 1 | 4 | NPC-007 |
| CITY-008 | Frostwatch | 5 | 0 | 5 | — |
| CITY-009 | Port Aureon | 5 | 2 | 3 | NPC-008, 014 |
| CITY-010 | Southport | 5 | 1 | 4 | NPC-024 |
| CITY-011 | Azurehold | 5 | 0 | 5 | — |
| CITY-012 | Westhaven | 5 | 0 | 5 | — |
| CITY-013 | Elaris | 5 | 2 | 3 | NPC-009, 015 |
| CITY-014 | Sylford | 5 | 1 | 4 | NPC-025 |
| CITY-015 | Riverwyn | 5 | 0 | 5 | — |
| CITY-016 | Wildmere | 5 | 0 | 5 | — |
| CITY-017 | Qasrane | 5 | 1 | 4 | NPC-016 |
| CITY-018 | Sarakh | 5 | 1 | 4 | NPC-026 |
| CITY-019 | Caravanser | 5 | 0 | 5 | — |
| CITY-020 | Sunscar | 5 | 0 | 5 | — |
| **TOTAL** | | **100** | **14** | **86** | |

## Settlement Coverage — 40 Scope Units

> Settlement yang belum tercatat sebagai assignment Canon tetap 0. NPC dengan `SETTLEMENT_ID: ???` tidak dihitung.

| ID | Settlement | Parent City | Target | Actual | Gap |
|---|---|---|---:|---:|---:|
| SETTLEMENT-001 | Bellmere | CITY-001 Varenhold | 3 | 0 | 3 |
| SETTLEMENT-002 | Oakrest | CITY-001 Varenhold | 3 | 0 | 3 |
| SETTLEMENT-003 | Rivergate | CITY-002 Averen | 3 | 1 | 2 |
| SETTLEMENT-004 | Millhaven | CITY-002 Averen | 3 | 0 | 3 |
| SETTLEMENT-005 | Wheatcross | CITY-003 Goldmere | 3 | 0 | 3 |
| SETTLEMENT-006 | Sunfield | CITY-003 Goldmere | 3 | 0 | 3 |
| SETTLEMENT-007 | Briarford | CITY-004 Thornwick | 3 | 0 | 3 |
| SETTLEMENT-008 | Greenhollow | CITY-004 Thornwick | 3 | 0 | 3 |
| SETTLEMENT-009 | Stonepass | CITY-005 Durnhaven | 3 | 0 | 3 |
| SETTLEMENT-010 | Highmere | CITY-005 Durnhaven | 3 | 0 | 3 |
| SETTLEMENT-011 | Valecrest | CITY-006 Kharhold | 3 | 1 | 2 |
| SETTLEMENT-012 | Ironbrook | CITY-006 Kharhold | 3 | 0 | 3 |
| SETTLEMENT-013 | Blackridge | CITY-007 Ferren | 3 | 0 | 3 |
| SETTLEMENT-014 | Redstone | CITY-007 Ferren | 3 | 0 | 3 |
| SETTLEMENT-015 | Pinewatch | CITY-008 Frostwatch | 3 | 0 | 3 |
| SETTLEMENT-016 | Coldmere | CITY-008 Frostwatch | 3 | 0 | 3 |
| SETTLEMENT-017 | Seabridge | CITY-009 Port Aureon | 3 | 0 | 3 |
| SETTLEMENT-018 | Tidemere | CITY-009 Port Aureon | 3 | 0 | 3 |
| SETTLEMENT-019 | Saltmere | CITY-010 Southport | 3 | 1 | 2 |
| SETTLEMENT-020 | Gullhaven | CITY-010 Southport | 3 | 0 | 3 |
| SETTLEMENT-021 | Pearlwatch | CITY-011 Azurehold | 3 | 0 | 3 |
| SETTLEMENT-022 | Windrest | CITY-011 Azurehold | 3 | 0 | 3 |
| SETTLEMENT-023 | Driftwood | CITY-012 Westhaven | 3 | 0 | 3 |
| SETTLEMENT-024 | Stormbay | CITY-012 Westhaven | 3 | 0 | 3 |
| SETTLEMENT-025 | Greenford | CITY-013 Elaris | 3 | 0 | 3 |
| SETTLEMENT-026 | Mossvale | CITY-013 Elaris | 3 | 0 | 3 |
| SETTLEMENT-027 | Oakmere | CITY-014 Sylford | 3 | 1 | 2 |
| SETTLEMENT-028 | Fernwatch | CITY-014 Sylford | 3 | 0 | 3 |
| SETTLEMENT-029 | Brookrest | CITY-015 Riverwyn | 3 | 0 | 3 |
| SETTLEMENT-030 | Alderbank | CITY-015 Riverwyn | 3 | 0 | 3 |
| SETTLEMENT-031 | Pinecross | CITY-016 Wildmere | 3 | 0 | 3 |
| SETTLEMENT-032 | Thornrest | CITY-016 Wildmere | 3 | 0 | 3 |
| SETTLEMENT-033 | Wellspring | CITY-017 Qasrane | 3 | 0 | 3 |
| SETTLEMENT-034 | Datehaven | CITY-017 Qasrane | 3 | 0 | 3 |
| SETTLEMENT-035 | Grassrest | CITY-018 Sarakh | 3 | 1 | 2 |
| SETTLEMENT-036 | Herdwatch | CITY-018 Sarakh | 3 | 0 | 3 |
| SETTLEMENT-037 | Dustgate | CITY-019 Caravanser | 3 | 0 | 3 |
| SETTLEMENT-038 | Redwell | CITY-019 Caravanser | 3 | 0 | 3 |
| SETTLEMENT-039 | Sandmere | CITY-020 Sunscar | 3 | 0 | 3 |
| SETTLEMENT-040 | Farwatch | CITY-020 Sunscar | 3 | 0 | 3 |
| **TOTAL** | | | **120** | **5** | **115** |

## Faction / Noble House Assignment Audit
| Assignment class | Actual assignments | NPCs |
|---|---:|---|
| Imperial factions | 5 | NPC-001–005 |
| Kingdom factions | 15 | NPC-006–010, NPC-012–016, NPC-022–026 |
| Noble Houses | 6 | NPC-016–021 |
| **Total NPC faction/house assignments** | **26** | NPC-001–026 |

> Catatan: angka assignment dapat lebih besar dari jumlah NPC unik jika satu NPC memiliki lebih dari satu konteks organisasi. Secondary faction context pada Batch 1 merupakan konteks tambahan, bukan penambahan organisasi Canon baru.

## Batch 1 Audit

| NPC | Settlement | City | Kingdom | Empire | Primary faction | Secondary context | Result |
|---|---|---|---|---|---|---|---|
| NPC-022 Maren Vale | SETTLEMENT-003 | CITY-002 | KINGDOM-001 | EMPIRE-001 | FACTION-201 | FACTION-103 | PASS |
| NPC-023 Borin Keld | SETTLEMENT-011 | CITY-006 | KINGDOM-002 | EMPIRE-001 | FACTION-206 | FACTION-114 | PASS |
| NPC-024 Selene Varo | SETTLEMENT-019 | CITY-010 | KINGDOM-003 | EMPIRE-001 | FACTION-210 | FACTION-123 | PASS |
| NPC-025 Elira Fen | SETTLEMENT-027 | CITY-014 | KINGDOM-004 | EMPIRE-001 | FACTION-214 | FACTION-134 | PASS |
| NPC-026 Rafiq Sahr | SETTLEMENT-035 | CITY-018 | KINGDOM-005 | EMPIRE-001 | FACTION-218 | FACTION-144 | PASS |

## Role Integrity
Roles must be justified by established geography, population, governance, economy, faction, or other Canon context. Batch 1 roles correspond directly to the established functions of their settlements/cities and do not introduce unsupported institutions.

## Overlap Rules
**Allowed:** genuine cross-scope officials, faction leaders, regional specialists, and settlement figures with real wider influence.

**Forbidden:** reuse solely to reach quota, artificial authority, or automatic scope relevance from geographic containment.

## Anti-Filler / Anti-Duplicate
Reject candidates created only for quota, without material function/agency, with unsupported location/background, with template duplication, or with unverifiable Origin/knowledge boundary/Race.

## Race Safety
Every Canon NPC must use an active `RACE_CANON_ID` from `races/CANON_REGISTRY.md`. Race must not be inferred from name, location, role, faction, appearance stereotype, or profession.

## Canonization Gate
```text
[✓] Coverage need valid
[✓] Geography verified
[✓] Population context verified
[✓] Governance context verified
[✓] Faction context verified
[✓] Race Canon available
[✓] No duplicate
[✓] Role materially justified
[✓] Agency justified
[✓] Knowledge boundary defined
[✓] Origin traceable
[✓] Identity schema complete
```

## Status
```text
EMPIRE TARGET: ≥25
KINGDOM TARGET: ≥10 × 5 = ≥50
CITY TARGET: ≥5 × 20 = ≥100
SETTLEMENT TARGET: ≥3 × 40 = ≥120
TOTAL SCOPE COVERAGE TARGET: ≥295

AUDITED EMPIRE COVERAGE: 26 / 25
AUDITED KINGDOM COVERAGE: 20 / 50
AUDITED CITY COVERAGE: 14 / 100
AUDITED SETTLEMENT COVERAGE: 5 / 120
AUDITED OFFICIAL SCOPE COVERAGE: 70 / 295
AUDITED OFFICIAL COVERAGE PROGRESS: 23.73%
FACTION / HOUSE ASSIGNMENTS: 26 primary assignments; 5 additional secondary contexts

INDIVIDUAL CANON NPC CREATED: 26
INDIVIDUAL CANON NPC REGISTERED: 26
```

> Coverage Matrix mengatur pemerataan kebutuhan Canon NPC; bukan alasan pembuatan NPC filler.
