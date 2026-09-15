# ELDORIA WORLD — CANON NPC COVERAGE MATRIX

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Master coverage matrix untuk merencanakan kebutuhan Canon NPC berdasarkan struktur Empire → Kingdom → City → Settlement tanpa membuat NPC individual.
> **Scope:** Planning / coverage only. File ini tidak mendaftarkan identitas NPC.

---

## 1. Canon Authority

NPC Canon hanya boleh dibuat setelah parent geography dan context yang diperlukan tersedia.

```text
CANON GEOGRAPHY
→ POPULATION MODEL
→ SETTLEMENT / CITY / KINGDOM CONTEXT
→ FACTION / GOVERNANCE CONTEXT
→ CANON NPC
```

Sumber struktur geography resmi:
- `world/CANON_GEOGRAPHY.md`
- `world/kingdoms/KINGDOM-001_GEOGRAPHY.md`
- `world/kingdoms/KINGDOM-002_GEOGRAPHY.md`
- `world/kingdoms/KINGDOM-003_GEOGRAPHY.md`
- `world/kingdoms/KINGDOM-004_GEOGRAPHY.md`
- `world/kingdoms/KINGDOM-005_GEOGRAPHY.md`

---

## 2. Coverage Semantics

Angka di bawah adalah **minimum coverage obligation**, bukan daftar NPC individual dan bukan kewajiban membuat NPC filler.

```text
SETTLEMENT → ≥ 3 Canon NPC coverage
CITY       → ≥ 5 Canon NPC coverage
KINGDOM    → ≥ 10 Canon NPC coverage
EMPIRE     → ≥ 25 Canon NPC coverage
```

### 2.1 Cross-Scope Coverage

Satu NPC Canon boleh memenuhi coverage pada lebih dari satu scope apabila secara lore memang relevan.

Contoh valid:

```text
NPC A
Settlement relevance: Bellmere
City relevance: Varenhold
Kingdom relevance: Valedorn
Empire relevance: Valthera
```

Overlap hanya boleh digunakan jika hubungan, jabatan, aktivitas, wilayah pengaruh, atau pengetahuan NPC secara masuk akal mendukung scope tersebut. Tidak boleh menaikkan coverage secara administratif tanpa dasar lore.

### 2.2 Unique NPC Count

Matrix ini **tidak menetapkan jumlah minimum NPC unik global**. Jumlah NPC unik akan ditentukan saat Master NPC List dibuat berdasarkan kebutuhan lore, faction, governance, geography, dan hubungan antarkarakter.

---

## 3. Coverage Hierarchy

```text
EMPIRE-001 — Kekaisaran Valthera
│
├── KINGDOM-001 — Valedorn
│   ├── CITY-001 Varenhold
│   │   ├── SETTLEMENT-001 Bellmere
│   │   └── SETTLEMENT-002 Oakrest
│   ├── CITY-002 Averen
│   │   ├── SETTLEMENT-003 Rivergate
│   │   └── SETTLEMENT-004 Millhaven
│   ├── CITY-003 Goldmere
│   │   ├── SETTLEMENT-005 Wheatcross
│   │   └── SETTLEMENT-006 Sunfield
│   └── CITY-004 Thornwick
│       ├── SETTLEMENT-007 Briarford
│       └── SETTLEMENT-008 Greenhollow
│
├── KINGDOM-002 — Brannor
│   ├── CITY-005 Durnhaven
│   │   ├── SETTLEMENT-009 Stonepass
│   │   └── SETTLEMENT-010 Highmere
│   ├── CITY-006 Kharhold
│   │   ├── SETTLEMENT-011 Valecrest
│   │   └── SETTLEMENT-012 Ironbrook
│   ├── CITY-007 Ferren
│   │   ├── SETTLEMENT-013 Blackridge
│   │   └── SETTLEMENT-014 Redstone
│   └── CITY-008 Frostwatch
│       ├── SETTLEMENT-015 Pinewatch
│       └── SETTLEMENT-016 Coldmere
│
├── KINGDOM-003 — Mariselle
│   ├── CITY-009 Port Aureon
│   │   ├── SETTLEMENT-017 Seabridge
│   │   └── SETTLEMENT-018 Tidemere
│   ├── CITY-010 Southport
│   │   ├── SETTLEMENT-019 Saltmere
│   │   └── SETTLEMENT-020 Gullhaven
│   ├── CITY-011 Azurehold
│   │   ├── SETTLEMENT-021 Pearlwatch
│   │   └── SETTLEMENT-022 Windrest
│   └── CITY-012 Westhaven
│       ├── SETTLEMENT-023 Driftwood
│       └── SETTLEMENT-024 Stormbay
│
├── KINGDOM-004 — Sylvaran
│   ├── CITY-013 Elaris
│   │   ├── SETTLEMENT-025 Greenford
│   │   └── SETTLEMENT-026 Mossvale
│   ├── CITY-014 Sylford
│   │   ├── SETTLEMENT-027 Oakmere
│   │   └── SETTLEMENT-028 Fernwatch
│   ├── CITY-015 Riverwyn
│   │   ├── SETTLEMENT-029 Brookrest
│   │   └── SETTLEMENT-030 Alderbank
│   └── CITY-016 Wildmere
│       ├── SETTLEMENT-031 Pinecross
│       └── SETTLEMENT-032 Thornrest
│
└── KINGDOM-005 — Sahrad
    ├── CITY-017 Qasrane
    │   ├── SETTLEMENT-033 Wellspring
    │   └── SETTLEMENT-034 Datehaven
    ├── CITY-018 Sarakh
    │   ├── SETTLEMENT-035 Grassrest
    │   └── SETTLEMENT-036 Herdwatch
    ├── CITY-019 Caravanser
    │   ├── SETTLEMENT-037 Dustgate
    │   └── SETTLEMENT-038 Redwell
    └── CITY-020 Sunscar
        ├── SETTLEMENT-039 Sandmere
        └── SETTLEMENT-040 Farwatch
```

