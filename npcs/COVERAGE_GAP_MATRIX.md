# ELDORIA WORLD — NPC COVERAGE GAP MATRIX

> **Authority:** Admin
> **Status:** Admin Audit v1.0
> **Source:** `npcs/CANON_REGISTRY.md` + `npcs/COVERAGE_MATRIX_v1_0.md` + `world/CANON_GEOGRAPHY.md`
> **Audit Date:** 2026-09-16
> **Purpose:** Menunjukkan coverage aktual dan gap untuk seluruh 66 scope resmi tanpa membuat NPC baru.

## 1. Calculation Rule

Setiap Canon NPC dibandingkan terhadap lima kolom:

```text
EMPIRE + KINGDOM + CITY + SETTLEMENT + FACTION/NOBLE HOUSE
```

Assignment hanya dihitung jika field tersebut benar-benar tercatat dan valid. `???` = **0 coverage** pada kolom tersebut.

Satu NPC boleh menghasilkan beberapa scope assignments. Karena itu **21 NPC unik tidak sama dengan 21 total scope coverage**.

Faction/Noble House adalah kolom audit tambahan. Matrix v1.0 belum memberikan target numerik faction/house, sehingga kolom tersebut tidak dimasukkan ke denominator official `295`.

## 2. Official Scope Summary

| Scope | Units | Target each | Actual assignments | Gap |
|---|---:|---:|---:|---:|
| Empire | 1 | ≥25 | 21 | 4 |
| Kingdom | 5 | ≥10 | 15 | 35 |
| City | 20 | ≥5 | 9 | 91 |
| Settlement | 40 | ≥3 | 0 | 120 |
| **Official total** | **66** | — | **45** | **250** |

**Official coverage = 45 / 295 = 15.25%**

## 3. Empire

| ID | Name | Target | Actual | Gap | NPCs |
|---|---|---:|---:|---:|---|
| EMPIRE-001 | Kekaisaran Valthera | 25 | 21 | 4 | NPC-001–021 |

## 4. Kingdom

| ID | Kingdom | Target | Actual | Gap | NPCs |
|---|---|---:|---:|---:|---|
| KINGDOM-001 | Valedorn | 10 | 3 | 7 | NPC-006, 012, 017 |
| KINGDOM-002 | Brannor | 10 | 3 | 7 | NPC-007, 013, 018 |
| KINGDOM-003 | Mariselle | 10 | 3 | 7 | NPC-008, 014, 019 |
| KINGDOM-004 | Sylvaran | 10 | 3 | 7 | NPC-009, 015, 020 |
| KINGDOM-005 | Sahrad | 10 | 3 | 7 | NPC-010, 016, 021 |
| **TOTAL** | | **50** | **15** | **35** | |

## 5. City — All 20 Scope Units

| ID | City | Kingdom | Target | Actual | Gap | NPCs |
|---|---|---|---:|---:|---:|---|
| CITY-001 | Varenhold | K-001 | 5 | 1 | 4 | NPC-012 |
| CITY-002 | Averen | K-001 | 5 | 0 | 5 | — |
| CITY-003 | Goldmere | K-001 | 5 | 1 | 4 | NPC-006 |
| CITY-004 | Thornwick | K-001 | 5 | 0 | 5 | — |
| CITY-005 | Durnhaven | K-002 | 5 | 1 | 4 | NPC-013 |
| CITY-006 | Kharhold | K-002 | 5 | 0 | 5 | — |
| CITY-007 | Ferren | K-002 | 5 | 1 | 4 | NPC-007 |
| CITY-008 | Frostwatch | K-002 | 5 | 0 | 5 | — |
| CITY-009 | Port Aureon | K-003 | 5 | 2 | 3 | NPC-008, 014 |
| CITY-010 | Southport | K-003 | 5 | 0 | 5 | — |
| CITY-011 | Azurehold | K-003 | 5 | 0 | 5 | — |
| CITY-012 | Westhaven | K-003 | 5 | 0 | 5 | — |
| CITY-013 | Elaris | K-004 | 5 | 2 | 3 | NPC-009, 015 |
| CITY-014 | Sylford | K-004 | 5 | 0 | 5 | — |
| CITY-015 | Riverwyn | K-004 | 5 | 0 | 5 | — |
| CITY-016 | Wildmere | K-004 | 5 | 0 | 5 | — |
| CITY-017 | Qasrane | K-005 | 5 | 1 | 4 | NPC-016 |
| CITY-018 | Sarakh | K-005 | 5 | 0 | 5 | — |
| CITY-019 | Caravanser | K-005 | 5 | 0 | 5 | — |
| CITY-020 | Sunscar | K-005 | 5 | 0 | 5 | — |
| **TOTAL** | | | **100** | **9** | **91** | |

