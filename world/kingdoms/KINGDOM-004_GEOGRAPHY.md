# ELDORIA WORLD — KINGDOM-004 GEOGRAPHY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-004 — Kerajaan Sylvaran
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi Region → City → Village/Settlement → Population Model untuk Kingdom-004.

## 1. Scope
File ini adalah extension Canon geografis untuk `KINGDOM-004`. Semua parent identity harus mengarah ke entity yang sudah resmi di `world/CANON_GEOGRAPHY.md`.

## 2. Administrative Hierarchy
```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-004 — Kerajaan Sylvaran
    ├── REGION-013 — Hutan Elaris
    │   └── CITY-013 — Elaris
    │       ├── SETTLEMENT-025 — Greenford
    │       └── SETTLEMENT-026 — Mossvale
    ├── REGION-014 — Lembah Silvan
    │   └── CITY-014 — Sylford
    │       ├── SETTLEMENT-027 — Oakmere
    │       └── SETTLEMENT-028 — Fernwatch
    ├── REGION-015 — Sungai Elden
    │   └── CITY-015 — Riverwyn
    │       ├── SETTLEMENT-029 — Brookrest
    │       └── SETTLEMENT-030 — Alderbank
    └── REGION-016 — Perbatasan Wildmere
        └── CITY-016 — Wildmere
            ├── SETTLEMENT-031 — Pinecross
            └── SETTLEMENT-032 — Thornrest
```

## 3. Region Registry

### REGION-013 — Hutan Elaris
```text
REGION_ID: REGION-013
PARENT_ID: KINGDOM-004
NAME: Hutan Elaris
TYPE: Forest Administrative Core
TERRAIN: Hutan lebat, bukaan hutan, jalur darat berhutan
CLIMATE: Temperate forest
BOUNDARY: Kawasan hutan inti yang mengelilingi Elaris; batas fisik rinci = ???
CURRENT_STATE: Aktif sebagai pusat hutan dan pengelolaan sumber daya; kondisi ekologi dan keamanan = ???
ORIGIN: Berkembang dari jaringan permukiman hutan dan pusat pengelolaan sumber daya
HISTORY: ???
```
**Regional role:** kehutanan, hasil hutan, perburuan, kerajinan, dan jalur hutan.

### REGION-014 — Lembah Silvan
```text
REGION_ID: REGION-014
PARENT_ID: KINGDOM-004
NAME: Lembah Silvan
TYPE: Forest Valley
TERRAIN: Lembah, lereng berhutan, aliran sungai, lahan pertanian
CLIMATE: Temperate
BOUNDARY: Koridor lembah dan permukiman yang terhubung di antara kawasan hutan; batas fisik rinci = ???
CURRENT_STATE: Produktif; kondisi pertanian, transportasi, dan settlement = ???
ORIGIN: Berkembang dari jaringan permukiman lembah dan jalur darat lokal
HISTORY: ???
```
**Regional role:** pertanian, peternakan, kerajinan, perdagangan lokal, dan konektivitas lembah.

### REGION-015 — Sungai Elden
```text
REGION_ID: REGION-015
PARENT_ID: KINGDOM-004
NAME: Sungai Elden
TYPE: River Corridor
TERRAIN: Lembah sungai luas, tepian hutan, lahan pertanian, jalur air
CLIMATE: Temperate
BOUNDARY: Koridor Sungai Elden dan kawasan ekonomi yang bergantung pada sungai; batas fisik rinci = ???
CURRENT_STATE: Aktif; kondisi transportasi sungai, pertanian, dan perdagangan = ???
ORIGIN: Berkembang sebagai jalur air dan pusat penggilingan serta perdagangan
HISTORY: ???
```
**Regional role:** transportasi sungai, pertanian, penggilingan, kerajinan, dan perdagangan.

### REGION-016 — Perbatasan Wildmere
```text
REGION_ID: REGION-016
PARENT_ID: KINGDOM-004
NAME: Perbatasan Wildmere
TYPE: Remote Forest Frontier
TERRAIN: Hutan dalam, dataran tinggi tidak rata, jalur frontier
CLIMATE: Variable temperate
BOUNDARY: Zona frontier menuju kawasan Wildmere; batas eksternal dan ancaman = ???
CURRENT_STATE: Settled but frontier-sensitive; kondisi keamanan, wildlife, dan monster pressure = ???
ORIGIN: Berkembang dari perluasan settlement dan jalur penjagaan frontier
HISTORY: ???
```
**Regional role:** kehutanan, perburuan, keamanan jalur, settlement frontier, dan suplai wilayah terpencil.

