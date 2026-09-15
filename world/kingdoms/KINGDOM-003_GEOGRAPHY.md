# ELDORIA WORLD — KINGDOM-003 GEOGRAPHY

> **Authority:** Admin
> **Canon:** Admin Canon v1.1
> **Kingdom:** KINGDOM-003 — Kerajaan Mariselle
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi Region → City → Village/Settlement → Population Model untuk Kingdom-003.

## 1. Scope
File ini adalah extension Canon geografis untuk `KINGDOM-003`. Semua parent identity harus mengarah ke entity yang sudah resmi di `world/CANON_GEOGRAPHY.md`.

## 2. Administrative Hierarchy
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

## 3. Region Registry

### REGION-009 — Teluk Aureon
```text
REGION_ID: REGION-009
PARENT_ID: KINGDOM-003
NAME: Teluk Aureon
TYPE: Coastal Urban / Trade Core
TERRAIN: Dataran pesisir, teluk, muara sungai
CLIMATE: Maritime
BOUNDARY: Kawasan teluk dan dataran pesisir yang menjadi inti Port Aureon; batas fisik rinci = ???
CURRENT_STATE: Aktif secara ekonomi; kapasitas pelabuhan, arus, dan pertahanan = ???
ORIGIN: Berkembang sebagai pusat pelabuhan dan perdagangan laut
HISTORY: ???
```
Regional role: pelabuhan utama, perdagangan maritim, perikanan, administrasi, dan konektivitas pesisir.

### REGION-010 — Pantai Selatan
```text
REGION_ID: REGION-010
PARENT_ID: KINGDOM-003
NAME: Pantai Selatan
TYPE: Coastal Production Belt
TERRAIN: Pantai, dataran rendah, estuari
CLIMATE: Maritime-warm
BOUNDARY: Sabuk pesisir selatan yang mendukung perikanan, garam, dan pertanian; batas fisik rinci = ???
CURRENT_STATE: Produktif; kondisi perikanan, garam, pertanian, dan transportasi = ???
ORIGIN: Berkembang dari jaringan desa pesisir dan produksi pantai
HISTORY: ???
```
Regional role: perikanan, produksi garam, pertanian pesisir, transportasi, dan suplai kota.

### REGION-011 — Kepulauan Azure
```text
REGION_ID: REGION-011
PARENT_ID: KINGDOM-003
NAME: Kepulauan Azure
TYPE: Island Maritime Zone
TERRAIN: Pulau, terumbu, selat, perairan antarpulau
CLIMATE: Maritime
BOUNDARY: Zona kepulauan dan jalur laut antarpulau; jumlah pulau, batas, dan bahaya terumbu = ???
CURRENT_STATE: Aktif; kondisi navigasi, perdagangan, dan perikanan = ???
ORIGIN: Berkembang dari jaringan pulau dan rute pelayaran antarpulau
HISTORY: ???
```
Regional role: perdagangan antarpulau, perikanan, navigasi, jasa kapal, dan konektivitas maritim.

### REGION-012 — Pesisir Barat
```text
REGION_ID: REGION-012
PARENT_ID: KINGDOM-003
NAME: Pesisir Barat
TYPE: Frontier Coast
TERRAIN: Tebing, teluk kecil, hutan pesisir, jalur pantai
CLIMATE: Maritime-variable
BOUNDARY: Zona pesisir barat yang berbatasan dengan kawasan frontier; batas fisik rinci = ???
CURRENT_STATE: Settled but storm-exposed; ancaman cuaca dan keamanan = ???
ORIGIN: Berkembang dari settlement pesisir, kehutanan, dan jalur pantai
HISTORY: ???
```
Regional role: perikanan, kehutanan, jalur pesisir, logistik, dan settlement frontier.

