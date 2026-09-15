# ELDORIA WORLD — CANON GEOGRAPHY REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.7
> **Purpose:** Registry resmi struktur geografis-politik Eldoria sebagai dasar settlement, population model, faction, dan Canon NPC.

## 1. Authority

File ini adalah registry struktur. Detail wilayah hanya menjadi Canon setelah ditetapkan oleh Admin atau sumber Canon yang sah.

```text
WORLD
└── 1 KEKAISARAN
    └── BEBERAPA KERAJAAN
        └── BEBERAPA KOTA
            └── BEBERAPA DESA / SETTLEMENT
```

## 2. Current Canon Coverage

```text
CONTINENT_COUNT: 1 (main continent)
EMPIRE_COUNT: 1
KINGDOM_COUNT: 5 (KINGDOM-001 through KINGDOM-005 established)
KINGDOM-001_REGION_COUNT: 4
KINGDOM-001_CITY_COUNT: 4
KINGDOM-001_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-001_POPULATION_MODEL: ACTIVE
KINGDOM-002_REGION_COUNT: 4
KINGDOM-002_CITY_COUNT: 4
KINGDOM-002_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-002_POPULATION_MODEL: ACTIVE
KINGDOM-003_REGION_COUNT: 4
KINGDOM-003_CITY_COUNT: 4
KINGDOM-003_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-003_POPULATION_MODEL: ACTIVE
KINGDOM-004_REGION_COUNT: 4
KINGDOM-004_CITY_COUNT: 4
KINGDOM-004_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-004_POPULATION_MODEL: ACTIVE
KINGDOM-005_REGION_COUNT: 4
KINGDOM-005_CITY_COUNT: 4
KINGDOM-005_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-005_POPULATION_MODEL: ACTIVE
KINGDOM-006+: PENDING
```

## 3. Empire Registry

### EMPIRE-001

```text
EMPIRE_ID: EMPIRE-001
NAME: Kekaisaran Valthera
TYPE: EMPIRE
CAPITAL: Aurelis
CONTINENT: Benua Utama Eldoria
BOUNDARY: ???
REGIONS: Kingdom-dependent; imperial macro-regions beyond current Canon = ???
CURRENT_STATE: Stabil secara administratif; kondisi politik internal rinci = ???
ORIGIN: ???
HISTORY: ???
```

### 3.1 Political Identity

```text
POLITICAL_SYSTEM: Monarki Kekaisaran Terdesentralisasi
HEAD_OF_STATE: Kaisar Valthera
CENTRAL_AUTHORITY: Pemerintahan Kekaisaran
KINGDOM_AUTONOMY: Internal governance permitted within Imperial law
IMPERIAL_SCOPE: Pertahanan bersama, hukum kekaisaran, hubungan antar-kerajaan, kepentingan strategis, dan urusan yang ditetapkan oleh hukum kekaisaran
LOCAL_SCOPE: Pemerintahan kerajaan dan administrasi lokal berada pada kerajaan masing-masing sesuai hukum yang berlaku
```

Nama pribadi Kaisar, struktur kementerian/dewan rinci, hukum spesifik, dan batas kewenangan yang belum ditetapkan tetap `???`.

### 3.2 Territorial Framework

```text
EMPIRE-001
    ↓
KINGDOM-001 — Valedorn
KINGDOM-002 — Brannor
KINGDOM-003 — Mariselle
KINGDOM-004 — Sylvaran
KINGDOM-005 — Sahrad
KINGDOM-006+ — future kingdoms, count open
```

Integrity rules:
1. Setiap Kingdom wajib memiliki `EMPIRE_ID: EMPIRE-001`.
2. Setiap Region wajib memiliki parent Kingdom yang valid.
3. Setiap City wajib memiliki `KINGDOM_ID` dan `REGION_ID` valid.
4. Setiap Settlement wajib memiliki `CITY_ID` dan `REGION_ID` valid kecuali Canon secara eksplisit menetapkan struktur lain.
5. Tidak ada Canon geography yang boleh menunjuk parent `???`.
6. Kingdom baru harus memiliki fungsi geografis/politik/ekonomi yang jelas dan tidak dibuat hanya untuk memenuhi quota NPC.

