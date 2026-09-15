# ELDORIA WORLD — KINGDOM-002 GEOGRAPHY

> **Authority:** Admin
> **Canon:** Admin Canon v1.0
> **Kingdom:** KINGDOM-002 — Kerajaan Brannor
> **Empire:** EMPIRE-001 — Kekaisaran Valthera
> **Purpose:** Registry resmi Region → City → Village/Settlement dan Population Model Kingdom-002.

## 1. Geography Hierarchy

```text
EMPIRE-001 — Kekaisaran Valthera
└── KINGDOM-002 — Kerajaan Brannor
    ├── REGION-005 — Pegunungan Durn
    │   └── CITY-005 — Durnhaven
    │       ├── SETTLEMENT-009 — Stonepass
    │       └── SETTLEMENT-010 — Highmere
    ├── REGION-006 — Lembah Kharven
    │   └── CITY-006 — Kharhold
    │       ├── SETTLEMENT-011 — Valecrest
    │       └── SETTLEMENT-012 — Ironbrook
    ├── REGION-007 — Punggung Besi
    │   └── CITY-007 — Ferren
    │       ├── SETTLEMENT-013 — Blackridge
    │       └── SETTLEMENT-014 — Redstone
    └── REGION-008 — Perbatasan Frostpine
        └── CITY-008 — Frostwatch
            ├── SETTLEMENT-015 — Pinewatch
            └── SETTLEMENT-016 — Coldmere
```

Semua ID di atas adalah Canon Admin dan memiliki parent yang valid.

## 2. Region Registry

### REGION-005 — Pegunungan Durn

```text
REGION_ID: REGION-005
KINGDOM_ID: KINGDOM-002
NAME: Pegunungan Durn
TYPE: Highland-Mountain Core
PRIMARY_FUNCTION: pusat pegunungan, pertambangan, jalur lintas, dan pusat pemerintahan kerajaan
TERRAIN: pegunungan tinggi, lereng berbatu, lembah sempit
CLIMATE: dingin dataran tinggi; detail musiman lokal = ???
RESOURCE_BASE: mineral dan bahan batuan; jenis mineral spesifik = ???
CURRENT_STATE: aktif dan terhubung dengan pusat kerajaan; detail keamanan = ???
```

### REGION-006 — Lembah Kharven

```text
REGION_ID: REGION-006
KINGDOM_ID: KINGDOM-002
NAME: Lembah Kharven
TYPE: Highland-Valley Corridor
PRIMARY_FUNCTION: permukiman lembah, pertanian dataran tinggi, transportasi, dan penghubung antarwilayah
TERRAIN: lembah luas, lereng, sungai pegunungan
CLIMATE: dataran tinggi dengan musim dingin yang nyata; detail lokal = ???
RESOURCE_BASE: pertanian lembah, hasil hutan, batuan, dan bahan mentah; detail = ???
CURRENT_STATE: aktif sebagai koridor internal; kondisi keamanan = ???
```

### REGION-007 — Punggung Besi

```text
REGION_ID: REGION-007
KINGDOM_ID: KINGDOM-002
NAME: Punggung Besi
TYPE: Mineral-Extraction Belt
PRIMARY_FUNCTION: pertambangan, pengolahan bahan mentah, metalworking, dan perdagangan material
TERRAIN: perbukitan berbatu dan pegunungan rendah-menengah
CLIMATE: variatif menurut elevasi; detail lokal = ???
RESOURCE_BASE: mineral logam dan batuan; jenis serta cadangan spesifik = ???
CURRENT_STATE: aktif secara ekonomi; detail risiko tambang dan keamanan = ???
```

### REGION-008 — Perbatasan Frostpine

```text
REGION_ID: REGION-008
KINGDOM_ID: KINGDOM-002
NAME: Perbatasan Frostpine
TYPE: Frontier-Forest Highland
PRIMARY_FUNCTION: frontier, kehutanan, jalur pegunungan, pengawasan perbatasan, dan settlement terpencil
TERRAIN: hutan konifer, pegunungan, lembah dan jalur sempit
CLIMATE: dingin; kondisi cuaca ekstrem dan pola musim lokal = ???
RESOURCE_BASE: hasil hutan, batuan, dan bahan mentah frontier; detail = ???
CURRENT_STATE: frontier aktif; tingkat ancaman eksternal/internal = ???
```

