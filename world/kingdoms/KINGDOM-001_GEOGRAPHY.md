# ELDORIA WORLD — KINGDOM-001 GEOGRAPHY

> **Authority:** Admin
> **Canon:** Admin Canon v1.0
> **Kingdom:** KINGDOM-001 — Kerajaan Valedorn
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi Region → City → Village/Settlement → Population Model untuk Kingdom-001.

## 1. Scope

File ini adalah extension Canon geografis untuk `KINGDOM-001`. Semua parent identity harus mengarah ke entity yang sudah resmi di `world/CANON_GEOGRAPHY.md`.

```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-001 — Kerajaan Valedorn
    ├── REGION-001 — Cekungan Varenhold
    │   └── CITY-001 — Varenhold
    │       ├── SETTLEMENT-001 — Bellmere
    │       └── SETTLEMENT-002 — Oakrest
    ├── REGION-002 — Koridor Sungai Averen
    │   └── CITY-002 — Averen
    │       ├── SETTLEMENT-003 — Rivergate
    │       └── SETTLEMENT-004 — Millhaven
    ├── REGION-003 — Dataran Ladang Emas
    │   └── CITY-003 — Goldmere
    │       ├── SETTLEMENT-005 — Wheatcross
    │       └── SETTLEMENT-006 — Sunfield
    └── REGION-004 — Perbatasan Hutan Thorn
        └── CITY-004 — Thornwick
            ├── SETTLEMENT-007 — Briarford
            └── SETTLEMENT-008 — Greenhollow
```

## 2. Region Registry

### REGION-001 — Cekungan Varenhold

```text
REGION_ID: REGION-001
PARENT_ID: KINGDOM-001
NAME: Cekungan Varenhold
TYPE: Capital Basin
TERRAIN: Dataran sungai, lahan pertanian, tepian sungai
CLIMATE: Temperate, seasonal
BOUNDARY: Cekungan dan jaringan lahan produktif yang mengelilingi Varenhold
CURRENT_STATE: Stabil; detail keamanan dan politik lokal = ???
ORIGIN: Berkembang sebagai pusat administratif dan perdagangan Kingdom-001
HISTORY: ???
```

**Regional role:** pusat pemerintahan, distribusi, pasar, jasa, dan konektivitas kerajaan.

### REGION-002 — Koridor Sungai Averen

```text
REGION_ID: REGION-002
PARENT_ID: KINGDOM-001
NAME: Koridor Sungai Averen
TYPE: River Trade Corridor
TERRAIN: Sungai utama, dataran banjir, tepian hutan dan lahan pertanian
CLIMATE: Temperate, humid near river
BOUNDARY: Jalur sungai dan settlement yang bergantung pada transportasi air
CURRENT_STATE: Aktif secara ekonomi; kondisi keamanan sungai = ???
ORIGIN: Tumbuh dari jalur transportasi sungai dan perdagangan antarwilayah
HISTORY: ???
```

**Regional role:** transportasi air, perdagangan, penggilingan, gudang, dan distribusi pangan.

### REGION-003 — Dataran Ladang Emas

```text
REGION_ID: REGION-003
PARENT_ID: KINGDOM-001
NAME: Dataran Ladang Emas
TYPE: Agricultural Heartland
TERRAIN: Dataran luas, ladang, kanal irigasi, padang rumput
CLIMATE: Temperate, seasonal dry/wet cycle
BOUNDARY: Zona produksi pertanian utama di bagian pedalaman Valedorn
CURRENT_STATE: Produktif; risiko panen, cuaca, dan keamanan = ???
ORIGIN: Berkembang sebagai pusat produksi pangan kerajaan
HISTORY: ???
```

**Regional role:** produksi gandum dan pangan umum, peternakan, tenaga kerja agraris, dan suplai kota.

### REGION-004 — Perbatasan Hutan Thorn

```text
REGION_ID: REGION-004
PARENT_ID: KINGDOM-001
NAME: Perbatasan Hutan Thorn
TYPE: Frontier Woodland
TERRAIN: Hutan campuran, perbukitan rendah, sungai kecil, jalan frontier
CLIMATE: Temperate, wetter woodland conditions
BOUNDARY: Zona transisi antara lahan kerajaan dan kawasan hutan frontier
CURRENT_STATE: Settled but frontier-sensitive; monster/wildlife pressure = ???
ORIGIN: Berkembang dari perluasan permukiman dan jalur frontier kerajaan
HISTORY: ???
```

**Regional role:** kayu, hasil hutan, berburu, frontier settlement, dan jalur keamanan darat.