### 3.3 Empire Canon Boundaries

```text
EMPIRE_ID: EMPIRE-001
NAME: Kekaisaran Valthera
CAPITAL: Aurelis
CONTINENT: Benua Utama Eldoria
KINGDOMS: KINGDOM-001 through KINGDOM-005 + future kingdoms
MAJOR_REGIONS: ???
POLITICAL_SYSTEM: Monarki Kekaisaran Terdesentralisasi
RULER: Kaisar Valthera (nama pribadi: ???)
MILITARY_STRUCTURE: ???
ECONOMIC_STRUCTURE: ???
CULTURAL_PROFILE: ???
RELIGIOUS_STRUCTURE: ???
MAJOR_FACTIONS: ???
EXTERNAL_RELATIONS: ???
CURRENT_POLITICAL_STATE: Stabil secara administratif; detail politik aktif = ???
```

Population kekaisaran direpresentasikan secara agregat. Tidak ada kewajiban membuat file untuk setiap penduduk.

## 4. Kingdom Registry

### 4.1 KINGDOM-001 — Kerajaan Valedorn

```text
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Valedorn
TYPE: Kerajaan Heartland Agraris-Riverine
CAPITAL: Varenhold
REGIONS: REGION-001, REGION-002, REGION-003, REGION-004
```
Detail geography/population: `world/kingdoms/KINGDOM-001_GEOGRAPHY.md`.

### 4.2 KINGDOM-002 — Kerajaan Brannor

```text
KINGDOM_ID: KINGDOM-002
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Brannor
TYPE: Kerajaan Highland-Mineral
CAPITAL: Durnhaven
REGIONS: REGION-005, REGION-006, REGION-007, REGION-008
```
Detail geography/population: `world/kingdoms/KINGDOM-002_GEOGRAPHY.md`.

### 4.3 KINGDOM-003 — Kerajaan Mariselle

```text
KINGDOM_ID: KINGDOM-003
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Mariselle
TYPE: Kerajaan Coastal-Maritime
CAPITAL: Port Aureon
REGIONS: REGION-009, REGION-010, REGION-011, REGION-012
```
Detail geography/population: `world/kingdoms/KINGDOM-003_GEOGRAPHY.md`.

Mariselle menjadi pusat pesisir, pelabuhan, pelayaran, perikanan, perdagangan laut, galangan kapal, dan konektivitas antarpantai.

### 4.4 KINGDOM-004 — Kerajaan Sylvaran

```text
KINGDOM_ID: KINGDOM-004
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Sylvaran
TYPE: Kerajaan Forest-Border
CAPITAL: Elaris
REGIONS: REGION-013, REGION-014, REGION-015, REGION-016
```
Detail geography/population: `world/kingdoms/KINGDOM-004_GEOGRAPHY.md`.

Sylvaran menjadi wilayah hutan, sungai hulu, hasil hutan, pertanian, kerajinan, jalur darat, dan frontier ekologis.

### 4.5 KINGDOM-005 — Kerajaan Sahrad

```text
KINGDOM_ID: KINGDOM-005
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Sahrad
TYPE: Kerajaan Arid-Steppe
CAPITAL: Qasrane
REGIONS: REGION-017, REGION-018, REGION-019, REGION-020
```
Detail geography/population: `world/kingdoms/KINGDOM-005_GEOGRAPHY.md`.

Sahrad menjadi wilayah oasis, padang rumput kering, jalur kafilah, peternakan, perdagangan darat jarak jauh, dan frontier arid.

### 4.6 Future Kingdoms

```text
KINGDOM-006+: PENDING
```

Kerajaan berikutnya dibangun hanya jika diperlukan oleh desain dunia dan memiliki fungsi yang jelas.

## 5. City Registry

