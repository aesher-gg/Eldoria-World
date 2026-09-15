# ELDORIA WORLD — KINGDOM-005 GEOGRAPHY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-005 — Kerajaan Sahrad
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi Region → City → Village/Settlement → Population Model untuk Kingdom-005.

## 1. Scope
File ini adalah extension Canon geografis untuk `KINGDOM-005`. Semua parent identity harus mengarah ke entity yang sudah resmi di `world/CANON_GEOGRAPHY.md`.

## 2. Administrative Hierarchy
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

## 3. Region Registry
### REGION-017 — Oasis Qasrane
```text
REGION_ID: REGION-017
PARENT_ID: KINGDOM-005
NAME: Oasis Qasrane
TYPE: Oasis Urban Core
TERRAIN: Cekungan oasis, lahan pertanian, dataran kering sekeliling
CLIMATE: Arid
BOUNDARY: Kawasan oasis yang menjadi inti Qasrane; kapasitas air dan batas fisik rinci = ???
CURRENT_STATE: Aktif sebagai pusat air, pertanian, perdagangan, dan administrasi; kondisi sumber air = ???
ORIGIN: Berkembang dari jaringan oasis, pertanian, dan jalur perdagangan
HISTORY: ???
```
**Regional role:** sumber air, pertanian oasis, administrasi, pasar, dan perdagangan.

### REGION-018 — Padang Rumput Sahr
```text
REGION_ID: REGION-018
PARENT_ID: KINGDOM-005
NAME: Padang Rumput Sahr
TYPE: Steppe Pastoral Belt
TERRAIN: Padang rumput terbuka, dataran kering, jalur penggembalaan
CLIMATE: Semi-arid with seasonal variation
BOUNDARY: Zona padang rumput dan jalur penggembalaan Sahr; batas grazing rinci = ???
CURRENT_STATE: Aktif; kondisi padang rumput, ternak, dan mobilitas musiman = ???
ORIGIN: Berkembang dari jaringan pastoralism dan settlement musiman
HISTORY: ???
```
**Regional role:** peternakan, penggembalaan, perdagangan lokal, transportasi, dan suplai ternak.

### REGION-019 — Koridor Kafilah Timur
```text
REGION_ID: REGION-019
PARENT_ID: KINGDOM-005
NAME: Koridor Kafilah Timur
TYPE: Long-Distance Trade Corridor
TERRAIN: Dataran kering, rute berbatu, titik istirahat kafilah
CLIMATE: Arid / semi-arid
BOUNDARY: Koridor perdagangan darat utama menuju arah timur; endpoint, rute, dan bahaya = ???
CURRENT_STATE: Aktif secara ekonomi; keamanan kafilah, suplai, dan kondisi rute = ???
ORIGIN: Berkembang dari jaringan jalur kafilah dan settlement perdagangan
HISTORY: ???
```
**Regional role:** perdagangan jarak jauh, caravan services, gudang, kerajinan, transportasi, dan keamanan rute.

### REGION-020 — Perbatasan Sunscar
```text
REGION_ID: REGION-020
PARENT_ID: KINGDOM-005
NAME: Perbatasan Sunscar
TYPE: Remote Dry Frontier
TERRAIN: Gurun berbatu, semak kering, titik air terisolasi
CLIMATE: Arid
BOUNDARY: Zona frontier kering menuju luar Sahrad; batas eksternal dan hubungan luar = ???
CURRENT_STATE: Settled but frontier-sensitive; kondisi patroli, air, cuaca, dan keamanan = ???
ORIGIN: Berkembang dari settlement frontier, peternakan, dan pengawasan jalur
HISTORY: ???
```
**Regional role:** patroli, penggembalaan, monitoring rute, logistik frontier, dan pengawasan titik air.

## 4. City Registry
### CITY-017 — Qasrane
```text
CITY_ID: CITY-017
KINGDOM_ID: KINGDOM-005
REGION_ID: REGION-017
NAME: Qasrane
TYPE: Kingdom Capital / Oasis City
BOUNDARY: ???
CURRENT_STATE: Stabil; detail administrasi, air, pertanian, dan perdagangan = ???
ORIGIN: Pusat oasis yang berkembang menjadi ibu kota dan pusat perdagangan
HISTORY: ???
```
**Role:** administrasi kerajaan, pengelolaan air, pertanian oasis, pasar, dan perdagangan.