## 4. City Registry

### CITY-013 — Elaris
```text
CITY_ID: CITY-013
KINGDOM_ID: KINGDOM-004
REGION_ID: REGION-013
NAME: Elaris
TYPE: Kingdom Capital / Forest City
BOUNDARY: ???
CURRENT_STATE: Stabil; detail administrasi, perdagangan hutan, dan keamanan = ???
ORIGIN: Pusat administrasi dan perdagangan hasil hutan Sylvaran
HISTORY: ???
```
**Role:** pusat kerajaan, administrasi, perdagangan hasil hutan, kerajinan, dan konektivitas.

### CITY-014 — Sylford
```text
CITY_ID: CITY-014
KINGDOM_ID: KINGDOM-004
REGION_ID: REGION-014
NAME: Sylford
TYPE: Valley City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail pertanian, peternakan, dan perdagangan = ???
ORIGIN: Berkembang sebagai pusat lembah dan pertukaran lokal
HISTORY: ???
```
**Role:** pasar lembah, pertanian, peternakan, kerajinan, dan distribusi.

### CITY-015 — Riverwyn
```text
CITY_ID: CITY-015
KINGDOM_ID: KINGDOM-004
REGION_ID: REGION-015
NAME: Riverwyn
TYPE: River Trade City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail perdagangan sungai dan penggilingan = ???
ORIGIN: Tumbuh di sepanjang Sungai Elden sebagai pusat transportasi dan produksi
HISTORY: ???
```
**Role:** perdagangan sungai, penggilingan, pertanian, transportasi, dan kerajinan.

### CITY-016 — Wildmere
```text
CITY_ID: CITY-016
KINGDOM_ID: KINGDOM-004
REGION_ID: REGION-016
NAME: Wildmere
TYPE: Frontier City
BOUNDARY: ???
CURRENT_STATE: Stabil tetapi frontier-sensitive; detail ancaman dan keamanan = ???
ORIGIN: Pos frontier dan logistik yang berkembang menjadi pusat regional
HISTORY: ???
```
**Role:** logistik frontier, kehutanan, keamanan jalur, dan perdagangan lokal.

## 5. Village / Settlement Registry

### SETTLEMENT-025 — Greenford
```text
SETTLEMENT_ID: SETTLEMENT-025
CITY_ID: CITY-013
REGION_ID: REGION-013
NAME: Greenford
TYPE: Forest-Edge Village
CURRENT_STATE: Productive; farming and forestry conditions = ???
ORIGIN: Settlement tepian hutan yang memasok Elaris
HISTORY: ???
```

### SETTLEMENT-026 — Mossvale
```text
SETTLEMENT_ID: SETTLEMENT-026
CITY_ID: CITY-013
REGION_ID: REGION-013
NAME: Mossvale
TYPE: Woodland Village
CURRENT_STATE: Active; hunting, forestry, and craft conditions = ???
ORIGIN: Settlement pemanfaatan sumber daya hutan dekat pusat Elaris
HISTORY: ???
```

### SETTLEMENT-027 — Oakmere
```text
SETTLEMENT_ID: SETTLEMENT-027
CITY_ID: CITY-014
REGION_ID: REGION-014
NAME: Oakmere
TYPE: Valley Agricultural Village
CURRENT_STATE: Productive; harvest and livestock condition = ???
ORIGIN: Settlement pertanian dan peternakan di Lembah Silvan
HISTORY: ???
```

### SETTLEMENT-028 — Fernwatch
```text
SETTLEMENT_ID: SETTLEMENT-028
CITY_ID: CITY-014
REGION_ID: REGION-014
NAME: Fernwatch
TYPE: Forest-Valley Settlement
CURRENT_STATE: Active; route security and resource access = ???
ORIGIN: Settlement penjagaan jalur dan pemanfaatan hutan lembah
HISTORY: ???
```