```text
KINGDOM-001:
CITY-001 → Varenhold → REGION-001
CITY-002 → Averen → REGION-002
CITY-003 → Goldmere → REGION-003
CITY-004 → Thornwick → REGION-004

KINGDOM-002:
CITY-005 → Durnhaven → REGION-005
CITY-006 → Kharhold → REGION-006
CITY-007 → Ferren → REGION-007
CITY-008 → Frostwatch → REGION-008

KINGDOM-003:
CITY-009 → Port Aureon → REGION-009
CITY-010 → Southport → REGION-010
CITY-011 → Azurehold → REGION-011
CITY-012 → Westhaven → REGION-012

KINGDOM-004:
CITY-013 → Elaris → REGION-013
CITY-014 → Sylford → REGION-014
CITY-015 → Riverwyn → REGION-015
CITY-016 → Wildmere → REGION-016

KINGDOM-005:
CITY-017 → Qasrane → REGION-017
CITY-018 → Sarakh → REGION-018
CITY-019 → Caravanser → REGION-019
CITY-020 → Sunscar → REGION-020
```

## 6. Village / Settlement Registry

```text
KINGDOM-001:
SETTLEMENT-001 → Bellmere → CITY-001 → REGION-001
SETTLEMENT-002 → Oakrest → CITY-001 → REGION-001
SETTLEMENT-003 → Rivergate → CITY-002 → REGION-002
SETTLEMENT-004 → Millhaven → CITY-002 → REGION-002
SETTLEMENT-005 → Wheatcross → CITY-003 → REGION-003
SETTLEMENT-006 → Sunfield → CITY-003 → REGION-003
SETTLEMENT-007 → Briarford → CITY-004 → REGION-004
SETTLEMENT-008 → Greenhollow → CITY-004 → REGION-004

KINGDOM-002:
SETTLEMENT-009 → Stonepass → CITY-005 → REGION-005
SETTLEMENT-010 → Highmere → CITY-005 → REGION-005
SETTLEMENT-011 → Valecrest → CITY-006 → REGION-006
SETTLEMENT-012 → Ironbrook → CITY-006 → REGION-006
SETTLEMENT-013 → Blackridge → CITY-007 → REGION-007
SETTLEMENT-014 → Redstone → CITY-007 → REGION-007
SETTLEMENT-015 → Pinewatch → CITY-008 → REGION-008
SETTLEMENT-016 → Coldmere → CITY-008 → REGION-008

KINGDOM-003:
SETTLEMENT-017 → Seabridge → CITY-009 → REGION-009
SETTLEMENT-018 → Tidemere → CITY-009 → REGION-009
SETTLEMENT-019 → Saltmere → CITY-010 → REGION-010
SETTLEMENT-020 → Gullhaven → CITY-010 → REGION-010
SETTLEMENT-021 → Pearlwatch → CITY-011 → REGION-011
SETTLEMENT-022 → Windrest → CITY-011 → REGION-011
SETTLEMENT-023 → Driftwood → CITY-012 → REGION-012
SETTLEMENT-024 → Stormbay → CITY-012 → REGION-012

KINGDOM-004:
SETTLEMENT-025 → Greenford → CITY-013 → REGION-013
SETTLEMENT-026 → Mossvale → CITY-013 → REGION-013
SETTLEMENT-027 → Oakmere → CITY-014 → REGION-014
SETTLEMENT-028 → Fernwatch → CITY-014 → REGION-014
SETTLEMENT-029 → Brookrest → CITY-015 → REGION-015
SETTLEMENT-030 → Alderbank → CITY-015 → REGION-015
SETTLEMENT-031 → Pinecross → CITY-016 → REGION-016
SETTLEMENT-032 → Thornrest → CITY-016 → REGION-016

KINGDOM-005:
SETTLEMENT-033 → Wellspring → CITY-017 → REGION-017
SETTLEMENT-034 → Datehaven → CITY-017 → REGION-017
SETTLEMENT-035 → Grassrest → CITY-018 → REGION-018
SETTLEMENT-036 → Herdwatch → CITY-018 → REGION-018
SETTLEMENT-037 → Dustgate → CITY-019 → REGION-019
SETTLEMENT-038 → Redwell → CITY-019 → REGION-019
SETTLEMENT-039 → Sandmere → CITY-020 → REGION-020
SETTLEMENT-040 → Farwatch → CITY-020 → REGION-020
```

## 7. Region Registry

