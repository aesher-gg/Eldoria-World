# ELDORIA WORLD — CANON NPC CREATION PLAN v1.0

> **Authority:** Admin
> **Status:** Development Planning Canon
> **Source:** `npcs/COVERAGE_GAP_MATRIX.md`, `npcs/COVERAGE_MATRIX_v1_0.md`, `npcs/CANON_REGISTRY.md`, `world/CANON_GEOGRAPHY.md`, Kingdom Geography files, `factions/CANON_REGISTRY.md`, `16_NPC_SYSTEM.md`
> **Purpose:** Menentukan urutan pembuatan Canon NPC berdasarkan kebutuhan dunia nyata dan overlap scope yang sah, bukan filler quota.

## 1. Current Verified State

```text
UNIQUE CANON NPC: 21
OFFICIAL SCOPE UNITS: 66
OFFICIAL TARGET: 295
ACTUAL OFFICIAL SCOPE COVERAGE: 45
OFFICIAL GAP: 250
OFFICIAL PROGRESS: 15.25%

EMPIRE: 21 / 25       → gap 4
KINGDOM: 3 / 10 each  → gap 7 each
CITY: 9 / 5 aggregate target per city → 13 cities still at 0
SETTLEMENT: 0 / 3 each → all 40 settlements at 0
FACTION/HOUSE: 21 assignments → no numeric target
```

`???` tidak dihitung sebagai assignment. Coverage dihitung per field nyata; satu NPC dapat menghasilkan beberapa assignment.

## 2. Key Finding

### 2.1 Settlement adalah bottleneck struktural

Semua 40 settlement memiliki coverage 0. Target settlement adalah 3 NPC per settlement. Karena satu Canon NPC yang valid ditempatkan pada settlement juga secara geografis dapat menambah assignment untuk:

```text
SETTLEMENT + CITY + KINGDOM + EMPIRE
```

maka NPC settlement adalah jalur overlap paling kuat untuk memperbaiki empat scope geografis sekaligus.

### 2.2 Jangan mengejar Empire secara terpisah

Empire hanya kekurangan 4 assignment. Membuat 4 NPC empire-only akan memperbaiki angka Empire tetapi tidak menyentuh bottleneck settlement dan city. Karena itu prioritas Admin bukan membuat NPC Empire-only.

### 2.3 Jangan menutup gap Kingdom dengan NPC Kingdom-only

Setiap Kingdom kekurangan 7 assignment, tetapi semua kingdom juga memiliki city dan settlement yang jauh lebih kosong. NPC yang benar-benar dibutuhkan sebaiknya lahir dari konteks lokal city/settlement sehingga assignment Kingdom merupakan efek overlap yang sah.

### 2.4 Faction digunakan sebagai konteks, bukan target angka

Faction/Noble House tidak memiliki target numerik pada Matrix v1.0. Karena itu NPC tidak dibuat hanya untuk menambah faction assignment. Jika role NPC secara alami membutuhkan organisasi yang sudah Canon, faction dapat menjadi konteks yang sah setelah membership/role benar-benar ditetapkan.

Settlement-specific Canon faction belum ada. Admin tidak membuat faction baru hanya untuk menempelkan NPC ke settlement.

## 3. Creation Principle

Urutan pembuatan:

```text
WORLD FUNCTION
↓
CITY / SETTLEMENT NEED
↓
KINGDOM ROLE
↓
EXISTING FACTION CONTEXT, IF JUSTIFIED
↓
NPC ROLE + AGENCY + KNOWLEDGE BOUNDARY
↓
CANON NPC
↓
COVERAGE RECALCULATION
```

Setiap NPC harus:

- memiliki fungsi material;
- berada pada settlement yang benar-benar Canon;
- sekaligus memiliki City dan Kingdom parent yang valid;
- menggunakan faction yang memang relevan, bila ada;
- tidak diberi authority yang tidak didukung Law/Governance/Nobility Canon;
- tidak diberi race hanya berdasarkan nama/tempat;
- memiliki agency, goals, needs, capabilities, knowledge boundary, Origin, dan state yang dapat dipertanggungjawabkan;
- tidak menjadi duplicate dari NPC yang sudah ada.