## 3. City Registry

### CITY-005 — Durnhaven

```text
CITY_ID: CITY-005
KINGDOM_ID: KINGDOM-002
REGION_ID: REGION-005
NAME: Durnhaven
TYPE: Kingdom Capital / Major Mountain City
PRIMARY_FUNCTION: ibu kota kerajaan, administrasi, perdagangan, dan simpul jalur pegunungan
POPULATION_BAND: 40,000–120,000
CURRENT_STATE: aktif; detail administrasi dan keamanan = ???
```

### CITY-006 — Kharhold

```text
CITY_ID: CITY-006
KINGDOM_ID: KINGDOM-002
REGION_ID: REGION-006
NAME: Kharhold
TYPE: Secondary Valley City
PRIMARY_FUNCTION: pusat lembah, perdagangan regional, agrikultur dataran tinggi, dan transportasi
POPULATION_BAND: 15,000–60,000
CURRENT_STATE: aktif; detail = ???
```

### CITY-007 — Ferren

```text
CITY_ID: CITY-007
KINGDOM_ID: KINGDOM-002
REGION_ID: REGION-007
NAME: Ferren
TYPE: Mining-Industrial City
PRIMARY_FUNCTION: pengolahan mineral, metalworking, perdagangan material, dan jasa pertambangan
POPULATION_BAND: 15,000–60,000
CURRENT_STATE: aktif; detail = ???
```

### CITY-008 — Frostwatch

```text
CITY_ID: CITY-008
KINGDOM_ID: KINGDOM-002
REGION_ID: REGION-008
NAME: Frostwatch
TYPE: Frontier Mountain City
PRIMARY_FUNCTION: pengawasan frontier, logistik, kehutanan, dan pengamanan jalur pegunungan
POPULATION_BAND: 15,000–60,000
CURRENT_STATE: aktif; detail keamanan = ???
```

## 4. Village / Settlement Registry

### CITY-005 — Durnhaven

```text
SETTLEMENT-009 → Stonepass → CITY-005 → REGION-005
TYPE: Mountain Pass Village
FUNCTION: jasa jalur pegunungan, penginapan, logistik, dan perdagangan lokal
POPULATION_BAND: 300–2,000

SETTLEMENT-010 → Highmere → CITY-005 → REGION-005
TYPE: Highland Village
FUNCTION: pertanian dataran tinggi, peternakan, dan suplai kota
POPULATION_BAND: 2,000–8,000
```

### CITY-006 — Kharhold

```text
SETTLEMENT-011 → Valecrest → CITY-006 → REGION-006
TYPE: Large Valley Village
FUNCTION: pertanian lembah, pengolahan pangan, dan transportasi lokal
POPULATION_BAND: 2,000–8,000

SETTLEMENT-012 → Ironbrook → CITY-006 → REGION-006
TYPE: Small Resource Village
FUNCTION: pengumpulan bahan mentah, pengolahan sederhana, dan jasa transport
POPULATION_BAND: 300–2,000
```

### CITY-007 — Ferren

```text
SETTLEMENT-013 → Blackridge → CITY-007 → REGION-007
TYPE: Mining Village
FUNCTION: layanan pertambangan dan pemukiman pekerja tambang
POPULATION_BAND: 2,000–8,000

SETTLEMENT-014 → Redstone → CITY-007 → REGION-007
TYPE: Processing Village
FUNCTION: pengolahan batuan/mineral dan suplai industri lokal
POPULATION_BAND: 300–2,000
```

### CITY-008 — Frostwatch

```text
SETTLEMENT-015 → Pinewatch → CITY-008 → REGION-008
TYPE: Frontier Forest Village
FUNCTION: kehutanan, suplai frontier, dan pemantauan jalur lokal
POPULATION_BAND: 300–2,000

SETTLEMENT-016 → Coldmere → CITY-008 → REGION-008
TYPE: Remote Highland Settlement
FUNCTION: pemukiman frontier, peternakan/pertanian terbatas, dan pos logistik
POPULATION_BAND: 300–2,000
```

## 5. Kingdom-002 Population Model

```text
POPULATION_MODEL_ID: POP-BRA-001
TOTAL_POPULATION: RANGE 450,000–700,000
URBANIZATION: LOW-MODERATE
PRIMARY_POPULATION_BASE: MINING + HIGHLAND AGRICULTURE + TRADE + FORESTRY
SEASONAL_MOBILITY: MODERATE-HIGH
MIGRATION_BALANCE: ???
EXACT_RACE_PERCENTAGES: ???
```

