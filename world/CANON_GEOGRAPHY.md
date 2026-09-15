# ELDORIA WORLD — CANON GEOGRAPHY REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.1
> **Purpose:** Registry resmi struktur geografis-politik Eldoria sebagai dasar pembangunan settlement, population model, faction, dan Canon NPC.

## 1. Authority

File ini adalah registry struktur, bukan narasi dunia.

Urutan authority geografis utama:

```text
WORLD
└── 1 KEKAISARAN
    └── BEBERAPA KERAJAAN
        └── BEBERAPA KOTA
            └── BEBERAPA DESA / SETTLEMENT
```

Nama, jumlah, batas, parent, dan detail geografis hanya menjadi Canon setelah dimasukkan oleh Admin atau sumber Canon yang sah.

## 2. Current Canon Coverage

```text
EMPIRE_COUNT: 1 (structural requirement)
KINGDOM_COUNT: ???
CITY_COUNT: ???
VILLAGE_SETTLEMENT_COUNT: ???
```

## 3. Empire Registry

### EMPIRE-001

```text
EMPIRE_ID: EMPIRE-001
NAME: Kekaisaran Valthera
TYPE: EMPIRE
CAPITAL: ???
BOUNDARY: ???
REGIONS: ???
CURRENT_STATE: ???
ORIGIN: ???
HISTORY: ???
```

### 3.1 Empire Identity

**Kekaisaran Valthera** adalah satu-satunya entitas kekaisaran utama dalam struktur politik Canon Eldoria. Kekaisaran ini menjadi payung administratif dan geopolitik bagi beberapa kerajaan yang akan ditetapkan kemudian.

Kekaisaran tidak dianggap sebagai satu kota raksasa. Struktur internalnya terdiri atas kerajaan-kerajaan dengan wilayah, pemerintahan, settlement, faction, dan kepentingan regional masing-masing.

### 3.2 Administrative Role

Kekaisaran Valthera menjadi tingkat administratif tertinggi dalam struktur daratan Canon Eldoria:

```text
KEKAISARAN VALTHERA
└── KERAJAAN
    └── KOTA
        └── DESA / SETTLEMENT
```

Kewenangan kekaisaran, bentuk hubungan dengan kerajaan, dan pembagian administratif yang lebih rinci akan ditetapkan bersama Canon Kerajaan dan Region. Detail yang belum ditetapkan tetap `???`.

### 3.3 Empire Canon Boundaries

```text
EMPIRE_ID: EMPIRE-001
NAME: Kekaisaran Valthera
CAPITAL: ???
CONTINENT: 1 BENUA UTAMA
KINGDOMS: ???
MAJOR_REGIONS: ???
POLITICAL_SYSTEM: ???
RULER: ???
MILITARY_STRUCTURE: ???
ECONOMIC_STRUCTURE: ???
CULTURAL_PROFILE: ???
RELIGIOUS_STRUCTURE: ???
MAJOR_FACTIONS: ???
EXTERNAL_RELATIONS: ???
CURRENT_POLITICAL_STATE: ???
```

Field `???` sengaja belum diisi. Tidak boleh diturunkan sebagai fakta oleh AI GM tanpa Canon atau state yang sah.

### 3.4 Empire Population Boundary

Population Kekaisaran Valthera tidak dicatat sebagai daftar individu. Population Model tingkat kekaisaran akan dibangun setelah struktur kerajaan, region, kota, dan settlement ditetapkan.

Penduduk massal akan direpresentasikan secara agregat. Tokoh penting akan direpresentasikan melalui Canon NPC, sedangkan individu biasa dapat muncul melalui Dynamic NPC sesuai aturan generation.

### 3.5 Empire Construction Rule

Pembangunan Kerajaan wajib menggunakan:

```text
EMPIRE-001
    ↓
KINGDOM.EMPIRE_ID = EMPIRE-001
    ↓
REGION / CITY / SETTLEMENT
    ↓
POPULATION MODEL
    ↓
CANON NPC
```

Tidak boleh ada kerajaan Canon yang menunjuk ke Empire ID yang belum valid.

## 4. Kingdom Registry

Setiap Kerajaan Canon wajib memiliki:

```text
KINGDOM_ID
EMPIRE_ID
NAME
CAPITAL
BOUNDARY
REGIONS
CURRENT_STATE
ORIGIN
HISTORY
```

Daftar Kerajaan:

```text
KINGDOM-001: ???
KINGDOM-002: ???
KINGDOM-003: ???
...
```

Jumlah aktual tidak boleh ditebak.

## 5. City Registry

Setiap Kota Canon wajib memiliki:

```text
CITY_ID
KINGDOM_ID
REGION_ID
NAME
TYPE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

Daftar Kota:

```text
CITY-001: ???
CITY-002: ???
CITY-003: ???
...
```

## 6. Village / Settlement Registry

Setiap Desa Canon wajib memiliki:

```text
SETTLEMENT_ID
CITY_ID
REGION_ID
NAME
TYPE
CURRENT_STATE
ORIGIN
HISTORY
```

Daftar Desa/Settlement:

```text
SETTLEMENT-001: ???
SETTLEMENT-002: ???
SETTLEMENT-003: ???
...
```

## 7. Region Registry

Region digunakan untuk konteks geografis, ekologis, administratif, travel, economy, monster ecology, dan faction influence.

Minimum:

```text
REGION_ID
PARENT_ID
NAME
TYPE
TERRAIN
CLIMATE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

Daftar Region:

```text
REGION-001: ???
REGION-002: ???
REGION-003: ???
...
```

## 8. Parent-Child Integrity

Tidak boleh ada Canon entity yang menunjuk kepada parent `???`.

Validasi minimum:

```text
EMPIRE
↓
KINGDOM.EMPIRE_ID → existing EMPIRE_ID
↓
CITY.KINGDOM_ID → existing KINGDOM_ID
CITY.REGION_ID → existing REGION_ID
↓
SETTLEMENT.CITY_ID → existing CITY_ID
SETTLEMENT.REGION_ID → existing REGION_ID
```

Jika hubungan administratif berbeda dari hierarchy normal, hubungan tersebut harus dinyatakan eksplisit oleh Canon.

## 9. Canon NPC Build Gate

Canon NPC tidak boleh dibuat berdasarkan wilayah yang masih `???`.

Urutan pembangunan:

```text
CANON GEOGRAPHY
→ POPULATION MODEL
→ SETTLEMENT CONTEXT
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Minimum Canon NPC setelah parent wilayah resmi tersedia:

```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC per kerajaan
KEKAISARAN → ≥ 25 Canon NPC
```

Minimum tersebut adalah jumlah tokoh penting Canon, bukan jumlah penduduk.

## 10. NPC Distribution Rule

Canon NPC harus mempunyai alasan keberadaan yang sesuai dengan wilayahnya.

Sebelum membuat NPC, Admin harus mempertimbangkan konteks parent seperti:

- governance,
- security,
- economy,
- faction,
- religion/culture bila Canon relevan,
- services,
- trade,
- military,
- local information,
- conflict,
- regional interests.

Tidak boleh membuat NPC hanya untuk memenuhi angka minimum.

## 11. Population Boundary

Population Model menangani penduduk massal secara agregat. Tidak semua penduduk menjadi Canon NPC atau record individual.

Dynamic NPC dapat dimaterialisasi saat gameplay membutuhkan individu tertentu. Dynamic NPC tidak otomatis menjadi Canon.

## 12. Construction Status

```text
PHASE 1 — STRUCTURE: COMPLETE
PHASE 2 — EMPIRE IDENTITY: COMPLETE
PHASE 3 — KINGDOMS: PENDING
PHASE 4 — REGIONS: PENDING
PHASE 5 — CITIES: PENDING
PHASE 6 — VILLAGES / SETTLEMENTS: PENDING
PHASE 7 — POPULATION MODELS: PENDING
PHASE 8 — CANON NPC BY REGION: LOCKED UNTIL PHASE 3–6 ARE DEFINED
```

## 13. Canon Safety

- Jangan mengarang jumlah Kerajaan/Kota/Desa.
- Jangan membuat Canon NPC yang parent wilayahnya belum Canon.
- Jangan menganggap Dynamic Discovery sebagai Canon Geography.
- Perubahan struktur geografis Canon adalah kewenangan Admin.
- Detail Empire yang belum ditetapkan tetap `???`.
- Nama Kekaisaran `Kekaisaran Valthera` adalah Canon resmi setelah commit ini.

## 14. Final Principle

> **Bangun peta dan hierarchy terlebih dahulu; kemudian isi kehidupan wilayah secara sistematis. Canon NPC mengikuti geografi, bukan sebaliknya.**