### CITY-018 — Sarakh
```text
CITY_ID: CITY-018
KINGDOM_ID: KINGDOM-005
REGION_ID: REGION-018
NAME: Sarakh
TYPE: Steppe City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail pastoral trade, livestock, dan crafts = ???
ORIGIN: Berkembang sebagai pusat perdagangan dan administrasi padang rumput
HISTORY: ???
```
**Role:** perdagangan ternak, pasar, kerajinan, jasa transportasi, dan distribusi.

### CITY-019 — Caravanser
```text
CITY_ID: CITY-019
KINGDOM_ID: KINGDOM-005
REGION_ID: REGION-019
NAME: Caravanser
TYPE: Caravan City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail perdagangan, gudang, dan keamanan rute = ???
ORIGIN: Tumbuh dari jaringan caravanserai dan jalur perdagangan jarak jauh
HISTORY: ???
```
**Role:** perdagangan jarak jauh, logistik, gudang, perbaikan, dan jasa kafilah.

### CITY-020 — Sunscar
```text
CITY_ID: CITY-020
KINGDOM_ID: KINGDOM-005
REGION_ID: REGION-020
NAME: Sunscar
TYPE: Frontier City
BOUNDARY: ???
CURRENT_STATE: Stabil tetapi frontier-sensitive; detail keamanan dan suplai = ???
ORIGIN: Pos frontier dan route monitoring yang berkembang menjadi pusat regional
HISTORY: ???
```
**Role:** pengawasan frontier, logistik, keamanan rute, dan perdagangan lokal.

## 5. Village / Settlement Registry
### SETTLEMENT-033 — Wellspring
```text
SETTLEMENT_ID: SETTLEMENT-033
CITY_ID: CITY-017
REGION_ID: REGION-017
NAME: Wellspring
TYPE: Oasis Village
CURRENT_STATE: Productive; water management and farming condition = ???
ORIGIN: Settlement sekitar sumber air dan pertanian oasis
HISTORY: ???
```

### SETTLEMENT-034 — Datehaven
```text
SETTLEMENT_ID: SETTLEMENT-034
CITY_ID: CITY-017
REGION_ID: REGION-017
NAME: Datehaven
TYPE: Oasis Village
CURRENT_STATE: Active; agriculture, livestock, and food processing = ???
ORIGIN: Settlement pertanian oasis dan pengolahan pangan
HISTORY: ???
```

### SETTLEMENT-035 — Grassrest
```text
SETTLEMENT_ID: SETTLEMENT-035
CITY_ID: CITY-018
REGION_ID: REGION-018
NAME: Grassrest
TYPE: Steppe Village
CURRENT_STATE: Active; herding, seasonal trade, and supply conditions = ???
ORIGIN: Settlement pendukung penggembalaan dan jalur musiman
HISTORY: ???
```

### SETTLEMENT-036 — Herdwatch
```text
SETTLEMENT_ID: SETTLEMENT-036
CITY_ID: CITY-018
REGION_ID: REGION-018
NAME: Herdwatch
TYPE: Pastoral Settlement
CURRENT_STATE: Productive; livestock and transport condition = ???
ORIGIN: Settlement pastoral yang berkembang di jalur penggembalaan
HISTORY: ???
```

### SETTLEMENT-037 — Dustgate
```text
SETTLEMENT_ID: SETTLEMENT-037
CITY_ID: CITY-019
REGION_ID: REGION-019
NAME: Dustgate
TYPE: Caravan Village
CURRENT_STATE: Active; caravan services, repair, and trade = ???
ORIGIN: Settlement jasa kafilah pada jalur timur
HISTORY: ???
```

### SETTLEMENT-038 — Redwell
```text
SETTLEMENT_ID: SETTLEMENT-038
CITY_ID: CITY-019
REGION_ID: REGION-019
NAME: Redwell
TYPE: Route Settlement
CURRENT_STATE: Active; water access, livestock, and logistics = ???
ORIGIN: Titik air dan perhentian rute kafilah
HISTORY: ???
```

### SETTLEMENT-039 — Sandmere
```text
SETTLEMENT_ID: SETTLEMENT-039
CITY_ID: CITY-020
REGION_ID: REGION-020
NAME: Sandmere
TYPE: Frontier Village
CURRENT_STATE: Frontier-active; herding, farming, and route services = ???
ORIGIN: Settlement frontier yang mendukung peternakan dan jalur kering
HISTORY: ???
```

