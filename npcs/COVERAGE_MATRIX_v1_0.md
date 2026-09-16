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

Coverage aktual dihitung dari field yang benar-benar tercatat pada setiap Canon NPC:

```text
NPC
├── EMPIRE_ID       → Empire coverage
├── KINGDOM_ID      → Kingdom coverage
├── CITY_ID         → City coverage
├── SETTLEMENT_ID   → Settlement coverage
└── FACTION / HOUSE → Faction / Noble House assignment
```

`???` tidak dihitung sebagai coverage.

Satu NPC dapat menghitung pada beberapa kolom. Ini adalah **scope assignment**, bukan jumlah NPC unik.

## Current Audited Coverage — 2026-09-16

| Coverage column | Actual | Target | Gap |
|---|---:|---:|---:|
| Empire | **21** | ≥25 | **4** |
| Kingdom | **15** | ≥50 | **35** |
| City | **9** | ≥100 | **91** |
| Settlement | **0** | ≥120 | **120** |
| Faction / Noble House | **21 assignments** | No numeric target in v1.0 | — |
| **Official scope coverage** | **45** | **≥295** | **250** |

**Official scope coverage progress: 45 / 295 = 15.25%.**

## Empire Coverage

| ID | Name | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| EMPIRE-001 | Kekaisaran Valthera | 25 | 21 | 4 | NPC-CANON-001–021 |

## Kingdom Coverage

| ID | Kingdom | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| KINGDOM-001 | Valedorn | 10 | 3 | 7 | NPC-006, 012, 017 |
| KINGDOM-002 | Brannor | 10 | 3 | 7 | NPC-007, 013, 018 |
| KINGDOM-003 | Mariselle | 10 | 3 | 7 | NPC-008, 014, 019 |
| KINGDOM-004 | Sylvaran | 10 | 3 | 7 | NPC-009, 015, 020 |
| KINGDOM-005 | Sahrad | 10 | 3 | 7 | NPC-010, 016, 021 |
| **TOTAL** | | **50** | **15** | **35** | |

## City Coverage — 20 Scope Units

| ID | City | Target | Actual | Gap | Supporting NPCs |
|---|---|---:|---:|---:|---|
| CITY-001 | Varenhold | 5 | 1 | 4 | NPC-012 |
| CITY-002 | Averen | 5 | 0 | 5 | — |
| CITY-003 | Goldmere | 5 | 1 | 4 | NPC-006 |
| CITY-004 | Thornwick | 5 | 0 | 5 | — |
| CITY-005 | Durnhaven | 5 | 1 | 4 | NPC-013 |
| CITY-006 | Kharhold | 5 | 0 | 5 | — |
| CITY-007 | Ferren | 5 | 1 | 4 | NPC-007 |
| CITY-008 | Frostwatch | 5 | 0 | 5 | — |
| CITY-009 | Port Aureon | 5 | 2 | 3 | NPC-008, 014 |
| CITY-010 | Southport | 5 | 0 | 5 | — |
| CITY-011 | Azurehold | 5 | 0 | 5 | — |
| CITY-012 | Westhaven | 5 | 0 | 5 | — |
| CITY-013 | Elaris | 5 | 2 | 3 | NPC-009, 015 |
| CITY-014 | Sylford | 5 | 0 | 5 | — |
| CITY-015 | Riverwyn | 5 | 0 | 5 | — |
| CITY-016 | Wildmere | 5 | 0 | 5 | — |
| CITY-017 | Qasrane | 5 | 1 | 4 | NPC-016 |
| CITY-018 | Sarakh | 5 | 0 | 5 | — |
| CITY-019 | Caravanser | 5 | 0 | 5 | — |
| CITY-020 | Sunscar | 5 | 0 | 5 | — |
| **TOTAL** | | **100** | **9** | **91** | |

## Settlement Coverage — 40 Scope Units

> Semua `SETTLEMENT_ID` yang belum tercatat sebagai assignment Canon tetap **0 coverage**. NPC dengan `SETTLEMENT_ID: ???` tidak dihitung.