## 4. Batch 1 — Five-Kingdom Settlement Anchors

**Status: LAYAK UNTUK DIBUAT SETELAH RECORD INDIVIDUAL DISELESAIKAN.**

Batch pertama sebaiknya menyentuh satu city yang saat ini 0-coverage dari masing-masing kingdom dan satu settlement yang relevan dengan fungsi city tersebut. Ini memberi pemerataan awal tanpa memusatkan pembangunan hanya pada satu kerajaan.

| Kingdom | City target | Settlement target | Existing world function | Candidate NPC function | Existing faction context to validate |
|---|---|---|---|---|---|
| Valedorn | CITY-002 Averen | SETTLEMENT-003 Rivergate | River crossing, bongkar-muat, transport sungai | pengelola/koordinator lalu lintas sungai lokal | CITY-002 administration + relevant Valedorn trade context |
| Brannor | CITY-006 Kharhold | SETTLEMENT-011 Valecrest | Pertanian lembah, pengolahan pangan, transport lokal | koordinator suplai/transport lembah | CITY-006 administration + relevant Brannor trade/agricultural context |
| Mariselle | CITY-010 Southport | SETTLEMENT-019 Saltmere | Produksi garam, perikanan, suplai pesisir | pengelola produksi/suplai pesisir | CITY-010 administration + relevant Mariselle maritime/trade context |
| Sylvaran | CITY-014 Sylford | SETTLEMENT-027 Oakmere | Pertanian lembah, peternakan, pertukaran lokal | pengelola hasil pertanian/peternakan | CITY-014 administration + relevant Sylvaran economic context |
| Sahrad | CITY-018 Sarakh | SETTLEMENT-035 Grassrest | Penggembalaan, perdagangan musiman, suplai | koordinator pastoral/seasonal trade | CITY-018 administration + relevant Sahrad pastoral/trade context |

**Mengapa lima titik ini:** kelimanya berasal dari city yang masih 0 coverage, tersebar merata di lima kingdom, dan settlement yang dipilih memiliki fungsi ekonomi/transportasi yang jelas dalam Geography Canon. Tidak diperlukan faction baru untuk menjalankannya.

### Expected geographic effect if all 5 are validly Canonized

```text
EMPIRE:      21 → 26
KINGDOM:     masing-masing +1 → 4 / 10
CITY:        9 → 14 assignments aggregate
SETTLEMENT:  0 → 5 assignments
```

Kenaikan di atas adalah **proyeksi coverage**, bukan fakta sebelum NPC benar-benar dibuat dan diregistrasikan.

## 5. Batch 2 — Complete the Same Five City Anchors

Setelah Batch 1 diverifikasi, prioritas berikutnya adalah menambah NPC pada settlement kedua di masing-masing city yang sama:

```text
Averen     → SETTLEMENT-004 Millhaven
Kharhold   → SETTLEMENT-012 Ironbrook
Southport  → SETTLEMENT-020 Gullhaven
Sylford    → SETTLEMENT-028 Fernwatch
Sarakh     → SETTLEMENT-036 Herdwatch
```

Tujuan batch ini adalah memperkuat city yang sebelumnya 0 tanpa membuat cluster NPC hanya di satu titik. Settlement kedua memiliki fungsi berbeda dari settlement pertama sehingga role NPC tidak perlu duplicate.

## 6. Batch 3 — First Three-Coverage Candidates

Setelah dua settlement pertama pada lima city anchor terisi, pilih city berikutnya berdasarkan kebutuhan fungsi yang belum terwakili, bukan sekadar nama kota.

Kandidat awal:

```text
Valedorn  → CITY-004 Thornwick → SETTLEMENT-007 Briarford / SETTLEMENT-008 Greenhollow
Brannor   → CITY-008 Frostwatch → SETTLEMENT-015 Pinewatch / SETTLEMENT-016 Coldmere
Mariselle → CITY-012 Westhaven → SETTLEMENT-023 Driftwood / SETTLEMENT-024 Stormbay
Sylvaran  → CITY-016 Wildmere → SETTLEMENT-031 Pinecross / SETTLEMENT-032 Thornrest
Sahrad    → CITY-020 Sunscar → SETTLEMENT-039 Sandmere / SETTLEMENT-040 Farwatch
```