## 4. City Registry
### CITY-009 — Port Aureon
```text
CITY_ID: CITY-009
KINGDOM_ID: KINGDOM-003
REGION_ID: REGION-009
NAME: Port Aureon
TYPE: Kingdom Capital / Major Port
BOUNDARY: ???
CURRENT_STATE: Stabil; detail administrasi, perdagangan, dan keamanan pelabuhan = ???
ORIGIN: Pusat pemerintahan dan pelabuhan utama Mariselle
HISTORY: ???
```
Role: administrasi kerajaan, pelabuhan utama, perdagangan, pelayaran, dan jasa maritim.

### CITY-010 — Southport
```text
CITY_ID: CITY-010
KINGDOM_ID: KINGDOM-003
REGION_ID: REGION-010
NAME: Southport
TYPE: Secondary Coastal City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail perikanan, garam, pertanian, dan transportasi = ???
ORIGIN: Berkembang sebagai pusat produksi dan transportasi Pantai Selatan
HISTORY: ???
```
Role: perikanan, garam, pertanian, perdagangan pesisir, dan transportasi.

### CITY-011 — Azurehold
```text
CITY_ID: CITY-011
KINGDOM_ID: KINGDOM-003
REGION_ID: REGION-011
NAME: Azurehold
TYPE: Island City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail navigasi, perdagangan antarpulau, dan perikanan = ???
ORIGIN: Berkembang sebagai pusat kepulauan dan navigasi Azure
HISTORY: ???
```
Role: navigasi, perdagangan antarpulau, perikanan, jasa kapal, dan distribusi maritim.

### CITY-012 — Westhaven
```text
CITY_ID: CITY-012
KINGDOM_ID: KINGDOM-003
REGION_ID: REGION-012
NAME: Westhaven
TYPE: Frontier Coastal City
BOUNDARY: ???
CURRENT_STATE: Stabil tetapi frontier-sensitive; detail keamanan dan cuaca = ???
ORIGIN: Pos perdagangan dan keamanan pesisir barat yang berkembang menjadi kota
HISTORY: ???
```
Role: keamanan pesisir, perikanan, kehutanan, logistik, dan rute pantai.

## 5. Village / Settlement Registry
### SETTLEMENT-017 — Seabridge
```text
SETTLEMENT_ID: SETTLEMENT-017
CITY_ID: CITY-009
REGION_ID: REGION-009
NAME: Seabridge
TYPE: Coastal Village
CURRENT_STATE: Active; fishing and harbor-support activity = ???
ORIGIN: Settlement pesisir yang mendukung Port Aureon
HISTORY: ???
```
### SETTLEMENT-018 — Tidemere
```text
SETTLEMENT_ID: SETTLEMENT-018
CITY_ID: CITY-009
REGION_ID: REGION-009
NAME: Tidemere
TYPE: Estuary Village
CURRENT_STATE: Productive; fisheries, processing, and coastal agriculture = ???
ORIGIN: Settlement di sekitar muara dan kegiatan perikanan
HISTORY: ???
```
### SETTLEMENT-019 — Saltmere
```text
SETTLEMENT_ID: SETTLEMENT-019
CITY_ID: CITY-010
REGION_ID: REGION-010
NAME: Saltmere
TYPE: Salt / Coastal Village
CURRENT_STATE: Active; salt production and fishing conditions = ???
ORIGIN: Settlement produksi garam dan perikanan Pantai Selatan
HISTORY: ???
```
### SETTLEMENT-020 — Gullhaven
```text
SETTLEMENT_ID: SETTLEMENT-020
CITY_ID: CITY-010
REGION_ID: REGION-010
NAME: Gullhaven
TYPE: Fishing Village
CURRENT_STATE: Productive; fisheries and boat services = ???
ORIGIN: Settlement perikanan yang memasok Southport
HISTORY: ???
```
### SETTLEMENT-021 — Pearlwatch
```text
SETTLEMENT_ID: SETTLEMENT-021
CITY_ID: CITY-011
REGION_ID: REGION-011
NAME: Pearlwatch
TYPE: Island Village
CURRENT_STATE: Active; fishing and navigation support = ???
ORIGIN: Settlement pulau pada jaringan Kepulauan Azure
HISTORY: ???
```
### SETTLEMENT-022 — Windrest
```text
SETTLEMENT_ID: SETTLEMENT-022
CITY_ID: CITY-011
REGION_ID: REGION-011
NAME: Windrest
TYPE: Island Settlement
CURRENT_STATE: Active; livestock, fishing, and maritime logistics = ???
ORIGIN: Settlement pulau yang mendukung lalu lintas maritim
HISTORY: ???
```
### SETTLEMENT-023 — Driftwood
```text
SETTLEMENT_ID: SETTLEMENT-023
CITY_ID: CITY-012
REGION_ID: REGION-012
NAME: Driftwood
TYPE: Forest-Coast Village
CURRENT_STATE: Active; forestry, fishing, and crafts = ???
ORIGIN: Settlement pertemuan hutan pesisir dan jalur laut
HISTORY: ???
```
### SETTLEMENT-024 — Stormbay
```text
SETTLEMENT_ID: SETTLEMENT-024
CITY_ID: CITY-012
REGION_ID: REGION-012
NAME: Stormbay
TYPE: Frontier Village
CURRENT_STATE: Frontier-active; storm exposure, fishing, and route watch = ???
ORIGIN: Settlement pesisir yang berkembang sebagai titik perlindungan dan pengawasan rute
HISTORY: ???
```

