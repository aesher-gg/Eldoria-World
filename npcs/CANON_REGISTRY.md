# ELDORIA WORLD — CANON NPC REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Registry dan index NPC penting yang ditetapkan sebagai Canon resmi Eldoria.

## 1. Cakupan
Registry ini hanya mencatat **NPC Canon penting**, bukan seluruh populasi dunia. Populasi biasa tetap ditangani oleh Population Model + Dynamic NPC Generation.

## 2. Minimum Canon NPC Coverage
```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC
KEKAISARAN → ≥ 25 Canon NPC
```
Angka tersebut adalah target minimum coverage, bukan perintah untuk membuat NPC filler.

## 3. Aturan Canon NPC
Setiap Canon NPC wajib memiliki stable `NPC_ID` dan record resmi. Identity, fungsi, konteks faction, agency, batas pengetahuan, dan Origin harus dapat dipertanggungjawabkan terhadap Canon.

## 4. Aturan Runtime
Jika Player berinteraksi dengan tokoh Canon, AI GM wajib mencari dan menggunakan record Canon yang sesuai sebelum generation. Canon NPC tidak boleh digantikan Dynamic NPC dengan identity berbeda hanya karena record belum dimuat.

## 5. NPC Terdaftar

### NPC-CANON-001 — Alaric Veyn
```text
ROLE: Pejabat Administrasi Kekaisaran — Pengawas Koordinasi Antar-Kerajaan
RACE_CANON_ID: RACE-001
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-001
RECORD: npcs/canon/NPC-CANON-001.md
```

### NPC-CANON-002 — Seraphine Darr
```text
ROLE: Pejabat Koordinasi Pertahanan Kekaisaran — Penghubung Antar-Kerajaan
RACE_CANON_ID: RACE-001
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-002
RECORD: npcs/canon/NPC-CANON-002.md
```

### NPC-CANON-003 — Corvin Hale
```text
ROLE: Koordinator Administrasi Perdagangan Kekaisaran — Penghubung Jalur Antar-Kerajaan
RACE_CANON_ID: RACE-003
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-003
RECORD: npcs/canon/NPC-CANON-003.md
```

### NPC-CANON-004 — Mirelle Ordan
```text
ROLE: Pemeriksa Catatan Administrasi Kekaisaran — Verifikasi Antar-Wilayah
RACE_CANON_ID: RACE-002
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-001
RECORD: npcs/canon/NPC-CANON-004.md
```

### NPC-CANON-005 — Garran Voss
```text
ROLE: Koordinator Catatan dan Logistik Pertahanan Kekaisaran
RACE_CANON_ID: RACE-006
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-002
RECORD: npcs/canon/NPC-CANON-005.md
```

### NPC-CANON-006 — Edric Vale
```text
ROLE: Pengelola Distribusi Pangan Kerajaan Valedorn
RACE_CANON_ID: RACE-004
SETTLEMENT_ID: ???
CITY_ID: CITY-003
REGION_ID: REGION-003
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-104
RECORD: npcs/canon/NPC-CANON-006.md
```

### NPC-CANON-007 — Dorin Khar
```text
ROLE: Koordinator Operasional Pertambangan Brannor
RACE_CANON_ID: RACE-003
SETTLEMENT_ID: ???
CITY_ID: CITY-007
REGION_ID: REGION-007
KINGDOM_ID: KINGDOM-002
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-113
RECORD: npcs/canon/NPC-CANON-007.md
```

### NPC-CANON-008 — Marina Solenne
```text
ROLE: Koordinator Pelayaran dan Galangan Mariselle
RACE_CANON_ID: RACE-002
SETTLEMENT_ID: ???
CITY_ID: CITY-009
REGION_ID: REGION-009
KINGDOM_ID: KINGDOM-003
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-124
RECORD: npcs/canon/NPC-CANON-008.md
```

### NPC-CANON-009 — Elowen Thorne
```text
ROLE: Pengelola Hasil Hutan Sylvaran
RACE_CANON_ID: RACE-001
SETTLEMENT_ID: ???
CITY_ID: CITY-013
REGION_ID: REGION-013
KINGDOM_ID: KINGDOM-004
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-133
RECORD: npcs/canon/NPC-CANON-009.md
```

### NPC-CANON-010 — Rashid Qamar
```text
ROLE: Koordinator Jalur Kafilah Sahrad
RACE_CANON_ID: RACE-005
SETTLEMENT_ID: ???
CITY_ID: CITY-019
REGION_ID: REGION-019
KINGDOM_ID: KINGDOM-005
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-143
RECORD: npcs/canon/NPC-CANON-010.md
```

### NPC-CANON-011 — Aurelian Valthera
```text
ROLE: Kaisar Kekaisaran Valthera — Kepala Negara
RACE_CANON_ID: RACE-001
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-001
RECORD: npcs/canon/NPC-CANON-011.md
```

### NPC-CANON-012 — Cedric Varen
```text
ROLE: Raja Kerajaan Valedorn — Kepala Negara Kerajaan
RACE_CANON_ID: RACE-001
CITY_ID: CITY-001
REGION_ID: REGION-001
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-101
RECORD: npcs/canon/NPC-CANON-012.md
```

### NPC-CANON-013 — Tharok Brann
```text
ROLE: Raja Kerajaan Brannor — Kepala Negara Kerajaan
RACE_CANON_ID: RACE-003
CITY_ID: CITY-005
REGION_ID: REGION-005
KINGDOM_ID: KINGDOM-002
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-111
RECORD: npcs/canon/NPC-CANON-013.md
```

### NPC-CANON-014 — Celestine Aureon
```text
ROLE: Ratu Kerajaan Mariselle — Kepala Negara Kerajaan
RACE_CANON_ID: RACE-002
CITY_ID: CITY-009
REGION_ID: REGION-009
KINGDOM_ID: KINGDOM-003
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-121
RECORD: npcs/canon/NPC-CANON-014.md
```

### NPC-CANON-015 — Edrien Sylvar
```text
ROLE: Raja Kerajaan Sylvaran — Kepala Negara Kerajaan
RACE_CANON_ID: RACE-001
CITY_ID: CITY-013
REGION_ID: REGION-013
KINGDOM_ID: KINGDOM-004
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-131
RECORD: npcs/canon/NPC-CANON-015.md
```

### NPC-CANON-016 — Nadir Qasrane
```text
ROLE: Raja Kerajaan Sahrad — Kepala Negara Kerajaan
RACE_CANON_ID: RACE-001
CITY_ID: CITY-017
REGION_ID: REGION-017
KINGDOM_ID: KINGDOM-005
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-141
HOUSE: NOBLE-HOUSE-009 — House Qasrane
RECORD: npcs/canon/NPC-CANON-016.md
```

## 6. Status Coverage Saat Ini
```text
EMPIRE CANON NPC CREATED: 7 / ≥25 target coverage
KINGDOM-001 CANON NPC: 2 / ≥10
KINGDOM-002 CANON NPC: 2 / ≥10
KINGDOM-003 CANON NPC: 2 / ≥10
KINGDOM-004 CANON NPC: 2 / ≥10
KINGDOM-005 CANON NPC: 2 / ≥10
CITY CANON NPC CREATED: 0
SETTLEMENT CANON NPC CREATED: 0
TOTAL INDIVIDUAL CANON NPC CREATED: 16
```

## 7. Prinsip
Coverage target bukan alasan pembuatan NPC. Setiap NPC harus memiliki fungsi nyata, agency, konteks Canon, Race Canon yang valid, batas pengetahuan, dan Origin yang dapat diverifikasi. Pembuatan dilakukan dalam batch terkontrol maksimal 5 NPC.