### 5.1 Regional Population Distribution

```text
REGION-005 — Pegunungan Durn      → 20–25%
REGION-006 — Lembah Kharven       → 25–30%
REGION-007 — Punggung Besi        → 30–35%
REGION-008 — Perbatasan Frostpine → 15–20%
```

Rentang regional mencakup seluruh populasi Kingdom-002 secara agregat; exact allocation tetap dihitung/ditetapkan oleh Population Model runtime bila diperlukan dan tidak boleh diperlakukan sebagai angka individu.

### 5.2 Settlement Population Logic

Population tidak harus mengisi batas atas setiap settlement. Distribusi aktual mengikuti kapasitas ekonomi, terrain, akses, keamanan, musim, migrasi, dan kebutuhan simulasi.

```text
KINGDOM CAPITAL / MAJOR CITY → 40,000–120,000
SECONDARY CITY               → 15,000–60,000
LARGE VILLAGE                → 2,000–8,000
SMALL VILLAGE                → 300–2,000
FRONTIER SETTLEMENT          → 200–3,000
```

### 5.3 Occupational Baseline

```text
MINING / RESOURCE EXTRACTION: major share
AGRICULTURE / LIVESTOCK: major share in suitable valleys/highlands
TRADE / TRANSPORT: significant
CRAFT / METALWORKING / PROCESSING: significant
FORESTRY: region-dependent
SECURITY / FRONTIER SERVICE: moderate
ADMINISTRATION / SERVICES: moderate
OTHER: remainder
```

Exact percentages = `???`.

## 6. Race Population Boundary

Kingdom-002 tidak memiliki Race Canon eksklusif.

Population Model hanya boleh menggunakan `RACE_CANON_ID` aktif dari `races/CANON_REGISTRY.md`.

```text
ALLOWED_RACE_SOURCE: races/CANON_REGISTRY.md
EXACT_RACE_PERCENTAGES: ???
RACE_MIGRATION: dynamic / evidence-based
RACE_EXCLUSIVE_SETTLEMENT: none unless separately Canonized
```

Race tidak menentukan class, profession, faction, personality, morality, atau outcome individu. Nama wilayah seperti Durn, Kharven, Ferren, dan Frostpine juga tidak boleh dipakai untuk menebak race.

## 7. Dynamic NPC Population Flow

```text
POPULATION MODEL
↓
REGION / CITY / SETTLEMENT CONTEXT
↓
RACE_CANON_ID FROM ACTIVE RACE REGISTRY
↓
NPC GENERATION
↓
PERSIST ONLY IF MATERIAL
```

Dynamic NPC tidak otomatis menjadi Canon NPC. Canon NPC dibangun setelah geography, population, dan konteks faction/governance siap.

## 8. Geography Integrity

```text
EMPIRE-001
└── KINGDOM-002
    ├── REGION-005
    │   └── CITY-005
    │       ├── SETTLEMENT-009
    │       └── SETTLEMENT-010
    ├── REGION-006
    │   └── CITY-006
    │       ├── SETTLEMENT-011
    │       └── SETTLEMENT-012
    ├── REGION-007
    │   └── CITY-007
    │       ├── SETTLEMENT-013
    │       └── SETTLEMENT-014
    └── REGION-008
        └── CITY-008
            ├── SETTLEMENT-015
            └── SETTLEMENT-016
```

All `KINGDOM_ID`, `REGION_ID`, `CITY_ID`, dan `SETTLEMENT` parent references are authoritative within this Canon file.

## 9. Canon Safety

- Kingdom-002 tetap `Kerajaan Brannor`; capital tetap `Durnhaven`.
- Region, City, dan Settlement dalam file ini adalah Admin Canon.
- Population Model adalah model agregat, bukan daftar individu.
- Tidak ada Race Canon eksklusif untuk Brannor.
- Exact race percentages, migration balance, mineral types, exact boundaries, detailed governance, faction ownership, dan detailed security conditions tetap `???` jika belum ditetapkan.
- Canon NPC belum dibuat di tahap ini.
- AI GM boleh menghasilkan Dynamic NPC berdasarkan konteks ini, tetapi tidak boleh mengubah geography atau Population Model Canon.