## 6. Population Model
```text
KINGDOM_ID: KINGDOM-003
POPULATION_MODEL_ID: POP-MAR-001
TOTAL_POPULATION: RANGE 500,000–800,000
URBANIZATION: MODERATE
PRIMARY_POPULATION_BASE: MARITIME TRADE + FISHERIES + COASTAL AGRICULTURE + SHIPBUILDING
RACE_CATEGORIES: ONLY ACTIVE RACE_CANON_ID FROM races/CANON_REGISTRY.md
EXACT_RACE_PERCENTAGES: ???
MIGRATION_BALANCE: ???
SEASONAL_MOBILITY: HIGH
```

### Regional Distribution
```text
REGION-009 → 25–30%
REGION-010 → 25–30%
REGION-011 → 15–20%
REGION-012 → 20–25%
```

### Settlement Scale Bands
```text
KINGDOM CAPITAL / MAJOR CITY → 40,000–120,000
SECONDARY CITY               → 15,000–60,000
LARGE VILLAGE                → 2,000–8,000
SMALL VILLAGE                → 300–2,000
FRONTIER SETTLEMENT          → 200–3,000
```

### Occupational Distribution
```text
MARITIME TRADE / SHIPPING → MAJOR SHARE, REGION-DEPENDENT
FISHERIES / AQUATIC WORK  → SIGNIFICANT SHARE
AGRICULTURE / FOOD        → SIGNIFICANT SHARE
CRAFT / SHIPBUILDING      → SIGNIFICANT SHARE
SERVICES / ADMINISTRATION → MODERATE SHARE
SECURITY / COASTAL WATCH  → MODERATE SHARE
FORESTRY / RESOURCE WORK  → REGION-DEPENDENT
OTHER                     → REMAINDER
```
Exact percentages remain `???` until an economy/faction model requires a more precise local distribution.

### Race Distribution Rule
Population Model hanya menggunakan Race Canon aktif. Tidak boleh membuat ras baru. Persentase ras lokal tetap `???` sampai ditetapkan secara sah. Race tidak otomatis menentukan class, profession, faction, morality, personality, atau outcome.

### Dynamic NPC Generation Boundary
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

## 7. Geography → Population → NPC Gate
```text
KINGDOM-003
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
Canon NPC untuk Kingdom-003 belum dibuat dalam file ini.

## 8. Canon Safety
- Semua Region, City, dan Settlement memiliki parent Canon yang valid.
- `???` tetap unresolved dan tidak boleh diisi AI GM tanpa source sah.
- Population Model adalah agregat.
- Race distribution tidak boleh ditebak dari nama settlement atau karakteristik visual.
- Kingdom-004 tidak dibangun di file ini.
