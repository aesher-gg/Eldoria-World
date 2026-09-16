# ELDORIA WORLD — CANON NPC COVERAGE MATRIX v1.1

> **Authority:** Admin  
> **Status:** Admin Canon v1.1  
> **Purpose:** Master coverage matrix untuk memastikan kebutuhan NPC benar-benar mencerminkan dunia hidup Eldoria yang dimainkan oleh Player dengan Qwen sebagai AI Game Master.  
> **Scope:** Planning / coverage only.

## 1. Prinsip Utama — Basis NPC vs Konteks Geografis

Mulai v1.1, Coverage Matrix membedakan dua hal yang sebelumnya tercampur:

### A. PRIMARY BASE COVERAGE
Menjawab pertanyaan:

> **NPC ini benar-benar berbasis/berfungsi utama di scope mana?**

Setiap NPC hanya memiliki **satu `PRIMARY_SCOPE`**.

```text
PRIMARY_SCOPE
├── EMPIRE
├── KINGDOM
├── CITY
└── SETTLEMENT
```

`PRIMARY_SCOPE` ditentukan berdasarkan pusat fungsi, pekerjaan, kewenangan, dan aktivitas utama NPC — bukan sekadar karena NPC memiliki `EMPIRE_ID`, `KINGDOM_ID`, atau berada secara hierarkis di bawah wilayah tersebut.

Contoh:
- Kaisar / pejabat administrasi Kekaisaran → `EMPIRE`
- Raja / pejabat fungsi kerajaan / kepala Noble House tingkat kerajaan → `KINGDOM`
- pejabat atau pekerja yang fungsi utamanya terikat pada satu kota → `CITY`
- warga/pekerja yang fungsi utamanya terikat pada satu settlement → `SETTLEMENT`

**Hierarchical containment tidak otomatis menjadi Primary Base.**

### B. HIERARCHICAL CONTEXT COVERAGE
Field berikut tetap dicatat untuk mengetahui konteks geografis NPC:

```text
EMPIRE_ID
KINGDOM_ID
CITY_ID
SETTLEMENT_ID
```

NPC berbasis Settlement tetap memiliki konteks City → Kingdom → Empire, tetapi konteks tersebut **tidak mengubah `PRIMARY_SCOPE` menjadi City/Kingdom/Empire**.

Dengan demikian:

> `PRIMARY_SCOPE` = tempat/fungsi utama NPC hidup dan bekerja.  
> `*_ID` = konteks geografis/hierarki tempat NPC berada.

## 2. Scope Targets

Target v1.1 tetap dipertahankan sebagai target kebutuhan dunia:

| Scope | Units | Minimum each | Minimum coverage |
|---|---:|---:|---:|
| Empire | 1 | ≥25 | ≥25 |
| Kingdom | 5 | ≥10 | ≥50 |
| City | 20 | ≥5 | ≥100 |
| Settlement | 40 | ≥3 | ≥120 |
| **Total primary-base target** | **66** | — | **≥295** |

Target ini sekarang berlaku terhadap **PRIMARY BASE COVERAGE**, sehingga satu NPC tidak dapat memenuhi dua target scope sekaligus.

`Faction / Noble House` tetap merupakan assignment tambahan tanpa target numerik pada v1.1 dan tidak masuk denominator 295.

## 3. Aturan Perhitungan

### Primary Base
```text
Setiap NPC → tepat 1 PRIMARY_SCOPE
```

Contoh:
```text
NPC-011 Aurelian Valthera
PRIMARY_SCOPE: EMPIRE
EMPIRE_ID: EMPIRE-001
```

```text
NPC-022 Maren Vale
PRIMARY_SCOPE: SETTLEMENT
SETTLEMENT_ID: SETTLEMENT-003
CITY_ID: CITY-002
KINGDOM_ID: KINGDOM-001
EMPIRE_ID: EMPIRE-001
```

NPC-022 dihitung:
- +1 Settlement Primary
- +0 City Primary
- +0 Kingdom Primary
- +0 Empire Primary

tetapi tetap memiliki konteks geografis City, Kingdom, dan Empire.

### Hierarchical Context
Field `*_ID` dapat digunakan untuk mengetahui di mana NPC berada secara geografis, tetapi **tidak boleh digunakan untuk mengklaim target Primary Base secara otomatis**.

`???` tidak dihitung sebagai coverage.

## 4. Current Audited Primary Base Coverage — 2026-09-16

| Primary scope | Actual | Target | Gap |
|---|---:|---:|---:|
| **Empire** | **6** | ≥25 | **19** |
| **Kingdom** | **15** | ≥50 | **35** |
| **City** | **0** | ≥100 | **100** |
| **Settlement** | **5** | ≥120 | **115** |
| **TOTAL PRIMARY NPC** | **26** | **≥295** | **269** |