| ID | Settlement | Parent City | Target | Actual | Gap |
|---|---|---|---:|---:|---:|
| SETTLEMENT-001 | Bellmere | CITY-001 Varenhold | 3 | 0 | 3 |
| SETTLEMENT-002 | Oakrest | CITY-001 Varenhold | 3 | 0 | 3 |
| SETTLEMENT-003 | Rivergate | CITY-002 Averen | 3 | 0 | 3 |
| SETTLEMENT-004 | Millhaven | CITY-002 Averen | 3 | 0 | 3 |
| SETTLEMENT-005 | Wheatcross | CITY-003 Goldmere | 3 | 0 | 3 |
| SETTLEMENT-006 | Sunfield | CITY-003 Goldmere | 3 | 0 | 3 |
| SETTLEMENT-007 | Briarford | CITY-004 Thornwick | 3 | 0 | 3 |
| SETTLEMENT-008 | Greenhollow | CITY-004 Thornwick | 3 | 0 | 3 |
| SETTLEMENT-009 | Stonepass | CITY-005 Durnhaven | 3 | 0 | 3 |
| SETTLEMENT-010 | Highmere | CITY-005 Durnhaven | 3 | 0 | 3 |
| SETTLEMENT-011 | Valecrest | CITY-006 Kharhold | 3 | 0 | 3 |
| SETTLEMENT-012 | Ironbrook | CITY-006 Kharhold | 3 | 0 | 3 |
| SETTLEMENT-013 | Blackridge | CITY-007 Ferren | 3 | 0 | 3 |
| SETTLEMENT-014 | Redstone | CITY-007 Ferren | 3 | 0 | 3 |
| SETTLEMENT-015 | Pinewatch | CITY-008 Frostwatch | 3 | 0 | 3 |
| SETTLEMENT-016 | Coldmere | CITY-008 Frostwatch | 3 | 0 | 3 |
| SETTLEMENT-017 | Seabridge | CITY-009 Port Aureon | 3 | 0 | 3 |
| SETTLEMENT-018 | Tidemere | CITY-009 Port Aureon | 3 | 0 | 3 |
| SETTLEMENT-019 | Saltmere | CITY-010 Southport | 3 | 0 | 3 |
| SETTLEMENT-020 | Gullhaven | CITY-010 Southport | 3 | 0 | 3 |
| SETTLEMENT-021 | Pearlwatch | CITY-011 Azurehold | 3 | 0 | 3 |
| SETTLEMENT-022 | Windrest | CITY-011 Azurehold | 3 | 0 | 3 |
| SETTLEMENT-023 | Driftwood | CITY-012 Westhaven | 3 | 0 | 3 |
| SETTLEMENT-024 | Stormbay | CITY-012 Westhaven | 3 | 0 | 3 |
| SETTLEMENT-025 | Greenford | CITY-013 Elaris | 3 | 0 | 3 |
| SETTLEMENT-026 | Mossvale | CITY-013 Elaris | 3 | 0 | 3 |
| SETTLEMENT-027 | Oakmere | CITY-014 Sylford | 3 | 0 | 3 |
| SETTLEMENT-028 | Fernwatch | CITY-014 Sylford | 3 | 0 | 3 |
| SETTLEMENT-029 | Brookrest | CITY-015 Riverwyn | 3 | 0 | 3 |
| SETTLEMENT-030 | Alderbank | CITY-015 Riverwyn | 3 | 0 | 3 |
| SETTLEMENT-031 | Pinecross | CITY-016 Wildmere | 3 | 0 | 3 |
| SETTLEMENT-032 | Thornrest | CITY-016 Wildmere | 3 | 0 | 3 |
| SETTLEMENT-033 | Wellspring | CITY-017 Qasrane | 3 | 0 | 3 |
| SETTLEMENT-034 | Datehaven | CITY-017 Qasrane | 3 | 0 | 3 |
| SETTLEMENT-035 | Grassrest | CITY-018 Sarakh | 3 | 0 | 3 |
| SETTLEMENT-036 | Herdwatch | CITY-018 Sarakh | 3 | 0 | 3 |
| SETTLEMENT-037 | Dustgate | CITY-019 Caravanser | 3 | 0 | 3 |
| SETTLEMENT-038 | Redwell | CITY-019 Caravanser | 3 | 0 | 3 |
| SETTLEMENT-039 | Sandmere | CITY-020 Sunscar | 3 | 0 | 3 |
| SETTLEMENT-040 | Farwatch | CITY-020 Sunscar | 3 | 0 | 3 |
| **TOTAL** | | | **120** | **0** | **120** |

## Faction / Noble House Assignment Audit

Faction/House assignment dihitung sebagai kolom tersendiri dan tidak ditambahkan ke 295 official scope target.

| Assignment class | Actual assignments | Canon context |
|---|---:|---|
| Imperial factions | 5 | FACTION-001, FACTION-002, FACTION-003 |
| Kingdom factions | 5 | FACTION-101, 104, 111, 113, 121, 124, 131, 133, 141, 143 as applicable |
| Noble Houses | 6 | NOBLE-HOUSE-009, 002, 004, 006, 008, 010 |
| **Total NPC faction/house assignments** | **21** | Every registered NPC has a faction assignment |

> Catatan: angka `21` adalah **assignment NPC**, bukan jumlah faction/house unik. Registry faction Canon saat ini memiliki lebih banyak faction daripada yang terwakili oleh 21 NPC.

## Coverage Gap Interpretation

### Critical gaps

1. **Settlement:** 40/40 scope units masih 0 coverage.
2. **City:** 13/20 cities masih 0 coverage.
3. **Kingdom:** seluruh 5 kingdoms masih berada di bawah minimum 10.
4. **Empire:** masih kurang 4 assignment untuk minimum 25.

### Existing cross-scope opportunities

NPC dengan `CITY_ID` dan `KINGDOM_ID` sudah menghasilkan coverage berlapis yang sah karena field tersebut memang tercatat dalam registry. NPC dengan `SETTLEMENT_ID: ???` tidak boleh dipaksa masuk ke settlement tertentu.

### Creation rule

Gap tidak otomatis berarti NPC harus dibuat. Setiap kandidat harus memiliki fungsi nyata, agency, lokasi, faction context bila relevan, Race Canon, knowledge boundary, dan Origin yang dapat diverifikasi. Overlap hanya boleh digunakan bila secara substantif benar, bukan untuk mengejar quota.

## Audit Conclusion

```text
CANON NPC UNIQUE: 21
EMPIRE COVERAGE: 21 / 25
KINGDOM COVERAGE: 15 / 50
CITY COVERAGE: 9 / 100
SETTLEMENT COVERAGE: 0 / 120
FACTION / HOUSE ASSIGNMENTS: 21
OFFICIAL SCOPE COVERAGE: 45 / 295
OFFICIAL COVERAGE PROGRESS: 15.25%
OFFICIAL SCOPE COVERAGE GAP: 250
```

Coverage Matrix adalah alat pemerataan kebutuhan Canon NPC. Ia tidak boleh menjadi sumber lore atau alasan untuk membuat NPC filler.