---

## 4. Empire Coverage Matrix

### EMPIRE-001 — Kekaisaran Valthera

| Scope | Minimum Coverage | Planning Need | Status |
|---|---:|---|---|
| Empire | ≥25 | Imperial ruler/authority, administration, military, law, economy, diplomacy, strategic figures, major institutions/factions | PLANNED |

**Important:** personal name of the Emperor, detailed ministries/council, military structure, economic structure, religious structure, major factions, and other unresolved imperial details remain `???` until separately Canonized. NPC design must not invent unresolved Canon facts merely to fill this matrix.

---

## 5. Kingdom Coverage Matrix

| Kingdom | Type / Function | Minimum | Primary NPC Coverage Themes | Status |
|---|---|---:|---|---|
| KINGDOM-001 Valedorn | Heartland Agraris-Riverine | ≥10 | agriculture, river trade, food distribution, administration, roads, commerce, heartland security | PLANNED |
| KINGDOM-002 Brannor | Highland-Mineral | ≥10 | mining, minerals, mountain routes, transport, forestry, highland agriculture, frontier security | PLANNED |
| KINGDOM-003 Mariselle | Coastal-Maritime | ≥10 | ports, maritime trade, sailing, fisheries, shipbuilding, coastal security, island connectivity | PLANNED |
| KINGDOM-004 Sylvaran | Forest-Border | ≥10 | forestry, agriculture, upper rivers, crafts, land routes, ecological frontier, resource management | PLANNED |
| KINGDOM-005 Sahrad | Arid-Steppe | ≥10 | oasis, caravan trade, pastoralism, water access, long-distance commerce, arid frontier | PLANNED |

**Kingdom total coverage obligation: ≥50.**

This is a coverage total, not a requirement for 50 unique NPCs if valid cross-scope coverage exists.

---

## 6. City Coverage Matrix

Every current Canon city requires at least five relevant Canon NPC coverage.

