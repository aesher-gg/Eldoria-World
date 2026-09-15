# ELDORIA WORLD — FACTION CANON REGISTRY

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Purpose:** Registry faction spesifik sebagai konteks governance, ekonomi, keamanan, organisasi, dan bangsawan bagi Canon NPC.

## 1. Rules

Registry ini adalah authority untuk faction spesifik yang tercantum. Planning slot pada `world/GOVERNANCE_FACTION_MASTER.md` bukan otomatis faction.

`???` = Unknown/Unresolved dan tidak boleh ditebak. Faction Dynamic/Persistent tidak otomatis menjadi Canon.

Setiap faction persisten mengikuti schema Module 04:

```text
FACTION_ID
NAME
TYPE
LEADERSHIP
GOALS
INTERESTS
CURRENT_STATE
ORIGIN
HISTORY
```

Faction Canon di registry ini memiliki `ORIGIN: Admin Canon` dan `CANON_STATUS: ACTIVE`; detail yang belum ditetapkan tetap `???` kecuali sudah ditetapkan pada source Canon spesifik.

## 2. Empire-Level Factions

| ID | Name | Type | Scope | Function |
|---|---|---|---|---|
| FACTION-001 | Pemerintahan Kekaisaran Valthera | GOVERNMENT | EMPIRE-001 | Pemerintahan dan administrasi kekaisaran |
| FACTION-002 | Pertahanan Kekaisaran Valthera | MILITARY | EMPIRE-001 | Pertahanan bersama kekaisaran |
| FACTION-003 | Administrasi Perdagangan Kekaisaran | MERCANTILE / ADMINISTRATIVE | EMPIRE-001 | Koordinasi perdagangan antar-kerajaan |

## 3. Kingdom-Level Factions

| ID | Name | Type | Kingdom | Function |
|---|---|---|---|---|
| FACTION-101 | Pemerintahan Kerajaan Valedorn | GOVERNMENT | KINGDOM-001 | Pemerintahan internal |
| FACTION-102 | Pertahanan Kerajaan Valedorn | MILITARY | KINGDOM-001 | Keamanan dan pertahanan |
| FACTION-103 | Serikat Perdagangan Valedorn | MERCANTILE | KINGDOM-001 | Perdagangan darat dan sungai |
| FACTION-104 | Perserikatan Pengelola Lumbung Valedorn | AGRICULTURAL / ECONOMIC | KINGDOM-001 | Pangan dan distribusi agraris |
| FACTION-111 | Pemerintahan Kerajaan Brannor | GOVERNMENT | KINGDOM-002 | Pemerintahan internal |
| FACTION-112 | Pertahanan Kerajaan Brannor | MILITARY | KINGDOM-002 | Keamanan dan pertahanan |
| FACTION-113 | Serikat Penambang Brannor | MINING / ECONOMIC | KINGDOM-002 | Pertambangan dan mineral |
| FACTION-114 | Serikat Jalur Pegunungan Brannor | TRADE / TRANSPORT | KINGDOM-002 | Jalur dan transportasi highland |
| FACTION-121 | Pemerintahan Kerajaan Mariselle | GOVERNMENT | KINGDOM-003 | Pemerintahan internal |
| FACTION-122 | Pertahanan Kerajaan Mariselle | MILITARY | KINGDOM-003 | Keamanan dan pertahanan |
| FACTION-123 | Serikat Dagang Mariselle | MERCANTILE | KINGDOM-003 | Perdagangan maritim |
| FACTION-124 | Perserikatan Pelaut dan Galangan Mariselle | MARITIME / INDUSTRIAL | KINGDOM-003 | Pelayaran dan shipbuilding |
| FACTION-131 | Pemerintahan Kerajaan Sylvaran | GOVERNMENT | KINGDOM-004 | Pemerintahan internal |
| FACTION-132 | Pertahanan Kerajaan Sylvaran | MILITARY | KINGDOM-004 | Keamanan dan pertahanan |
| FACTION-133 | Serikat Pengelola Hutan Sylvaran | FORESTRY / ECONOMIC | KINGDOM-004 | Hasil hutan dan frontier |
| FACTION-134 | Serikat Pengrajin Sylvaran | CRAFT / ECONOMIC | KINGDOM-004 | Kerajinan dan produksi |
| FACTION-141 | Pemerintahan Kerajaan Sahrad | GOVERNMENT | KINGDOM-005 | Pemerintahan internal |
| FACTION-142 | Pertahanan Kerajaan Sahrad | MILITARY | KINGDOM-005 | Keamanan dan pertahanan |
| FACTION-143 | Serikat Kafilah Sahrad | MERCANTILE / TRANSPORT | KINGDOM-005 | Perdagangan jarak jauh |
| FACTION-144 | Perserikatan Penggembala Sahrad | PASTORAL / ECONOMIC | KINGDOM-005 | Pastoralism dan ternak |

## 4. City-Level Factions

Setiap 20 kota memiliki satu faction administrasi kota.