**Primary-base coverage: 26 / 295 = 8.81%.**

Ini adalah metrik yang sekarang digunakan untuk menilai apakah dunia memiliki cukup NPC yang benar-benar berbasis pada masing-masing level.

## 5. Empire — Primary Base

| ID | Name | Target | Actual Primary | Gap | NPCs |
|---|---|---:|---:|---:|---|
| EMPIRE-001 | Kekaisaran Valthera | 25 | **6** | **19** | NPC-001, NPC-002, NPC-003, NPC-004, NPC-005, NPC-011 |

### Catatan
NPC-006–026 tidak dihitung sebagai Empire Primary hanya karena memiliki `EMPIRE_ID: EMPIRE-001`. Mereka memiliki basis fungsi yang lebih spesifik pada Kingdom, Noble House, City, atau Settlement.

## 6. Kingdom — Primary Base

| ID | Kingdom | Target | Actual Primary | Gap | NPCs |
|---|---|---:|---:|---:|---|
| KINGDOM-001 | Valedorn | 10 | **3** | **7** | NPC-006, NPC-012, NPC-017 |
| KINGDOM-002 | Brannor | 10 | **3** | **7** | NPC-007, NPC-013, NPC-018 |
| KINGDOM-003 | Mariselle | 10 | **3** | **7** | NPC-008, NPC-014, NPC-019 |
| KINGDOM-004 | Sylvaran | 10 | **3** | **7** | NPC-009, NPC-015, NPC-020 |
| KINGDOM-005 | Sahrad | 10 | **3** | **7** | NPC-010, NPC-016, NPC-021 |
| **TOTAL** | | **50** | **15** | **35** | |

## 7. City — Primary Base

Tidak ada NPC Canon saat ini yang ditetapkan dengan `PRIMARY_SCOPE: CITY`.

| ID | City | Kingdom | Target | Actual Primary | Gap |
|---|---|---|---:|---:|---:|
| CITY-001 | Varenhold | K-001 | 5 | 0 | 5 |
| CITY-002 | Averen | K-001 | 5 | 0 | 5 |
| CITY-003 | Goldmere | K-001 | 5 | 0 | 5 |
| CITY-004 | Thornwick | K-001 | 5 | 0 | 5 |
| CITY-005 | Durnhaven | K-002 | 5 | 0 | 5 |
| CITY-006 | Kharhold | K-002 | 5 | 0 | 5 |
| CITY-007 | Ferren | K-002 | 5 | 0 | 5 |
| CITY-008 | Frostwatch | K-002 | 5 | 0 | 5 |
| CITY-009 | Port Aureon | K-003 | 5 | 0 | 5 |
| CITY-010 | Southport | K-003 | 5 | 0 | 5 |
| CITY-011 | Azurehold | K-003 | 5 | 0 | 5 |
| CITY-012 | Westhaven | K-003 | 5 | 0 | 5 |
| CITY-013 | Elaris | K-004 | 5 | 0 | 5 |
| CITY-014 | Sylford | K-004 | 5 | 0 | 5 |
| CITY-015 | Riverwyn | K-004 | 5 | 0 | 5 |
| CITY-016 | Wildmere | K-004 | 5 | 0 | 5 |
| CITY-017 | Qasrane | K-005 | 5 | 0 | 5 |
| CITY-018 | Sarakh | K-005 | 5 | 0 | 5 |
| CITY-019 | Caravanser | K-005 | 5 | 0 | 5 |
| CITY-020 | Sunscar | K-005 | 5 | 0 | 5 |
| **TOTAL** | | | **100** | **0** | **100** |

**Catatan penting:** NPC-006–010 dan NPC-012–016 memiliki `CITY_ID`, tetapi fungsi Canon mereka saat ini berada pada level Kingdom. Karena itu mereka tidak dihitung sebagai City Primary.

## 8. Settlement — Primary Base

| ID | Settlement | Parent City | Target | Actual Primary | Gap |
|---|---|---|---:|---:|---:|
| SETTLEMENT-003 | Rivergate | CITY-002 | 3 | 1 | 2 |
| SETTLEMENT-011 | Valecrest | CITY-006 | 3 | 1 | 2 |
| SETTLEMENT-019 | Saltmere | CITY-010 | 3 | 1 | 2 |
| SETTLEMENT-027 | Oakmere | CITY-014 | 3 | 1 | 2 |
| SETTLEMENT-035 | Grassrest | CITY-018 | 3 | 1 | 2 |
| **Other 35 settlements** | | | **105** | **0** | **105** |
| **TOTAL** | | | **120** | **5** | **115** |

## 9. Hierarchical Context Audit

