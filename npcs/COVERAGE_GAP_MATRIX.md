# ELDORIA WORLD — NPC COVERAGE GAP MATRIX

> **Authority:** Admin
> **Status:** Admin Audit v1.1
> **Source:** `npcs/CANON_REGISTRY.md` + `npcs/COVERAGE_MATRIX_v1_0.md` + `world/CANON_GEOGRAPHY.md` + Kingdom Geography files
> **Audit Date:** 2026-09-16
> **Purpose:** Menunjukkan coverage aktual dan gap untuk seluruh 66 scope resmi serta assignment Faction/Noble House.

## 1. Calculation Rule
Setiap Canon NPC dibandingkan terhadap lima kolom:
```text
EMPIRE + KINGDOM + CITY + SETTLEMENT + FACTION/NOBLE HOUSE
```
Assignment hanya dihitung jika field tersebut benar-benar tercatat dan valid. `???` = 0 coverage pada kolom tersebut.

Satu NPC boleh menghasilkan beberapa scope assignments. Faction/Noble House adalah kolom audit tambahan dan tidak masuk denominator official `295` karena v1.0 tidak menetapkan target numeriknya.

## 2. Official Scope Summary
| Scope | Units | Target each | Actual assignments | Gap |
|---|---:|---:|---:|---:|
| Empire | 1 | ≥25 | 26 | 0 |
| Kingdom | 5 | ≥10 | 20 | 30 |
| City | 20 | ≥5 | 14 | 86 |
| Settlement | 40 | ≥3 | 5 | 115 |
| **Official total** | **66** | — | **70** | **225** |

**Official coverage = 70 / 295 = 23.73%**

## 3. Empire
| ID | Name | Target | Actual | Gap | NPCs |
|---|---|---:|---:|---:|---|
| EMPIRE-001 | Kekaisaran Valthera | 25 | 26 | 0 | NPC-001–026 |

## 4. Kingdom
| ID | Kingdom | Target | Actual | Gap | NPCs |
|---|---|---:|---:|---:|---|
| KINGDOM-001 | Valedorn | 10 | 4 | 6 | NPC-006, 012, 017, 022 |
| KINGDOM-002 | Brannor | 10 | 4 | 6 | NPC-007, 013, 018, 023 |
| KINGDOM-003 | Mariselle | 10 | 4 | 6 | NPC-008, 014, 019, 024 |
| KINGDOM-004 | Sylvaran | 10 | 4 | 6 | NPC-009, 015, 020, 025 |
| KINGDOM-005 | Sahrad | 10 | 4 | 6 | NPC-010, 016, 021, 026 |
| **TOTAL** | | **50** | **20** | **30** | |

## 5. City — All 20 Scope Units
| ID | City | Kingdom | Target | Actual | Gap | NPCs |
|---|---|---|---:|---:|---:|---|
| CITY-001 | Varenhold | K-001 | 5 | 1 | 4 | NPC-012 |
| CITY-002 | Averen | K-001 | 5 | 1 | 4 | NPC-022 |
| CITY-003 | Goldmere | K-001 | 5 | 1 | 4 | NPC-006 |
| CITY-004 | Thornwick | K-001 | 5 | 0 | 5 | — |
| CITY-005 | Durnhaven | K-002 | 5 | 1 | 4 | NPC-013 |
| CITY-006 | Kharhold | K-002 | 5 | 1 | 4 | NPC-023 |
| CITY-007 | Ferren | K-002 | 5 | 1 | 4 | NPC-007 |
| CITY-008 | Frostwatch | K-002 | 5 | 0 | 5 | — |
| CITY-009 | Port Aureon | K-003 | 5 | 2 | 3 | NPC-008, 014 |
| CITY-010 | Southport | K-003 | 5 | 1 | 4 | NPC-024 |
| CITY-011 | Azurehold | K-003 | 5 | 0 | 5 | — |
| CITY-012 | Westhaven | K-003 | 5 | 0 | 5 | — |
| CITY-013 | Elaris | K-004 | 5 | 2 | 3 | NPC-009, 015 |
| CITY-014 | Sylford | K-004 | 5 | 1 | 4 | NPC-025 |
| CITY-015 | Riverwyn | K-004 | 5 | 0 | 5 | — |
| CITY-016 | Wildmere | K-004 | 5 | 0 | 5 | — |
| CITY-017 | Qasrane | K-005 | 5 | 1 | 4 | NPC-016 |
| CITY-018 | Sarakh | K-005 | 5 | 1 | 4 | NPC-026 |
| CITY-019 | Caravanser | K-005 | 5 | 0 | 5 | — |
| CITY-020 | Sunscar | K-005 | 5 | 0 | 5 | — |
| **TOTAL** | | | **100** | **14** | **86** | |