## 3. City Registry

### CITY-001 — Varenhold

```text
CITY_ID: CITY-001
KINGDOM_ID: KINGDOM-001
REGION_ID: REGION-001
NAME: Varenhold
TYPE: Kingdom Capital
BOUNDARY: ???
CURRENT_STATE: Stabil; detail pemerintahan kota = ???
ORIGIN: Pusat pemerintahan dan pasar utama Valedorn
HISTORY: ???
```

Role: pusat kerajaan, administrasi, pasar, layanan, dan distribusi.

### CITY-002 — Averen

```text
CITY_ID: CITY-002
KINGDOM_ID: KINGDOM-001
REGION_ID: REGION-002
NAME: Averen
TYPE: River Trade City
BOUNDARY: ???
CURRENT_STATE: Aktif; detail keamanan dan perdagangan = ???
ORIGIN: Tumbuh di sepanjang Koridor Sungai Averen
HISTORY: ???
```

Role: pelabuhan sungai, perdagangan, gudang, penggilingan, dan transportasi.

### CITY-003 — Goldmere

```text
CITY_ID: CITY-003
KINGDOM_ID: KINGDOM-001
REGION_ID: REGION-003
NAME: Goldmere
TYPE: Agricultural Market City
BOUNDARY: ???
CURRENT_STATE: Produktif; detail pasar dan pajak = ???
ORIGIN: Berkembang sebagai pusat pasar hasil pertanian pedalaman
HISTORY: ???
```

Role: pasar hasil panen, pengolahan pangan, peternakan, dan distribusi ke kota lain.

### CITY-004 — Thornwick

```text
CITY_ID: CITY-004
KINGDOM_ID: KINGDOM-001
REGION_ID: REGION-004
NAME: Thornwick
TYPE: Frontier City
BOUNDARY: ???
CURRENT_STATE: Stabil tetapi memiliki tekanan frontier; detail ancaman = ???
ORIGIN: Pos permukiman dan perdagangan yang berkembang menjadi pusat frontier
HISTORY: ???
```

Role: pertahanan lokal, perdagangan hasil hutan, jasa frontier, dan penghubung wilayah luar.

## 4. Village / Settlement Registry

### SETTLEMENT-001 — Bellmere

```text
SETTLEMENT_ID: SETTLEMENT-001
CITY_ID: CITY-001
REGION_ID: REGION-001
NAME: Bellmere
TYPE: Agricultural Village
CURRENT_STATE: Stable; local details = ???
ORIGIN: Settlement pertanian yang memasok kebutuhan Cekungan Varenhold
HISTORY: ???
```

### SETTLEMENT-002 — Oakrest

```text
SETTLEMENT_ID: SETTLEMENT-002
CITY_ID: CITY-001
REGION_ID: REGION-001
NAME: Oakrest
TYPE: Woodland-Edge Village
CURRENT_STATE: Stable; local details = ???
ORIGIN: Settlement tepian hutan yang terhubung dengan pasar Varenhold
HISTORY: ???
```

### SETTLEMENT-003 — Rivergate

```text
SETTLEMENT_ID: SETTLEMENT-003
CITY_ID: CITY-002
REGION_ID: REGION-002
NAME: Rivergate
TYPE: River Crossing Village
CURRENT_STATE: Active; river traffic conditions = ???
ORIGIN: Settlement di titik penyeberangan dan bongkar-muat sungai
HISTORY: ???
```

### SETTLEMENT-004 — Millhaven

```text
SETTLEMENT_ID: SETTLEMENT-004
CITY_ID: CITY-002
REGION_ID: REGION-002
NAME: Millhaven
TYPE: Milling Village
CURRENT_STATE: Active; production volume = ???
ORIGIN: Settlement penggilingan dan pengolahan hasil pertanian dekat sungai
HISTORY: ???
```

### SETTLEMENT-005 — Wheatcross

```text
SETTLEMENT_ID: SETTLEMENT-005
CITY_ID: CITY-003
REGION_ID: REGION-003
NAME: Wheatcross
TYPE: Farming Village
CURRENT_STATE: Productive; harvest condition = ???
ORIGIN: Persimpangan jalur pertanian dan pengangkutan hasil panen
HISTORY: ???
```

### SETTLEMENT-006 — Sunfield

```text
SETTLEMENT_ID: SETTLEMENT-006
CITY_ID: CITY-003
REGION_ID: REGION-003
NAME: Sunfield
TYPE: Farming and Pastoral Village
CURRENT_STATE: Productive; livestock condition = ???
ORIGIN: Settlement pertanian dan peternakan di dataran terbuka
HISTORY: ???
```