| City | Kingdom | Region | Min | Planning Themes | Status |
|---|---|---|---:|---|---|
| CITY-001 Varenhold | K-001 | REGION-001 Cekungan Varenhold | ≥5 | capital/administration, agriculture, river commerce, services, security | PLANNED |
| CITY-002 Averen | K-001 | REGION-002 Koridor Sungai Averen | ≥5 | river trade, transport, mills, logistics, local authority | PLANNED |
| CITY-003 Goldmere | K-001 | REGION-003 Dataran Ladang Emas | ≥5 | farming, grain trade, markets, land routes, rural administration | PLANNED |
| CITY-004 Thornwick | K-001 | REGION-004 Perbatasan Hutan Thorn | ≥5 | frontier, forest trade, farming, security, border commerce | PLANNED |
| CITY-005 Durnhaven | K-002 | REGION-005 Pegunungan Durn | ≥5 | mining, mountain administration, trade routes, smithing, security | PLANNED |
| CITY-006 Kharhold | K-002 | REGION-006 Lembah Kharven | ≥5 | valley agriculture, mining support, transport, commerce, administration | PLANNED |
| CITY-007 Ferren | K-002 | REGION-007 Punggung Besi | ≥5 | iron/mineral economy, industry, trade, labor, security | PLANNED |
| CITY-008 Frostwatch | K-002 | REGION-008 Perbatasan Frostpine | ≥5 | frontier defense, forestry, mountain travel, survival, trade | PLANNED |
| CITY-009 Port Aureon | K-003 | REGION-009 Teluk Aureon | ≥5 | port administration, shipping, maritime trade, fisheries, security | PLANNED |
| CITY-010 Southport | K-003 | REGION-010 Pantai Selatan | ≥5 | coastal trade, fishing, ship services, markets, security | PLANNED |
| CITY-011 Azurehold | K-003 | REGION-011 Kepulauan Azure | ≥5 | island governance, sailing, fisheries, inter-island trade, navigation | PLANNED |
| CITY-012 Westhaven | K-003 | REGION-012 Pesisir Barat | ≥5 | coastal commerce, fishing, shipbuilding, weather risks, security | PLANNED |
| CITY-013 Elaris | K-004 | REGION-013 Hutan Elaris | ≥5 | forest administration, forestry, crafts, agriculture, ecological management | PLANNED |
| CITY-014 Sylford | K-004 | REGION-014 Lembah Silvan | ≥5 | valley agriculture, river routes, crafts, trade, local governance | PLANNED |
| CITY-015 Riverwyn | K-004 | REGION-015 Sungai Elden | ≥5 | river trade, agriculture, transport, fisheries, administration | PLANNED |
| CITY-016 Wildmere | K-004 | REGION-016 Perbatasan Wildmere | ≥5 | frontier, forest resources, security, land routes, ecological boundary | PLANNED |
| CITY-017 Qasrane | K-005 | REGION-017 Oasis Qasrane | ≥5 | oasis governance, water, caravan trade, agriculture, markets | PLANNED |
| CITY-018 Sarakh | K-005 | REGION-018 Padang Rumput Sahr | ≥5 | pastoralism, livestock, dryland trade, water access, local governance | PLANNED |
| CITY-019 Caravanser | K-005 | REGION-019 Koridor Kafilah Timur | ≥5 | caravan logistics, merchants, guards, customs, long-distance trade | PLANNED |
| CITY-020 Sunscar | K-005 | REGION-020 Perbatasan Sunscar | ≥5 | arid frontier, survival, caravans, security, resource access | PLANNED |

**City total coverage obligation: ≥100.**

---

## 7. Settlement Coverage Matrix

Every current Canon settlement requires at least three relevant Canon NPC coverage.