Untuk menjaga data lama tetap dapat dibaca, konteks geografis aktual juga diaudit secara terpisah.

| Context field | Current assignments | Fungsi |
|---|---:|---|
| EMPIRE_ID | 26 | Menunjukkan konteks wilayah Kekaisaran |
| KINGDOM_ID | 20 | Menunjukkan konteks Kingdom |
| CITY_ID | **15** | Menunjukkan konteks City yang tercatat |
| SETTLEMENT_ID | 5 | Menunjukkan settlement yang tercatat |

**Bug yang ditemukan:** `CITY-019 Caravanser` sebelumnya tercatat 0, padahal NPC-010 memiliki `CITY_ID: CITY-019`. Maka hierarchical City context yang benar adalah **15**, bukan 14.

Hierarchical context total:
```text
26 Empire + 20 Kingdom + 15 City + 5 Settlement = 66 assignments
```

Angka 66 ini **bukan primary-base coverage** dan tidak digunakan untuk memenuhi denominator 295.

## 10. Faction / Noble House

| Assignment class | Primary assignments | Secondary contexts |
|---|---:|---:|
| Imperial factions | 5 | 0 |
| Kingdom factions | 15 | 5 |
| Noble Houses | 6 | 0 |
| **Total primary faction assignments** | **26** | **5 secondary contexts** |

Faction affiliation tetap merupakan konteks tambahan. Faction tidak otomatis menentukan `PRIMARY_SCOPE` jika fungsi utama NPC berada pada scope lain.

## 11. Batch 1 Reclassification

Batch 1 tetap valid, tetapi sekarang dibaca dengan definisi Primary Base:

| NPC | PRIMARY_SCOPE | Primary Base | Hierarchical Context |
|---|---|---|---|
| NPC-022 Maren Vale | SETTLEMENT | SETTLEMENT-003 Rivergate | CITY-002 → K-001 → E-001 |
| NPC-023 Borin Keld | SETTLEMENT | SETTLEMENT-011 Valecrest | CITY-006 → K-002 → E-001 |
| NPC-024 Selene Varo | SETTLEMENT | SETTLEMENT-019 Saltmere | CITY-010 → K-003 → E-001 |
| NPC-025 Elira Fen | SETTLEMENT | SETTLEMENT-027 Oakmere | CITY-014 → K-004 → E-001 |
| NPC-026 Rafiq Sahr | SETTLEMENT | SETTLEMENT-035 Grassrest | CITY-018 → K-005 → E-001 |

Batch 1 tetap memberikan **5 Settlement Primary**, bukan City/Kingdom/Empire Primary.

## 12. Corrected Understanding

Sebelumnya matrix menggunakan:
```text
EMPIRE_ID → Empire coverage
KINGDOM_ID → Kingdom coverage
CITY_ID → City coverage
SETTLEMENT_ID → Settlement coverage
```

Aturan tersebut valid untuk **hierarchical context**, tetapi terlalu longgar untuk menjawab kebutuhan dunia hidup.

Mulai v1.1:
```text
PRIMARY_SCOPE → primary-base coverage
*_ID           → hierarchical context
```

Dengan demikian NPC tidak dapat dianggap sebagai NPC Empire hanya karena berada di wilayah Kekaisaran.

## 13. Design Principle untuk Qwen Runtime

NPC Canon dibuat untuk memberikan dunia yang hidup ketika Player bermain dan Qwen bertindak sebagai AI Game Master.

Karena itu coverage harus membantu menjawab:
- Siapa yang benar-benar hidup dan bekerja di pusat Kekaisaran?
- Siapa yang menjalankan fungsi lintas wilayah Kingdom?
- Siapa yang menjadi aktor tetap di City?
- Siapa yang membuat Settlement terasa hidup?
- Faction apa yang benar-benar menghubungkan mereka?

Coverage target tidak boleh dicapai dengan NPC filler atau dengan menghitung containment geografis sebagai basis NPC.

## 14. Canonization Rule

Sebelum NPC baru dibuat:
```text
Coverage Gap
→ Geography
→ Population
→ Governance
→ Faction
→ World Function
→ PRIMARY_SCOPE
→ Agency
→ Knowledge Boundary
→ Origin
→ State
→ Audit
→ Canonize
```

`PRIMARY_SCOPE` wajib dapat dipertanggungjawabkan dari fungsi utama NPC.

## Final Principle

> **NPC Canon adalah aktor dunia, bukan angka coverage.**
>
> **Basis NPC menentukan coverage utama. Hierarchical containment hanya menjelaskan konteks geografis.**
>
> **Tujuan akhir adalah dunia Eldoria yang hidup untuk Player + Qwen GM, bukan sekadar memenuhi 295 angka.**
