# ELDORIA WORLD — CANON NPC REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Registry dan index NPC penting yang ditetapkan sebagai Canon resmi Eldoria.

## 1. Scope

Registry ini hanya mencatat **NPC Canon penting**, bukan seluruh populasi dunia.

Populasi biasa tetap ditangani oleh Population Model + Dynamic NPC Generation.

## 2. Minimum Canon NPC Coverage

```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC
KEKAISARAN → ≥ 25 Canon NPC
```

Angka tersebut adalah minimum. Wilayah dapat memiliki lebih banyak NPC Canon sesuai kepentingan dunia.

## 3. Canon NPC Authority

Setiap Canon NPC wajib memiliki stable `NPC_ID` dan record resmi.

Minimal record:

```text
NPC_ID
NPC_CLASS: CANON
NAME
ROLE
SETTLEMENT / REGION
FACTION
BACKGROUND
GOALS
CORE_RELATIONSHIPS
CAPABILITIES
KNOWLEDGE_BOUNDARY
CANON_ORIGIN
```

Current condition/state berada pada NPC State layer yang relevan.

## 4. Runtime Rule

Jika Player berinteraksi dengan tokoh Canon, AI GM wajib mencari dan menggunakan record Canon yang sesuai sebelum melakukan generation.

Canon NPC tidak boleh digantikan Dynamic NPC dengan identity berbeda hanya karena record Canon belum dimuat.

## 5. Registered Canon NPC

### NPC-CANON-001 — Alaric Veyn
```text
NPC_ID: NPC-CANON-001
NPC_CLASS: CANON
NAME: Alaric Veyn
RACE_CANON_ID: RACE-001
ROLE: Pejabat Administrasi Kekaisaran — Pengawas Koordinasi Antar-Kerajaan
EMPIRE_ID: EMPIRE-001
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
FACTION: FACTION-001 — Pemerintahan Kekaisaran Valthera
CANON_STATUS: ACTIVE
RECORD: npcs/canon/NPC-CANON-001.md
```

### NPC-CANON-002 — Seraphine Darr
```text
NPC_ID: NPC-CANON-002
NPC_CLASS: CANON
NAME: Seraphine Darr
RACE_CANON_ID: RACE-001
ROLE: Pejabat Koordinasi Pertahanan Kekaisaran — Penghubung Antar-Kerajaan
EMPIRE_ID: EMPIRE-001
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
FACTION: FACTION-002 — Pertahanan Kekaisaran Valthera
CANON_STATUS: ACTIVE
RECORD: npcs/canon/NPC-CANON-002.md
```

### NPC-CANON-003 — Corvin Hale
```text
NPC_ID: NPC-CANON-003
NPC_CLASS: CANON
NAME: Corvin Hale
RACE_CANON_ID: RACE-003
ROLE: Koordinator Administrasi Perdagangan Kekaisaran — Penghubung Jalur Antar-Kerajaan
EMPIRE_ID: EMPIRE-001
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
FACTION: FACTION-003 — Administrasi Perdagangan Kekaisaran
CANON_STATUS: ACTIVE
RECORD: npcs/canon/NPC-CANON-003.md
```

### NPC-CANON-004 — Mirelle Ordan
```text
NPC_ID: NPC-CANON-004
NPC_CLASS: CANON
NAME: Mirelle Ordan
RACE_CANON_ID: RACE-002
ROLE: Pemeriksa Catatan Administrasi Kekaisaran — Verifikasi Antar-Wilayah
EMPIRE_ID: EMPIRE-001
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
FACTION: FACTION-001 — Pemerintahan Kekaisaran Valthera
CANON_STATUS: ACTIVE
RECORD: npcs/canon/NPC-CANON-004.md
```

### NPC-CANON-005 — Garran Voss
```text
NPC_ID: NPC-CANON-005
NPC_CLASS: CANON
NAME: Garran Voss
RACE_CANON_ID: RACE-006
ROLE: Koordinator Catatan dan Logistik Pertahanan Kekaisaran
EMPIRE_ID: EMPIRE-001
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
FACTION: FACTION-002 — Pertahanan Kekaisaran Valthera
CANON_STATUS: ACTIVE
RECORD: npcs/canon/NPC-CANON-005.md
```

## 6. Registration Template

```text
NPC_ID: NPC-CANON-???
NPC_CLASS: CANON
NAME: ???
ROLE: ???
SETTLEMENT / REGION: ???
FACTION: ???
BACKGROUND: ???
GOALS: ???
CORE_RELATIONSHIPS: ???
CAPABILITIES: ???
KNOWLEDGE_BOUNDARY: ???
CANON_ORIGIN: Admin Canon
```

`???` berarti belum ditentukan.

## 7. Current Status

```text
EMPIRE CANON NPC CREATED: 5 / ≥25 target coverage
KINGDOM CANON NPC CREATED: 0
CITY CANON NPC CREATED: 0
SETTLEMENT CANON NPC CREATED: 0
TOTAL INDIVIDUAL CANON NPC CREATED: 5
```

> Coverage target bukan alasan pembuatan NPC. Setiap NPC harus memiliki fungsi nyata, agency, konteks Canon, dan Origin yang dapat diverifikasi.