| Settlement | City | Kingdom | Min | Local Coverage Themes | Status |
|---|---|---|---:|---|---|
| SETTLEMENT-001 Bellmere | Varenhold | K-001 | ≥3 | farming, local services, river/road activity | PLANNED |
| SETTLEMENT-002 Oakrest | Varenhold | K-001 | ≥3 | farming, forestry edge, local trade | PLANNED |
| SETTLEMENT-003 Rivergate | Averen | K-001 | ≥3 | river transport, trade, ferries/services | PLANNED |
| SETTLEMENT-004 Millhaven | Averen | K-001 | ≥3 | milling, agriculture, river economy | PLANNED |
| SETTLEMENT-005 Wheatcross | Goldmere | K-001 | ≥3 | grain production, farming, road trade | PLANNED |
| SETTLEMENT-006 Sunfield | Goldmere | K-001 | ≥3 | agriculture, seasonal labor, local commerce | PLANNED |
| SETTLEMENT-007 Briarford | Thornwick | K-001 | ≥3 | frontier farming, forest edge, crossing/roads | PLANNED |
| SETTLEMENT-008 Greenhollow | Thornwick | K-001 | ≥3 | forest resources, farming, frontier life | PLANNED |
| SETTLEMENT-009 Stonepass | Durnhaven | K-002 | ≥3 | mountain passage, mining support, trade | PLANNED |
| SETTLEMENT-010 Highmere | Durnhaven | K-002 | ≥3 | highland agriculture, travel, local services | PLANNED |
| SETTLEMENT-011 Valecrest | Kharhold | K-002 | ≥3 | valley farming, transport, trade | PLANNED |
| SETTLEMENT-012 Ironbrook | Kharhold | K-002 | ≥3 | mining/metal work, river access, commerce | PLANNED |
| SETTLEMENT-013 Blackridge | Ferren | K-002 | ≥3 | iron/mineral work, mountain labor, security | PLANNED |
| SETTLEMENT-014 Redstone | Ferren | K-002 | ≥3 | mining, quarry/resource work, trade | PLANNED |
| SETTLEMENT-015 Pinewatch | Frostwatch | K-002 | ≥3 | forestry, frontier watch, mountain travel | PLANNED |
| SETTLEMENT-016 Coldmere | Frostwatch | K-002 | ≥3 | cold-climate survival, forestry, frontier trade | PLANNED |
| SETTLEMENT-017 Seabridge | Port Aureon | K-003 | ≥3 | coastal transport, fishing, port services | PLANNED |
| SETTLEMENT-018 Tidemere | Port Aureon | K-003 | ≥3 | fisheries, coastal trade, maritime services | PLANNED |
| SETTLEMENT-019 Saltmere | Southport | K-003 | ≥3 | salt/coastal economy, fishing, trade | PLANNED |
| SETTLEMENT-020 Gullhaven | Southport | K-003 | ≥3 | fishing, coastal transport, markets | PLANNED |
| SETTLEMENT-021 Pearlwatch | Azurehold | K-003 | ≥3 | island trade, fisheries, navigation | PLANNED |
| SETTLEMENT-022 Windrest | Azurehold | K-003 | ≥3 | sailing, weather exposure, island services | PLANNED |
| SETTLEMENT-023 Driftwood | Westhaven | K-003 | ≥3 | coastal resources, fishing, trade | PLANNED |
| SETTLEMENT-024 Stormbay | Westhaven | K-003 | ≥3 | storm-prone coast, fishing, maritime safety | PLANNED |
| SETTLEMENT-025 Greenford | Elaris | K-004 | ≥3 | forestry, farming, crafts | PLANNED |
| SETTLEMENT-026 Mossvale | Elaris | K-004 | ≥3 | forest resources, agriculture, local trade | PLANNED |
| SETTLEMENT-027 Oakmere | Sylford | K-004 | ≥3 | valley agriculture, forestry, commerce | PLANNED |
| SETTLEMENT-028 Fernwatch | Sylford | K-004 | ≥3 | forest edge, watch/security, crafts | PLANNED |
| SETTLEMENT-029 Brookrest | Riverwyn | K-004 | ≥3 | river trade, farming, transport | PLANNED |
| SETTLEMENT-030 Alderbank | Riverwyn | K-004 | ≥3 | riverbank agriculture, crafts, trade | PLANNED |
| SETTLEMENT-031 Pinecross | Wildmere | K-004 | ≥3 | frontier crossing, forestry, security | PLANNED |
| SETTLEMENT-032 Thornrest | Wildmere | K-004 | ≥3 | forest frontier, farming, local defense | PLANNED |
| SETTLEMENT-033 Wellspring | Qasrane | K-005 | ≥3 | water management, oasis agriculture, trade | PLANNED |
| SETTLEMENT-034 Datehaven | Qasrane | K-005 | ≥3 | oasis farming, dates, markets/services | PLANNED |
| SETTLEMENT-035 Grassrest | Sarakh | K-005 | ≥3 | pastoralism, livestock, dryland trade | PLANNED |
| SETTLEMENT-036 Herdwatch | Sarakh | K-005 | ≥3 | herding, animal management, security | PLANNED |
| SETTLEMENT-037 Dustgate | Caravanser | K-005 | ≥3 | caravan passage, merchants, guards/services | PLANNED |
| SETTLEMENT-038 Redwell | Caravanser | K-005 | ≥3 | water access, caravan logistics, trade | PLANNED |
| SETTLEMENT-039 Sandmere | Sunscar | K-005 | ≥3 | arid survival, caravan support, water/resources | PLANNED |
| SETTLEMENT-040 Farwatch | Sunscar | K-005 | ≥3 | frontier watch, travel, survival, security | PLANNED |