## 6. Settlement — All 40 Scope Units
| ID | Settlement | Parent City | Target | Actual | Gap |
|---|---|---|---:|---:|---:|
| SETTLEMENT-001 | Bellmere | CITY-001 | 3 | 0 | 3 |
| SETTLEMENT-002 | Oakrest | CITY-001 | 3 | 0 | 3 |
| SETTLEMENT-003 | Rivergate | CITY-002 | 3 | 1 | 2 |
| SETTLEMENT-004 | Millhaven | CITY-002 | 3 | 0 | 3 |
| SETTLEMENT-005 | Wheatcross | CITY-003 | 3 | 0 | 3 |
| SETTLEMENT-006 | Sunfield | CITY-003 | 3 | 0 | 3 |
| SETTLEMENT-007 | Briarford | CITY-004 | 3 | 0 | 3 |
| SETTLEMENT-008 | Greenhollow | CITY-004 | 3 | 0 | 3 |
| SETTLEMENT-009 | Stonepass | CITY-005 | 3 | 0 | 3 |
| SETTLEMENT-010 | Highmere | CITY-005 | 3 | 0 | 3 |
| SETTLEMENT-011 | Valecrest | CITY-006 | 3 | 1 | 2 |
| SETTLEMENT-012 | Ironbrook | CITY-006 | 3 | 0 | 3 |
| SETTLEMENT-013 | Blackridge | CITY-007 | 3 | 0 | 3 |
| SETTLEMENT-014 | Redstone | CITY-007 | 3 | 0 | 3 |
| SETTLEMENT-015 | Pinewatch | CITY-008 | 3 | 0 | 3 |
| SETTLEMENT-016 | Coldmere | CITY-008 | 3 | 0 | 3 |
| SETTLEMENT-017 | Seabridge | CITY-009 | 3 | 0 | 3 |
| SETTLEMENT-018 | Tidemere | CITY-009 | 3 | 0 | 3 |
| SETTLEMENT-019 | Saltmere | CITY-010 | 3 | 1 | 2 |
| SETTLEMENT-020 | Gullhaven | CITY-010 | 3 | 0 | 3 |
| SETTLEMENT-021 | Pearlwatch | CITY-011 | 3 | 0 | 3 |
| SETTLEMENT-022 | Windrest | CITY-011 | 3 | 0 | 3 |
| SETTLEMENT-023 | Driftwood | CITY-012 | 3 | 0 | 3 |
| SETTLEMENT-024 | Stormbay | CITY-012 | 3 | 0 | 3 |
| SETTLEMENT-025 | Greenford | CITY-013 | 3 | 0 | 3 |
| SETTLEMENT-026 | Mossvale | CITY-013 | 3 | 0 | 3 |
| SETTLEMENT-027 | Oakmere | CITY-014 | 3 | 1 | 2 |
| SETTLEMENT-028 | Fernwatch | CITY-014 | 3 | 0 | 3 |
| SETTLEMENT-029 | Brookrest | CITY-015 | 3 | 0 | 3 |
| SETTLEMENT-030 | Alderbank | CITY-015 | 3 | 0 | 3 |
| SETTLEMENT-031 | Pinecross | CITY-016 | 3 | 0 | 3 |
| SETTLEMENT-032 | Thornrest | CITY-016 | 3 | 0 | 3 |
| SETTLEMENT-033 | Wellspring | CITY-017 | 3 | 0 | 3 |
| SETTLEMENT-034 | Datehaven | CITY-017 | 3 | 0 | 3 |
| SETTLEMENT-035 | Grassrest | CITY-018 | 3 | 1 | 2 |
| SETTLEMENT-036 | Herdwatch | CITY-018 | 3 | 0 | 3 |
| SETTLEMENT-037 | Dustgate | CITY-019 | 3 | 0 | 3 |
| SETTLEMENT-038 | Redwell | CITY-019 | 3 | 0 | 3 |
| SETTLEMENT-039 | Sandmere | CITY-020 | 3 | 0 | 3 |
| SETTLEMENT-040 | Farwatch | CITY-020 | 3 | 0 | 3 |
| **TOTAL** | | | **120** | **5** | **115** |

