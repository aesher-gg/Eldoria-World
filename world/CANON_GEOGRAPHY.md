# ELDORIA WORLD — CANON GEOGRAPHY REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.5
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
KINGDOM_COUNT: 2+ (KINGDOM-001 and KINGDOM-002 established; future count remains open)
KINGDOM-001_REGION_COUNT: 4
KINGDOM-001_CITY_COUNT: 4
KINGDOM-001_VILLAGE_SETTLEMENT_COUNT: 8
KINGDOM-001_POPULATION_MODEL: ACTIVE
KINGDOM-002_GEOGRAPHY: PENDING
KINGDOM-002_POPULATION_MODEL: PENDING
KINGDOM-003+: PENDING
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

### 3.1 Empire Identity

Kekaisaran Valthera adalah satu-satunya entitas kekaisaran utama dalam struktur politik Canon Eldoria dan menjadi otoritas politik tertinggi atas kerajaan-kerajaan di bawahnya. Aurelis adalah ibu kota kekaisaran.

### 3.2 Political Identity

```text
POLITICAL_SYSTEM: Monarki Kekaisaran Terdesentralisasi
HEAD_OF_STATE: Kaisar Valthera
CENTRAL_AUTHORITY: Pemerintahan Kekaisaran
KINGDOM_AUTONOMY: Internal governance permitted within Imperial law
IMPERIAL_SCOPE: Pertahanan bersama, hukum kekaisaran, hubungan antar-kerajaan, kepentingan strategis, dan urusan yang ditetapkan oleh hukum kekaisaran
LOCAL_SCOPE: Pemerintahan kerajaan dan administrasi lokal berada pada kerajaan masing-masing sesuai hukum yang berlaku
```

Nama pribadi Kaisar, struktur kementerian/dewan rinci, hukum spesifik, dan batas kewenangan yang belum ditetapkan tetap `???`.

### 3.3 Administrative Framework

```text
KEKAISARAN VALTHERA
        │
        ├── Otoritas Imperial
        │
        └── KERAJAAN
              │
              ├── Pemerintahan Kerajaan
              │
              └── KOTA
                    │
                    └── DESA / SETTLEMENT
```

### 3.4 Territorial Framework

```text
EMPIRE-001
    ↓
KINGDOM-001 — Valedorn
KINGDOM-002 — Brannor
KINGDOM-003 ... KINGDOM-???
```

Integrity rules:

1. Setiap Kingdom wajib memiliki `EMPIRE_ID: EMPIRE-001`.
2. Setiap Region wajib memiliki parent Kingdom yang valid.
3. Setiap City wajib memiliki `KINGDOM_ID` dan `REGION_ID` valid.
4. Setiap Settlement wajib memiliki `CITY_ID` dan `REGION_ID` valid kecuali Canon secara eksplisit menetapkan struktur lain.
5. Tidak ada Canon geography yang boleh menunjuk parent `???`.
6. Jumlah Kingdom tidak dibuat hanya untuk memenuhi quota NPC.

### 3.5 Imperial Authority Boundary

Domain prinsipil tingkat kekaisaran:

- legitimasi dan hukum kekaisaran,
- pertahanan dan keamanan strategis tingkat kekaisaran,
- hubungan resmi antar-kerajaan,
- kepentingan strategis lintas kerajaan,
- urusan lain yang ditetapkan Canon Imperial.

Domain kerajaan dan lokal tetap berada pada pemerintahan masing-masing selama tidak bertentangan dengan kewenangan imperial yang sah.

### 3.6 Empire Canon Boundaries