**Settlement total coverage obligation: ≥120.**

---

## 8. Aggregate Coverage Target

```text
Empire-level     ≥ 25 coverage
Kingdom-level    ≥ 50 coverage
City-level       ≥100 coverage
Settlement-level ≥120 coverage
--------------------------------
Raw scope obligations = ≥295 coverage entries
```

`295` adalah jumlah kewajiban coverage lintas scope, **bukan** target 295 NPC unik.

A single NPC may legitimately satisfy multiple scope entries. Namun, cross-scope assignment harus memiliki dasar lore dan tidak boleh digunakan sebagai quota exploit.

---

## 9. Coverage Role Families

Role families adalah kategori kebutuhan, bukan nama NPC dan bukan assignment final.

### Empire
- Imperial authority / administration
- military / security
- law / judiciary
- economy / treasury / trade
- diplomacy / inter-kingdom relations
- strategic institutions
- major faction representatives
- knowledge / scholarship / religion where Canonized

### Kingdom
- ruler / royal administration where governance Canonized
- regional administration
- economy / trade
- military / security
- agriculture / resource management
- infrastructure / transport
- major faction representation
- specialists tied to kingdom function

### City
- city administration
- commerce / market
- security / guard
- major local profession or industry
- faction / institution representation where Canonized
- services / logistics
- specialist tied to local geography

### Settlement
- local authority or respected community figure
- primary livelihood
- local trade / service
- security / survival / frontier role where applicable
- specialist tied to settlement context

Role families may overlap. Final roles must emerge from actual Canon design, not quota filling.

---

## 10. Race Coverage Rule

NPC coverage **tidak** boleh digunakan untuk memaksakan ras tertentu pada wilayah tertentu.

```text
RACE_CANON_ID
→ must reference active Race Canon
→ may be unresolved as ??? before individual creation
```

Race distribution follows Population Model and Race Canon constraints. Race must not be inferred from settlement name, geography, profession, faction, appearance, class, morality, or stereotype.

No settlement, city, kingdom, or empire may receive an artificial race quota through this matrix.

---

## 11. Faction / Governance Gate

NPC individual dengan `FACTION`, jabatan pemerintahan, atau otoritas politik yang belum memiliki Canon basis tidak boleh diciptakan hanya untuk memenuhi matrix.

```text
GOVERNANCE / FACTION CONTEXT
          ↓
   NPC MASTER DESIGN
          ↓
    NPC INDIVIDUALS
```

Jika suatu detail belum Canon:

```text
??? = Unknown / Unresolved
```

AI GM/Admin tidak boleh mengubah `???` menjadi fakta hanya untuk memenuhi coverage.

---

## 12. NPC Creation Gate

Matrix ini menjadi input untuk tahap berikutnya:

```text
1. Coverage Matrix              ← CURRENT
2. Governance / Faction Context
3. NPC Master List
4. Duplicate / Role / Geography / Race Audit
5. Individual Canon NPC Records
6. Canon NPC Registry Update
7. Final Integrity Verification
```

**Individual NPC creation is explicitly NOT performed by this file.**

---

## 13. Canon Safety

- Tidak ada NPC individual yang dibuat atau didaftarkan oleh matrix ini.
- Tidak ada NPC_ID baru yang dibuat oleh matrix ini.
- Tidak ada geography baru yang dibuat.
- Tidak ada race baru yang dibuat.
- Tidak ada faction/governance fact baru yang ditetapkan.
- Coverage adalah planning obligation, bukan alasan untuk membuat filler NPC.
- Dynamic NPC tidak otomatis menjadi Canon NPC.
- Canon NPC tetap membutuhkan stable `NPC_ID` dan record resmi di `npcs/CANON_REGISTRY.md`.
- `???` tetap Unknown/Unresolved.

---

## 14. Construction Status

```text
GEOGRAPHY CANON: LOCKED FOR CURRENT 5 KINGDOMS
POPULATION MODELS: ACTIVE
NPC ARCHITECTURE: ESTABLISHED IN DESIGN
NPC COVERAGE MATRIX: COMPLETE
NPC INDIVIDUALS: NONE
GOVERNANCE / FACTION CONTEXT: PARTIALLY PENDING
NEXT GATE: GOVERNANCE / FACTION MASTER CONTEXT → NPC MASTER LIST
```