```text
KINGDOM-001:
REGION-001 → Cekungan Varenhold
REGION-002 → Koridor Sungai Averen
REGION-003 → Dataran Ladang Emas
REGION-004 → Perbatasan Hutan Thorn

KINGDOM-002:
REGION-005 → Pegunungan Durn
REGION-006 → Lembah Kharven
REGION-007 → Punggung Besi
REGION-008 → Perbatasan Frostpine

KINGDOM-003:
REGION-009 → Teluk Aureon
REGION-010 → Pantai Selatan
REGION-011 → Kepulauan Azure
REGION-012 → Pesisir Barat

KINGDOM-004:
REGION-013 → Hutan Elaris
REGION-014 → Lembah Silvan
REGION-015 → Sungai Elden
REGION-016 → Perbatasan Wildmere

KINGDOM-005:
REGION-017 → Oasis Qasrane
REGION-018 → Padang Rumput Sahr
REGION-019 → Koridor Kafilah Timur
REGION-020 → Perbatasan Sunscar
```

## 8. Population Registry

Population Model adalah agregat; exact race percentages, migration balance, dan occupational percentages tetap `???` bila belum ditetapkan.

```text
KINGDOM-001 → POP-VAL-001 → RANGE 650,000–900,000 → ACTIVE
KINGDOM-002 → POP-BRA-001 → RANGE 450,000–700,000 → ACTIVE
KINGDOM-003 → POP-MAR-001 → RANGE 500,000–800,000 → ACTIVE
KINGDOM-004 → POP-SYL-001 → RANGE 400,000–650,000 → ACTIVE
KINGDOM-005 → POP-SAH-001 → RANGE 300,000–500,000 → ACTIVE
```

Detail regional distribution dan population logic berada di masing-masing Kingdom Geography file.

## 9. Parent-Child Integrity

```text
EMPIRE-001
↓
KINGDOM-001..005
↓
REGION-001..020
↓
CITY-001..020
↓
SETTLEMENT-001..040
```

Setiap child memiliki parent Canon yang valid. Tidak ada parent `???` pada struktur yang telah didaftarkan.

## 10. Canon NPC Build Gate

```text
CANON GEOGRAPHY
→ POPULATION MODEL
→ SETTLEMENT CONTEXT
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum coverage:
```text
DESA → ≥ 3 Canon NPC
KOTA → ≥ 5 Canon NPC
KERAJAAN → ≥ 10 Canon NPC per kingdom
KEKAISARAN → ≥ 25 Canon NPC
```

Kingdom-001 through Kingdom-005 geography dan Population Model sekarang tersedia. Canon NPC belum dibangun.

## 11. Canon Safety

- Semua Kingdom-001 through Kingdom-005 resmi berada di bawah EMPIRE-001.
- Semua Region, City, dan Settlement terdaftar adalah Admin Canon.
- Population Model tidak membuat penduduk massal menjadi file individual.
- `???` tetap Unknown/Unresolved dan tidak boleh ditebak AI GM.
- Race tidak boleh ditebak dari nama, penampilan, lokasi, class, faction, atau stereotype.
- Dynamic NPC tidak otomatis menjadi Canon NPC.
- Perubahan struktur geography Canon adalah kewenangan Admin.

## 12. Construction Status

```text
PHASE 1 — STRUCTURE: COMPLETE
PHASE 2 — EMPIRE IDENTITY: COMPLETE
PHASE 3 — KINGDOM-001 GEOGRAPHY + POPULATION: COMPLETE
PHASE 4 — KINGDOM-002 GEOGRAPHY + POPULATION: COMPLETE
PHASE 5 — KINGDOM-003 IDENTITY + GEOGRAPHY + POPULATION: COMPLETE
PHASE 6 — KINGDOM-004 IDENTITY + GEOGRAPHY + POPULATION: COMPLETE
PHASE 7 — KINGDOM-005 IDENTITY + GEOGRAPHY + POPULATION: COMPLETE
PHASE 8 — FACTION / GOVERNANCE CONTEXT: PENDING
PHASE 9 — CANON NPC KINGDOM-001..005: NEXT AFTER FACTION/GOVERNANCE CONTEXT
```

## 13. Final Principle

> **Bangun hierarchy geography terlebih dahulu, kemudian Population Model, lalu faction/governance context dan Canon NPC. Kingdom baru hanya dibuat setelah memiliki fungsi geografis, politik, ekonomi, dan population model yang masuk akal.**