```text
EMPIRE_ID: EMPIRE-001
NAME: Kekaisaran Valthera
CAPITAL: Aurelis
CONTINENT: Benua Utama Eldoria
KINGDOMS: KINGDOM-001 + KINGDOM-002 + future kingdoms (count open)
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

### 3.7 Empire Population Boundary

Population kekaisaran direpresentasikan secara agregat. Population Model dibangun bertahap setelah geography Kingdom/Region/City/Settlement tersedia. Tidak ada kewajiban membuat file untuk setiap penduduk.

### 3.8 Empire Construction Rule

```text
EMPIRE-001
↓
KINGDOM
↓
REGION / CITY / SETTLEMENT
↓
POPULATION MODEL
↓
CANON NPC
```

## 4. Kingdom Registry

### 4.1 KINGDOM-001 — Kerajaan Valedorn

```text
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Valedorn
TYPE: Kerajaan Heartland Agraris-Riverine
CAPITAL: Varenhold
BOUNDARY: Heartland tengah Valthera; detail batas fisik dibangun melalui Region Canon
REGIONS: REGION-001, REGION-002, REGION-003, REGION-004
CURRENT_STATE: Stabil; detail politik, keamanan, dan ekonomi aktif = ???
ORIGIN: Berkembang sebagai kerajaan agraris dan jalur sungai yang kemudian berada di bawah struktur Kekaisaran Valthera; detail sejarah pendirian = ???
HISTORY: ???
```

Valedorn berfungsi sebagai heartland pangan, perdagangan darat, koridor sungai, dan konektivitas internal. Karakter regional: **subur, produktif, terhubung, dan pragmatis**.

Detail Region → City → Village/Settlement → Population Model berada di `world/kingdoms/KINGDOM-001_GEOGRAPHY.md`.

### 4.2 KINGDOM-002 — Kerajaan Brannor

```text
KINGDOM_ID: KINGDOM-002
EMPIRE_ID: EMPIRE-001
NAME: Kerajaan Brannor
TYPE: Kerajaan Highland-Mineral
CAPITAL: Durnhaven
BOUNDARY: Wilayah dataran tinggi dan pegunungan di luar heartland Valedorn; batas fisik rinci = ???
REGIONS: PENDING
CURRENT_STATE: Stabil secara administratif; kondisi keamanan, politik, dan ekonomi aktif = ???
ORIGIN: Berkembang sebagai pusat dataran tinggi, sumber daya mineral, dan jalur lintas pegunungan; detail pendirian = ???
HISTORY: ???
```

Brannor menjadi pelengkap geografis Valedorn melalui fungsi dataran tinggi, pegunungan, mineral, jalur lintas pegunungan, perdagangan, dan frontier transport.

Detail Region → City → Village/Settlement → Population Model Brannor belum dibuat.

### 4.3 Future Kingdoms

```text
KINGDOM-003: ???
KINGDOM-004: ???
...
```

Kerajaan berikutnya dibangun satu per satu berdasarkan fungsi geografis, politik, ekonomi, dan karakter yang berbeda atau saling melengkapi dengan Kingdom yang sudah ada.

## 5. City Registry

Current Canon City Registry Kingdom-001:

```text
CITY-001 → Varenhold → REGION-001 → KINGDOM-001
CITY-002 → Averen → REGION-002 → KINGDOM-001
CITY-003 → Goldmere → REGION-003 → KINGDOM-001
CITY-004 → Thornwick → REGION-004 → KINGDOM-001
```

Detail City Canon Kingdom-001 berada pada `world/kingdoms/KINGDOM-001_GEOGRAPHY.md`.

Kingdom-002 City Registry: `PENDING`.

## 6. Village / Settlement Registry

Current Canon Settlement Registry Kingdom-001:

```text
SETTLEMENT-001 → Bellmere     → CITY-001 → REGION-001
SETTLEMENT-002 → Oakrest      → CITY-001 → REGION-001
SETTLEMENT-003 → Rivergate    → CITY-002 → REGION-002
SETTLEMENT-004 → Millhaven    → CITY-002 → REGION-002
SETTLEMENT-005 → Wheatcross   → CITY-003 → REGION-003
SETTLEMENT-006 → Sunfield     → CITY-003 → REGION-003
SETTLEMENT-007 → Briarford    → CITY-004 → REGION-004
SETTLEMENT-008 → Greenhollow  → CITY-004 → REGION-004
```

Kingdom-002 Settlement Registry: `PENDING`.

## 7. Region Registry

Current Canon Region Registry Kingdom-001:

```text
REGION-001 → Cekungan Varenhold       → KINGDOM-001
REGION-002 → Koridor Sungai Averen    → KINGDOM-001
REGION-003 → Dataran Ladang Emas      → KINGDOM-001
REGION-004 → Perbatasan Hutan Thorn   → KINGDOM-001
```

Kingdom-002 Region Registry: `PENDING`.

## 8. Parent-Child Integrity

```text
EMPIRE-001
↓
KINGDOM-001 / KINGDOM-002 → existing EMPIRE-001
↓
REGION → existing parent Kingdom
↓
CITY → existing Kingdom + Region
↓
SETTLEMENT → existing City + Region
```

Tidak ada Region/City/Settlement Kingdom-002 yang boleh dianggap Canon sampai parent geography-nya dibuat secara resmi.

## 9. Population Boundary

Population Model menangani penduduk massal secara agregat. Tidak semua penduduk menjadi Canon NPC atau record individual.

Kingdom-001 memiliki Population Model aktif:

```text
POPULATION_MODEL_ID: POP-VAL-001
TOTAL_POPULATION: RANGE 650,000–900,000
URBANIZATION: MODERATE
PRIMARY_POPULATION_BASE: AGRICULTURAL + RIVERINE
EXACT_RACE_PERCENTAGES: ???
MIGRATION_BALANCE: ???
SEASONAL_MOBILITY: MODERATE
```

Regional distribution model Kingdom-001:

```text
REGION-001 → 20–25%
REGION-002 → 20–25%
REGION-003 → 35–40%
REGION-004 → 15–20%
```

Exact race percentages tetap `???`; hanya Race Canon aktif dari `races/CANON_REGISTRY.md` yang boleh dipakai sebagai racial category.

Kingdom-002 Population Model: `PENDING`.

## 10. Canon NPC Build Gate

```text
CANON GEOGRAPHY
→ POPULATION MODEL
→ SETTLEMENT CONTEXT
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum Canon NPC:

```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC per kingdom
KEKAISARAN → ≥ 25 Canon NPC
```

Kingdom-001 geography dan population model tersedia; Canon NPC belum dibangun.
Kingdom-002 harus menyelesaikan geography dan population model sebelum Canon NPC wilayah dibangun.

## 11. Canon Safety

- `Kekaisaran Valthera`, `Aurelis`, `Monarki Kekaisaran Terdesentralisasi`, `Kerajaan Valedorn`, `Varenhold`, `Kerajaan Brannor`, dan `Durnhaven` adalah Canon resmi.
- Region/City/Settlement Kingdom-001 yang tercantum adalah Admin Canon.
- Kingdom-002 belum memiliki Region/City/Village Canon.
- `???` tetap Unknown/Unresolved dan tidak boleh ditebak AI GM.
- Population Model tidak membuat individu massal menjadi file repository.
- Race tidak boleh ditebak dari nama, penampilan, lokasi, class, faction, atau stereotype.
- Dynamic NPC tidak otomatis menjadi Canon NPC.
- Perubahan struktur geography Canon adalah kewenangan Admin.

## 12. Construction Status

```text
PHASE 1 — STRUCTURE: COMPLETE
PHASE 2 — EMPIRE IDENTITY: COMPLETE
PHASE 3 — KINGDOM-001 IDENTITY: COMPLETE
PHASE 4 — KINGDOM-001 REGIONS: COMPLETE
PHASE 5 — KINGDOM-001 CITIES: COMPLETE
PHASE 6 — KINGDOM-001 VILLAGES / SETTLEMENTS: COMPLETE
PHASE 7 — KINGDOM-001 POPULATION MODEL: COMPLETE
PHASE 8 — KINGDOM-001 CANON NPC: READY / NOT YET BUILT
PHASE 9 — KINGDOM-002 IDENTITY: COMPLETE
PHASE 10 — KINGDOM-002 REGIONS: NEXT
PHASE 11 — KINGDOM-002 CITIES: PENDING
PHASE 12 — KINGDOM-002 VILLAGES / SETTLEMENTS: PENDING
PHASE 13 — KINGDOM-002 POPULATION MODEL: PENDING
```

## 13. Final Principle

> **Bangun hierarchy geography terlebih dahulu, kemudian Population Model, lalu faction/governance context dan Canon NPC. Kingdom baru hanya dibuat setelah memiliki fungsi geografis, politik, ekonomi, dan regional yang sah.**