### SETTLEMENT-007 — Briarford

```text
SETTLEMENT_ID: SETTLEMENT-007
CITY_ID: CITY-004
REGION_ID: REGION-004
NAME: Briarford
TYPE: Frontier Crossing Village
CURRENT_STATE: Frontier-active; local security = ???
ORIGIN: Settlement di jalur penyeberangan menuju kawasan hutan
HISTORY: ???
```

### SETTLEMENT-008 — Greenhollow

```text
SETTLEMENT_ID: SETTLEMENT-008
CITY_ID: CITY-004
REGION_ID: REGION-004
NAME: Greenhollow
TYPE: Woodland Resource Village
CURRENT_STATE: Active; wildlife/monster pressure = ???
ORIGIN: Settlement pengumpul hasil hutan dan sumber daya frontier
HISTORY: ???
```

## 5. Population Model

Population Model adalah agregat; tidak membuat satu file per penduduk.

### 5.1 Kingdom-Level Model

```text
KINGDOM_ID: KINGDOM-001
POPULATION_MODEL_ID: POP-VAL-001
TOTAL_POPULATION: RANGE 650,000–900,000
URBANIZATION: MODERATE
PRIMARY_POPULATION_BASE: AGRICULTURAL + RIVERINE
RACE_CATEGORIES: ONLY ACTIVE RACE_CANON_ID FROM races/CANON_REGISTRY.md
EXACT_RACE_PERCENTAGES: ???
MIGRATION_BALANCE: ???
SEASONAL_MOBILITY: MODERATE
```

### 5.2 Regional Distribution

```text
REGION-001 Cekungan Varenhold       → 20–25% of kingdom population
REGION-002 Koridor Sungai Averen    → 20–25%
REGION-003 Dataran Ladang Emas      → 35–40%
REGION-004 Perbatasan Hutan Thorn   → 15–20%
```

Persentase adalah rentang model, bukan jumlah individu tetap. Distribusi aktual dapat berubah melalui migration, birth/death, disaster, war, economy, dan world events yang tervalidasi.

### 5.3 Settlement Scale Bands

```text
KINGDOM CAPITAL / MAJOR CITY → 40,000–120,000
SECONDARY CITY               → 15,000–60,000
LARGE VILLAGE                → 2,000–8,000
SMALL VILLAGE                → 300–2,000
FRONTIER SETTLEMENT          → 200–3,000
```

Band digunakan sebagai model skala, bukan angka otomatis untuk setiap settlement.

### 5.4 Occupational Distribution

Baseline population model:

```text
AGRICULTURE / FOOD PRODUCTION → MAJOR SHARE
TRADE / TRANSPORT             → SIGNIFICANT SHARE
CRAFT / PROCESSING            → SIGNIFICANT SHARE
SERVICES / ADMINISTRATION     → MODERATE SHARE
SECURITY / MILITARY           → MODERATE SHARE
RESOURCE / FORESTRY           → REGION-DEPENDENT
OTHER                         → REMAINDER
```

Exact percentages remain `???` until an economy/faction model requires a more precise local distribution.

### 5.5 Race Distribution Rule

Population Model boleh mengelompokkan penduduk berdasarkan Race Canon, tetapi:

- hanya `RACE_CANON_ID` aktif yang terdaftar di `races/CANON_REGISTRY.md`;
- tidak boleh membuat ras baru untuk mengisi populasi;
- persentase ras lokal tetap `???` sampai ditetapkan oleh Admin Canon atau model migrasi/populasi yang sah;
- Race tidak otomatis menentukan class, profession, faction, morality, personality, atau outcome;
- migration dapat mengubah komposisi lokal tanpa mengubah Race Canon.

### 5.6 Dynamic NPC Generation Boundary

Population Model menyediakan konteks agregat. Saat gameplay membutuhkan individu:

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

## 6. Geography → Population → NPC Gate

```text
KINGDOM-001
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

Canon NPC untuk Kingdom-001 belum dibuat dalam file ini. Pembuatan Canon NPC dilakukan setelah geography dan population model tervalidasi.

## 7. Canon Safety

- Semua Region, City, dan Settlement di file ini memiliki parent Canon yang valid.
- Nama dan identity di sini adalah Admin Canon.
- `???` tetap unresolved dan tidak boleh diisi oleh AI GM tanpa source yang sah.
- Population Model adalah agregat, bukan daftar penduduk individual.
- Race distribution tidak boleh ditebak dari nama settlement atau karakteristik visual.
- Kingdom-002 belum dibangun di file ini.