Alasannya adalah seluruh titik tersebut merupakan frontier-sensitive/remote contexts dalam Geography Canon, sehingga memiliki kebutuhan dunia yang berbeda dari pusat ekonomi biasa: keamanan, logistik, resource gathering, route monitoring, dan survival services.

## 7. Batch 4+ — Systematic Settlement Coverage

Sesudah anchor cities memiliki representasi material, pembangunan bergerak secara sistematis melalui remaining zero-coverage settlements dan city scopes.

Prioritas umum:

1. settlement frontier / remote;
2. settlement dengan fungsi transportasi atau resource chokepoint;
3. settlement yang mendukung city dengan coverage rendah;
4. settlement ekonomi utama;
5. settlement lain sampai target minimum tercapai.

Tidak ada settlement yang boleh diberi NPC hanya karena harus mengisi angka. Jika suatu settlement belum memerlukan Canon NPC, Dynamic NPC tetap menjadi mekanisme populasi yang sah sampai ada kebutuhan material untuk Canonization.

## 8. Faction / Noble House Strategy

Faction assignment harus mengikuti role NPC yang nyata.

Contoh konteks yang boleh dipertimbangkan setelah validasi:

```text
CITY GOVERNMENT
→ NPC dengan fungsi administrasi / layanan / koordinasi lokal

KINGDOM ECONOMIC FACTION
→ NPC dengan fungsi perdagangan, pertanian, pertambangan, maritim,
   kehutanan, pastoralism, atau transport sesuai faction Canon

NOBLE HOUSE
→ hanya jika role NPC memang berada dalam House dan hubungan tersebut
   ditetapkan sebagai Canon; bukan karena settlement berada dekat domain House
```

Membership tidak boleh disimpulkan otomatis dari lokasi. House membership juga tidak memberi title, authority, wealth, command, atau magic tanpa dasar Canon yang sesuai.

## 9. Anti-Filler Gate

Batch baru **tidak boleh dibuat** jika:

- NPC hanya diperlukan untuk menaikkan counter;
- role dapat dilakukan oleh Dynamic NPC dan belum material untuk Canon;
- faction membership hanya dibuat untuk menambah assignment;
- settlement dipilih tanpa fungsi dunia yang jelas;
- NPC merupakan duplicate fungsi/identity yang tidak diperlukan;
- authority, title, House membership, atau domain dibuat tanpa Law/Governance basis;
- Race ditentukan dari nama atau stereotype;
- record individual belum memiliki Origin dan knowledge boundary yang sah.

## 10. Coverage Recalculation Rule

Setelah setiap batch:

```text
CANON_REGISTRY
↓
COVERAGE_MATRIX
↓
COVERAGE_GAP_MATRIX
↓
VERIFY EACH NPC ASSIGNMENT
↓
DECIDE NEXT BATCH
```

Jangan menggunakan jumlah NPC unik sebagai pengganti coverage assignment.

## 11. Current Admin Decision

```text
NEXT ACTION: Batch 1 planning approved
NPC CREATED IN THIS PLAN: 0
NPC TO CREATE IMMEDIATELY: 0
FIRST TARGETS:
  SETTLEMENT-003 Rivergate
  SETTLEMENT-011 Valecrest
  SETTLEMENT-019 Saltmere
  SETTLEMENT-027 Oakmere
  SETTLEMENT-035 Grassrest
```

Batch 1 adalah **candidate creation batch**, bukan lima NPC yang otomatis sudah Canon. Individual records harus dibuat dan diverifikasi satu per satu sebelum coverage dihitung.

## 12. Final Principle

> **Coverage Gap Matrix menentukan di mana kekurangan berada; Geography, Population, Faction, Governance, dan fungsi dunia menentukan apakah NPC memang layak dibuat. Overlap adalah efisiensi Canon yang sah, bukan alasan untuk mengarang assignment.**