### SETTLEMENT-029 — Brookrest
```text
SETTLEMENT_ID: SETTLEMENT-029
CITY_ID: CITY-015
REGION_ID: REGION-015
NAME: Brookrest
TYPE: River Village
CURRENT_STATE: Productive; farming, fishing, and milling condition = ???
ORIGIN: Settlement di sepanjang jaringan air Sungai Elden
HISTORY: ???
```

### SETTLEMENT-030 — Alderbank
```text
SETTLEMENT_ID: SETTLEMENT-030
CITY_ID: CITY-015
REGION_ID: REGION-015
NAME: Alderbank
TYPE: Riverbank Village
CURRENT_STATE: Active; transport, agriculture, and crafts = ???
ORIGIN: Settlement tepian sungai untuk transportasi dan produksi lokal
HISTORY: ???
```

### SETTLEMENT-031 — Pinecross
```text
SETTLEMENT_ID: SETTLEMENT-031
CITY_ID: CITY-016
REGION_ID: REGION-016
NAME: Pinecross
TYPE: Frontier Village
CURRENT_STATE: Frontier-active; security and wildlife pressure = ???
ORIGIN: Settlement di persimpangan jalur frontier dan hutan
HISTORY: ???
```

### SETTLEMENT-032 — Thornrest
```text
SETTLEMENT_ID: SETTLEMENT-032
CITY_ID: CITY-016
REGION_ID: REGION-016
NAME: Thornrest
TYPE: Remote Frontier Settlement
CURRENT_STATE: Active; supply, weather, and wildlife pressure = ???
ORIGIN: Settlement terpencil untuk mendukung jalur dan suplai frontier
HISTORY: ???
```

## 6. Population Model
### 6.1 Kingdom-Level Model
```text
KINGDOM_ID: KINGDOM-004
POPULATION_MODEL_ID: POP-SYL-001
TOTAL_POPULATION: RANGE 400,000–650,000
URBANIZATION: LOW-MODERATE
PRIMARY_POPULATION_BASE: FORESTRY + AGRICULTURE + RIVER TRADE + CRAFTS
RACE_CATEGORIES: ONLY ACTIVE RACE_CANON_ID FROM races/CANON_REGISTRY.md
EXACT_RACE_PERCENTAGES: ???
MIGRATION_BALANCE: ???
SEASONAL_MOBILITY: MODERATE
```

### 6.2 Regional Distribution
```text
REGION-013 Hutan Elaris       → 25–30% of kingdom population
REGION-014 Lembah Silvan      → 25–30%
REGION-015 Sungai Elden       → 25–30%
REGION-016 Perbatasan Wildmere→ 15–20%
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
FORESTRY / RESOURCE GATHERING → MAJOR SHARE, REGION-DEPENDENT
AGRICULTURE / LIVESTOCK       → SIGNIFICANT SHARE
TRADE / TRANSPORT             → SIGNIFICANT SHARE
CRAFT / PROCESSING            → SIGNIFICANT SHARE
SERVICES / ADMINISTRATION     → MODERATE SHARE
SECURITY / FRONTIER            → MODERATE SHARE
HUNTING                        → REGION-DEPENDENT
OTHER                          → REMAINDER
```
Exact percentages remain `???` until an economy/faction model requires a more precise local distribution.

### 6.5 Race Distribution Rule
Population Model boleh mengelompokkan penduduk berdasarkan Race Canon, tetapi:
- hanya `RACE_CANON_ID` aktif yang terdaftar di `races/CANON_REGISTRY.md`;
- tidak boleh membuat ras baru untuk mengisi populasi;
- persentase ras lokal tetap `???` sampai ditetapkan oleh Admin Canon atau model migrasi/populasi yang sah;
- Race tidak otomatis menentukan class, profession, faction, morality, personality, atau outcome;
- migration dapat mengubah komposisi lokal tanpa mengubah Race Canon.

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
KINGDOM-004
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
Canon NPC untuk Kingdom-004 belum dibuat dalam file ini.

## 8. Canon Safety
- Semua Region, City, dan Settlement di file ini memiliki parent Canon yang valid.
- Nama dan identity di sini adalah Admin Canon.
- `???` tetap unresolved dan tidak boleh diisi oleh AI GM tanpa source yang sah.
- Population Model adalah agregat, bukan daftar penduduk individual.
- Race distribution tidak boleh ditebak dari nama settlement atau karakteristik visual.
- Kingdom-005 tidak dibangun di file ini.