| ID | City | Kingdom | Faction |
|---|---|---|---|
| FACTION-201 | Varenhold | KINGDOM-001 | Administrasi Kota Varenhold |
| FACTION-202 | Averen | KINGDOM-001 | Administrasi Kota Averen |
| FACTION-203 | Goldmere | KINGDOM-001 | Administrasi Kota Goldmere |
| FACTION-204 | Thornwick | KINGDOM-001 | Administrasi Kota Thornwick |
| FACTION-205 | Durnhaven | KINGDOM-002 | Administrasi Kota Durnhaven |
| FACTION-206 | Kharhold | KINGDOM-002 | Administrasi Kota Kharhold |
| FACTION-207 | Ferren | KINGDOM-002 | Administrasi Kota Ferren |
| FACTION-208 | Frostwatch | KINGDOM-002 | Administrasi Kota Frostwatch |
| FACTION-209 | Port Aureon | KINGDOM-003 | Administrasi Kota Port Aureon |
| FACTION-210 | Southport | KINGDOM-003 | Administrasi Kota Southport |
| FACTION-211 | Azurehold | KINGDOM-003 | Administrasi Kota Azurehold |
| FACTION-212 | Westhaven | KINGDOM-003 | Administrasi Kota Westhaven |
| FACTION-213 | Elaris | KINGDOM-004 | Administrasi Kota Elaris |
| FACTION-214 | Sylford | KINGDOM-004 | Administrasi Kota Sylford |
| FACTION-215 | Riverwyn | KINGDOM-004 | Administrasi Kota Riverwyn |
| FACTION-216 | Wildmere | KINGDOM-004 | Administrasi Kota Wildmere |
| FACTION-217 | Qasrane | KINGDOM-005 | Administrasi Kota Qasrane |
| FACTION-218 | Sarakh | KINGDOM-005 | Administrasi Kota Sarakh |
| FACTION-219 | Caravanser | KINGDOM-005 | Administrasi Kota Caravanser |
| FACTION-220 | Sunscar | KINGDOM-005 | Administrasi Kota Sunscar |

All city factions:

```text
FACTION_CLASS: CANON
TYPE: CITY_GOVERNMENT
OPERATING_SCOPE: respective CITY_ID
PARENT_AUTHORITY: respective KINGDOM_ID
LEADERSHIP: ???
GOALS: Administrasi kota dan kepentingan lokal yang sah
INTERESTS: Ketertiban, layanan, perdagangan, infrastruktur, kebutuhan kota
CURRENT_STATE: Active
TERRITORY_OR_INFLUENCE: City scope
CORE_RELATIONS: ???
ORIGIN: Admin Canon
HISTORY: ???
CANON_STATUS: ACTIVE
```

## 5. Settlement-Level Policy

Tidak ada faction settlement spesifik yang dibuat pada v1.0.

40 settlement tetap memiliki konteks komunitas lokal melalui Geography/Population Model. Faction lokal dapat muncul secara Dynamic bila dibutuhkan; jika menjadi material dan persisten, gunakan `DYNAMIC_PERSISTENT` tanpa otomatis menjadi Canon.

## 6. Noble House Factions — Canon

Noble House adalah faction type `NOBLE_HOUSE` dan memiliki registry terpisah di `factions/NOBLE_HOUSES_CANON.md`.

| ID | Name | Kingdom | Function |
|---|---|---|---|
| NOBLE-HOUSE-001 | House Varen | KINGDOM-001 | Royal House / Crown succession |
| NOBLE-HOUSE-002 | House Goldriver | KINGDOM-001 | Agrarian and riverine stewardship |
| NOBLE-HOUSE-003 | House Brann | KINGDOM-002 | Royal House / Crown succession |
| NOBLE-HOUSE-004 | House Ironvein | KINGDOM-002 | Mineral, mountain route, and defense interests |
| NOBLE-HOUSE-005 | House Aureon | KINGDOM-003 | Royal House / Crown succession |
| NOBLE-HOUSE-006 | House Tideward | KINGDOM-003 | Maritime and coastal infrastructure |
| NOBLE-HOUSE-007 | House Sylvar | KINGDOM-004 | Royal House / Crown succession |
| NOBLE-HOUSE-008 | House Thornward | KINGDOM-004 | Forest frontier and river-route stewardship |
| NOBLE-HOUSE-009 | House Qasrane | KINGDOM-005 | Royal House / Crown succession |
| NOBLE-HOUSE-010 | House Dustveil | KINGDOM-005 | Caravan and arid frontier stewardship |

All ten houses are `CANON`, `ACTIVE`, and operate under the authority boundaries of `37_NOBILITY_SYSTEM.md` and the kingdom-specific variation Canon.

## 7. Cross-Territorial Factions

```text
CROSS_TERRITORIAL_CANON_FACTIONS: NONE YET
```

## 8. Political Relations

No specific political relation is inferred merely from registry membership. Allowed relationship states remain `ALLY`, `FRIENDLY`, `NEUTRAL`, `TENSE`, `HOSTILE`, `AT_WAR`.

Specific House↔House, House↔Crown, House↔Guild, and Kingdom↔Kingdom relations must be separately Canonized or resolved from established state.

## 9. NPC Dependency

```text
FACTION CANON
↓
NOBLE HOUSE / GOVERNANCE CONTEXT
↓
NPC MASTER LIST
↓
INDIVIDUAL CANON NPC
```

Membership, rank, authority, access, reputation, resources, and personal relationships are not inherited automatically by NPCs.

## 10. Registry Status

```text
EMPIRE-LEVEL CANON FACTIONS: 3
KINGDOM-LEVEL CANON FACTIONS: 20
CITY-LEVEL CANON FACTIONS: 20
CANON NOBLE HOUSES: 10
SETTLEMENT-LEVEL SPECIFIC CANON FACTIONS: 0
ADDITIONAL CROSS-TERRITORIAL CANON FACTIONS: 0
TOTAL CURRENT CANON FACTIONS: 53
INDIVIDUAL CANON NPC CREATED: 15
```

## 11. Final Principle

> **Faction dan Noble House dibuat karena dunia membutuhkannya, bukan karena NPC Coverage Matrix membutuhkan angka. Organisasi menyediakan konteks; NPC individual tetap berada pada layer terpisah.**