## 6. Settlement — All 40 Scope Units

All 40 settlements currently have **0 Canon NPC assignment**.

| ID | Settlement | Parent City | Target | Actual | Gap |
|---|---|---|---:|---:|---:|
| SETTLEMENT-001 | Bellmere | CITY-001 | 3 | 0 | 3 |
| SETTLEMENT-002 | Oakrest | CITY-001 | 3 | 0 | 3 |
| SETTLEMENT-003 | Rivergate | CITY-002 | 3 | 0 | 3 |
| SETTLEMENT-004 | Millhaven | CITY-002 | 3 | 0 | 3 |
| SETTLEMENT-005 | Wheatcross | CITY-003 | 3 | 0 | 3 |
| SETTLEMENT-006 | Sunfield | CITY-003 | 3 | 0 | 3 |
| SETTLEMENT-007 | Briarford | CITY-004 | 3 | 0 | 3 |
| SETTLEMENT-008 | Greenhollow | CITY-004 | 3 | 0 | 3 |
| SETTLEMENT-009 | Stonepass | CITY-005 | 3 | 0 | 3 |
| SETTLEMENT-010 | Highmere | CITY-005 | 3 | 0 | 3 |
| SETTLEMENT-011 | Valecrest | CITY-006 | 3 | 0 | 3 |
| SETTLEMENT-012 | Ironbrook | CITY-006 | 3 | 0 | 3 |
| SETTLEMENT-013 | Blackridge | CITY-007 | 3 | 0 | 3 |
| SETTLEMENT-014 | Redstone | CITY-007 | 3 | 0 | 3 |
| SETTLEMENT-015 | Pinewatch | CITY-008 | 3 | 0 | 3 |
| SETTLEMENT-016 | Coldmere | CITY-008 | 3 | 0 | 3 |
| SETTLEMENT-017 | Seabridge | CITY-009 | 3 | 0 | 3 |
| SETTLEMENT-018 | Tidemere | CITY-009 | 3 | 0 | 3 |
| SETTLEMENT-019 | Saltmere | CITY-010 | 3 | 0 | 3 |
| SETTLEMENT-020 | Gullhaven | CITY-010 | 3 | 0 | 3 |
| SETTLEMENT-021 | Pearlwatch | CITY-011 | 3 | 0 | 3 |
| SETTLEMENT-022 | Windrest | CITY-011 | 3 | 0 | 3 |
| SETTLEMENT-023 | Driftwood | CITY-012 | 3 | 0 | 3 |
| SETTLEMENT-024 | Stormbay | CITY-012 | 3 | 0 | 3 |
| SETTLEMENT-025 | Greenford | CITY-013 | 3 | 0 | 3 |
| SETTLEMENT-026 | Mossvale | CITY-013 | 3 | 0 | 3 |
| SETTLEMENT-027 | Oakmere | CITY-014 | 3 | 0 | 3 |
| SETTLEMENT-028 | Fernwatch | CITY-014 | 3 | 0 | 3 |
| SETTLEMENT-029 | Brookrest | CITY-015 | 3 | 0 | 3 |
| SETTLEMENT-030 | Alderbank | CITY-015 | 3 | 0 | 3 |
| SETTLEMENT-031 | Pinecross | CITY-016 | 3 | 0 | 3 |
| SETTLEMENT-032 | Thornrest | CITY-016 | 3 | 0 | 3 |
| SETTLEMENT-033 | Wellspring | CITY-017 | 3 | 0 | 3 |
| SETTLEMENT-034 | Datehaven | CITY-017 | 3 | 0 | 3 |
| SETTLEMENT-035 | Grassrest | CITY-018 | 3 | 0 | 3 |
| SETTLEMENT-036 | Herdwatch | CITY-018 | 3 | 0 | 3 |
| SETTLEMENT-037 | Dustgate | CITY-019 | 3 | 0 | 3 |
| SETTLEMENT-038 | Redwell | CITY-019 | 3 | 0 | 3 |
| SETTLEMENT-039 | Sandmere | CITY-020 | 3 | 0 | 3 |
| SETTLEMENT-040 | Farwatch | CITY-020 | 3 | 0 | 3 |
| **TOTAL** | | | **120** | **0** | **120** |