### SETTLEMENT-040 — Farwatch
```text
SETTLEMENT_ID: SETTLEMENT-040
CITY_ID: CITY-020
REGION_ID: REGION-020
NAME: Farwatch
TYPE: Remote Frontier Settlement
CURRENT_STATE: Active; watch duty, livestock, supply, and weather = ???
ORIGIN: Settlement terpencil untuk pengawasan dan dukungan logistik frontier
HISTORY: ???
```

## 6. Population Model
### 6.1 Kingdom-Level Model
```text
KINGDOM_ID: KINGDOM-005
POPULATION_MODEL_ID: POP-SAH-001
TOTAL_POPULATION: RANGE 300,000–500,000
URBANIZATION: LOW
PRIMARY_POPULATION_BASE: CARAVAN TRADE + PASTORALISM + OASIS AGRICULTURE + CRAFTS
RACE_CATEGORIES: ONLY ACTIVE RACE_CANON_ID FROM races/CANON_REGISTRY.md
EXACT_RACE_PERCENTAGES: ???
MIGRATION_BALANCE: ???
SEASONAL_MOBILITY: HIGH
```

### 6.2 Regional Distribution
```text
REGION-017 Oasis Qasrane       → 25–30% of kingdom population
REGION-018 Padang Rumput Sahr  → 25–30%
REGION-019 Koridor Kafilah Timur→ 25–30%
REGION-020 Perbatasan Sunscar  → 15–20%
```
Persentase adalah rentang model, bukan jumlah individu tetap. Distribusi aktual dapat berubah melalui migration, birth/death, disaster, war, economy, dan world events yang tervalidasi.

### 6.3 Settlement Scale Bands
```text
KINGDOM CAPITAL / MAJOR CITY → 40,000–120,000
SECONDARY CITY               → 15,000–60,000
LARGE VILLAGE                → 2,000–8,000
SMALL VILLAGE                → 300–2,000
FRONTIER SETTLEMENT          → 200–3,000
```
Band digunakan sebagai model skala, bukan angka otomatis untuk setiap settlement.

### 6.4 Occupational Distribution
```text
CARAVAN TRADE / TRANSPORT → MAJOR SHARE
PASTORALISM / LIVESTOCK   → SIGNIFICANT SHARE
OASIS AGRICULTURE / FOOD  → SIGNIFICANT SHARE
CRAFT / PROCESSING        → SIGNIFICANT SHARE
SERVICES / ADMINISTRATION → MODERATE SHARE
SECURITY / FRONTIER       → MODERATE SHARE
WATER / RESOURCE WORK     → REGION-DEPENDENT
OTHER                     → REMAINDER
```
Exact percentages remain `???` until an economy/faction model requires a more precise local distribution.

### 6.5 Race Distribution Rule
Population Model boleh mengelompokkan penduduk berdasarkan Race Canon, tetapi hanya Race Canon aktif yang terdaftar. Tidak boleh membuat ras baru untuk mengisi populasi. Persentase ras lokal tetap `???` sampai ditetapkan secara sah. Race tidak otomatis menentukan class, profession, faction, morality, personality, atau outcome.

### 6.6 Dynamic NPC Generation Boundary
```text
POPULATION MODEL
↓
LOCAL CONTEXT
↓
DYNAMIC NPC GENERATION
↓
RACE_CANON_ID FROM RACE REGISTRY
↓
PERSIST ONLY IF MATERIAL
```
Dynamic NPC tidak otomatis menjadi Canon NPC.

## 7. Geography → Population → NPC Gate
```text
KINGDOM-005
↓
REGION
↓
CITY
↓
VILLAGE / SETTLEMENT
↓
POPULATION MODEL
↓
FACTION / GOVERNANCE CONTEXT
↓
CANON NPC
```
Canon NPC untuk Kingdom-005 belum dibuat dalam file ini.

## 8. Canon Safety
- Semua Region, City, dan Settlement memiliki parent Canon yang valid.
- `???` tetap unresolved dan tidak boleh diisi AI GM tanpa source sah.
- Population Model adalah agregat.
- Race distribution tidak boleh ditebak dari nama settlement atau karakteristik visual.
- Kingdom-001 tidak dibangun di file ini.