## 7. Faction / Noble House Assignment
| Assignment class | Primary assignments | Secondary contexts |
|---|---:|---:|
| Imperial factions | 5 | 0 |
| Kingdom factions | 15 | 5 |
| Noble Houses | 6 | 0 |
| **Total primary** | **26** | **5 secondary contexts** |

No new faction or Noble House was created for Batch 1.

## 8. Batch 1 Individual Audit
| NPC | Function | Geography | Faction context | Agency | Knowledge boundary | Origin | Result |
|---|---|---|---|---|---|---|---|
| NPC-022 Maren Vale | Rivergate river-traffic coordinator | SET-003 → CITY-002 → K-001 → E-001 | CITY-002 admin + Valedorn trade | Defined | Defined | Rivergate/local transport | PASS |
| NPC-023 Borin Keld | Valecrest supply/transport coordinator | SET-011 → CITY-006 → K-002 → E-001 | CITY-006 admin + mountain routes | Defined | Defined | Kharven transport network | PASS |
| NPC-024 Selene Varo | Saltmere salt/coastal supply manager | SET-019 → CITY-010 → K-003 → E-001 | CITY-010 admin + Mariselle trade | Defined | Defined | Coastal production community | PASS |
| NPC-025 Elira Fen | Oakmere agriculture/livestock manager | SET-027 → CITY-014 → K-004 → E-001 | CITY-014 admin + Sylvaran crafts | Defined | Defined | Silvan agricultural community | PASS |
| NPC-026 Rafiq Sahr | Grassrest pastoral/seasonal-trade coordinator | SET-035 → CITY-018 → K-005 → E-001 | CITY-018 admin + pastoral union | Defined | Defined | Sahr steppe pastoral community | PASS |

## 9. Batch 1 Canonization Gate
```text
[✓] Coverage need valid
[✓] Geography verified against Kingdom Geography Canon
[✓] City scope was previously 0
[✓] Settlement scope was previously 0
[✓] Kingdom overlap valid
[✓] Empire overlap valid
[✓] Existing faction contexts valid
[✓] No new faction required
[✓] Race IDs from active Race Canon
[✓] No duplicate role with existing relevant NPC
[✓] Material world function
[✓] Agency defined
[✓] Knowledge boundary defined
[✓] Origin defined
[✓] Current state defined
[✓] Authority boundaries respected
```

## 10. Recalculation Result
Batch 1 menambah **25 official geographic scope assignments**:
```text
5 NPC × (Empire + Kingdom + City + Settlement) = 20? 
```
Correction: setiap NPC memang memiliki empat geographic assignments, sehingga 5 NPC = **20** geographic assignments. Faction assignments adalah kolom terpisah dan tidak masuk 295. Dari baseline 45, official coverage menjadi **65**, bukan 70.

**Important correction:** registry sebelumnya mencatat `70 / 295` karena menghitung lima NPC sebagai +5 Empire +5 Kingdom +5 City +5 Settlement = +20, sehingga baseline 45 seharusnya menjadi **65**. Nilai 70 adalah arithmetic error. Official Canon scope coverage yang benar setelah Batch 1 adalah **65 / 295 = 22.03%**.

## 11. Corrected Official Scope Summary
| Scope | Before Batch 1 | Added | Correct After Batch 1 | Gap |
|---|---:|---:|---:|---:|
| Empire | 21 | +5 | **26** | 0 |
| Kingdom | 15 | +5 | **20** | 30 |
| City | 9 | +5 | **14** | 86 |
| Settlement | 0 | +5 | **5** | 115 |
| **Official total** | **45** | **+20** | **65** | **230** |

**Correct official progress: 65 / 295 = 22.03%.**

## 12. Admin Decision
Batch 1 passes individual design and Canonization Gate. NPC-022 through NPC-026 are now registered Canon NPCs.

The next batch must be reselected from the corrected gap data. The strongest immediate candidates remain the second settlements of the same five anchor cities, but they must be individually justified again before creation.

> **Coverage Gap Matrix menentukan di mana kekurangan berada; Geography, Population, Faction, Governance, dan fungsi dunia menentukan apakah NPC memang layak dibuat. Overlap adalah efisiensi Canon yang sah, bukan alasan untuk mengarang assignment.**
