# ELDORIA WORLD — CANON NPC COVERAGE MATRIX v1.0

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Master coverage matrix untuk merencanakan kebutuhan Canon NPC berdasarkan struktur Empire → Kingdom → City → Settlement dan konteks Faction/Noble House.
> **Scope:** Planning / coverage only.

## Scope Targets
| Scope | Units | Minimum each | Minimum coverage |
|---|---:|---:|---:|
| Empire | 1 | ≥25 | ≥25 |
| Kingdom | 5 | ≥10 | ≥50 |
| City | 20 | ≥5 | ≥100 |
| Settlement | 40 | ≥3 | ≥120 |
| **Total official scope coverage** | **66** | — | **≥295** |

`Faction / Noble House` adalah assignment tambahan tanpa target numerik pada v1.0 dan tidak masuk denominator 295.

**295 = scope coverage, bukan 295 NPC unik.** Satu NPC boleh memiliki beberapa assignment jika benar-benar didukung Canon. Geographic containment saja tidak cukup untuk membuat assignment tambahan.

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
| Faction / Noble House | **26 primary assignments + 5 secondary contexts** | No numeric target | — |
| **Official scope coverage** | **65** | **≥295** | **230** |

**Official scope coverage progress: 65 / 295 = 22.03%.**

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

## City Coverage
| ID | City | Target | Actual | Gap | NPCs |
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

## Settlement Coverage
All 40 settlements are official scope units. Batch 1 adds one assignment to SETTLEMENT-003, -011, -019, -027, and -035. Semua settlement lainnya tetap 0 coverage. Full per-settlement listing remains authoritative in `npcs/COVERAGE_GAP_MATRIX.md`.

```text
SETTLEMENT-003 Rivergate: 1 / 3
SETTLEMENT-011 Valecrest: 1 / 3
SETTLEMENT-019 Saltmere: 1 / 3
SETTLEMENT-027 Oakmere: 1 / 3
SETTLEMENT-035 Grassrest: 1 / 3
OTHER 35 SETTLEMENTS: 0 / 3
TOTAL: 5 / 120
```

## Faction / Noble House Assignment Audit
| Assignment class | Primary assignments | Secondary contexts |
|---|---:|---:|
| Imperial factions | 5 | 0 |
| Kingdom factions | 15 | 5 |
| Noble Houses | 6 | 0 |
| **Total primary assignments** | **26** | **5 secondary contexts** |

No new faction or Noble House was created for Batch 1.

## Batch 1 Audit
| NPC | Settlement | City | Kingdom | Empire | Primary faction | Secondary context | Result |
|---|---|---|---|---|---|---|---|
| NPC-022 Maren Vale | SETTLEMENT-003 Rivergate | CITY-002 Averen | K-001 | E-001 | FACTION-201 | FACTION-103 | PASS |
| NPC-023 Borin Keld | SETTLEMENT-011 Valecrest | CITY-006 Kharhold | K-002 | E-001 | FACTION-206 | FACTION-114 | PASS |
| NPC-024 Selene Varo | SETTLEMENT-019 Saltmere | CITY-010 Southport | K-003 | E-001 | FACTION-210 | FACTION-123 | PASS |
| NPC-025 Elira Fen | SETTLEMENT-027 Oakmere | CITY-014 Sylford | K-004 | E-001 | FACTION-214 | FACTION-134 | PASS |
| NPC-026 Rafiq Sahr | SETTLEMENT-035 Grassrest | CITY-018 Sarakh | K-005 | E-001 | FACTION-218 | FACTION-144 | PASS |

## Canonization Gate
```text
[✓] Coverage need valid
[✓] Geography verified
[✓] City was previously 0
[✓] Settlement was previously 0
[✓] Kingdom overlap valid
[✓] Empire overlap valid
[✓] Existing faction contexts valid
[✓] No new faction required
[✓] Race Canon available
[✓] No duplicate role
[✓] Material world function
[✓] Agency defined
[✓] Knowledge boundary defined
[✓] Origin traceable
[✓] Current state defined
[✓] Authority boundaries respected
```

## Correct Recalculation
Batch 1 terdiri dari 5 NPC. Masing-masing memberi tepat empat geographic assignments: Empire + Kingdom + City + Settlement. Jadi penambahan geographic scope adalah **5 × 4 = 20**, bukan 25.

```text
BEFORE: 45 / 295
ADDED:  +20
AFTER:  65 / 295
PROGRESS: 22.03%
GAP: 230
```

## Final Principle
> Coverage Matrix mengatur pemerataan kebutuhan Canon NPC; bukan alasan pembuatan NPC filler. Faction/House adalah konteks tambahan dan tidak boleh dibuat hanya untuk menaikkan angka.