## 7. Faction / Noble House Column

This column is audited separately because it has no numeric target in Matrix v1.0.

| Faction context | NPC assignments |
|---|---:|
| Imperial factions | 5 — NPC-001–005 |
| Kingdom factions | 10 — NPC-006–010 and NPC-012–016 |
| Noble Houses | 6 — NPC-016–021 |
| **Total assignments** | **21** |

NPC-016 is correctly counted in both a Kingdom faction and a Noble House because its registry contains both contexts. This is an assignment count, not a unique-faction count.

## 8. 21-NPC Assignment Audit

| NPC range | Empire | Kingdom | City | Settlement | Faction/House |
|---|:---:|:---:|:---:|:---:|:---:|
| NPC-001–005 | ✓ | — | — | — | ✓ |
| NPC-006–010 | ✓ | ✓ | ✓ | ??? / 0 | ✓ |
| NPC-011 | ✓ | — | — | — | ✓ |
| NPC-012–015 | ✓ | ✓ | ✓ | — | ✓ |
| NPC-016 | ✓ | ✓ | ✓ | — | ✓ + House |
| NPC-017–021 | ✓ | ✓ | — | — | ✓ + House |

`NPC-006–010` each have a valid City and Kingdom assignment but `SETTLEMENT_ID: ???`; therefore no settlement coverage is awarded.

## 9. Gap Priority Data

Current zero-coverage city scopes:

```text
CITY-002 Averen
CITY-004 Thornwick
CITY-006 Kharhold
CITY-008 Frostwatch
CITY-010 Southport
CITY-011 Azurehold
CITY-012 Westhaven
CITY-014 Sylford
CITY-015 Riverwyn
CITY-016 Wildmere
CITY-018 Sarakh
CITY-019 Caravanser
CITY-020 Sunscar
```

Current zero-coverage settlement scopes:

```text
SETTLEMENT-001 through SETTLEMENT-040
```

All five kingdoms are below minimum:

```text
KINGDOM-001: 3 / 10
KINGDOM-002: 3 / 10
KINGDOM-003: 3 / 10
KINGDOM-004: 3 / 10
KINGDOM-005: 3 / 10
```

Empire:

```text
EMPIRE-001: 21 / 25
```

## 10. Admin Conclusion

```text
UNIQUE CANON NPC: 21
OFFICIAL SCOPE UNITS: 66
OFFICIAL TARGET: 295
ACTUAL OFFICIAL SCOPE COVERAGE: 45
OFFICIAL GAP: 250
OFFICIAL PROGRESS: 15.25%
FACTION/HOUSE ASSIGNMENTS: 21
```

The next NPC batch must be selected from these verified gaps and justified by actual Canon context. The gap itself is **not** an automatic creation order. No filler, duplicate, invented settlement assignment, invented faction membership, or unsupported authority may be introduced.
