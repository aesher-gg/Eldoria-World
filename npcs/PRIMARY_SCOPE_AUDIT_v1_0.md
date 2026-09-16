# ELDORIA WORLD — PRIMARY_SCOPE AUDIT v1.0

> **Authority:** Admin
> **Status:** Admin Audit — PASS
> **Audit Date:** 2026-09-16
> **Scope:** Seluruh 26 Canon NPC yang saat ini terdaftar
> **Purpose:** Memverifikasi bahwa `PRIMARY_SCOPE` ditentukan berdasarkan fungsi utama NPC, bukan sekadar hierarchical containment.

## 1. Audit Rule

Setiap NPC wajib memiliki tepat satu `PRIMARY_SCOPE`:

```text
EMPIRE | KINGDOM | CITY | SETTLEMENT
```

Penentuan menggunakan kombinasi:
- fungsi/role utama;
- cakupan kewenangan dan aktivitas;
- konteks faction utama;
- konteks geografis;
- tujuan NPC;
- batas kewenangan yang dinyatakan pada record.

`EMPIRE_ID`, `KINGDOM_ID`, `CITY_ID`, dan `SETTLEMENT_ID` adalah hierarchical context dan tidak otomatis menentukan Primary Scope.

## 2. Individual Audit

| NPC | Nama | Fungsi Canon | Primary Scope | Primary Base | Hasil |
|---|---|---|---|---|---|
| NPC-001 | Alaric Veyn | Pengawas koordinasi administrasi antar-kerajaan | EMPIRE | EMPIRE-001 | PASS |
| NPC-002 | Seraphine Darr | Koordinasi pertahanan antar-kerajaan | EMPIRE | EMPIRE-001 | PASS |
| NPC-003 | Corvin Hale | Koordinasi administrasi perdagangan antar-kerajaan | EMPIRE | EMPIRE-001 | PASS |
| NPC-004 | Mirelle Ordan | Verifikasi catatan administrasi antar-wilayah | EMPIRE | EMPIRE-001 | PASS |
| NPC-005 | Garran Voss | Koordinasi catatan/logistik pertahanan kekaisaran | EMPIRE | EMPIRE-001 | PASS |
| NPC-006 | Edric Vale | Pengelolaan distribusi pangan dalam jaringan Valedorn | KINGDOM | KINGDOM-001 | PASS |
| NPC-007 | Dorin Khar | Koordinasi operasional pertambangan Brannor | KINGDOM | KINGDOM-002 | PASS |
| NPC-008 | Marina Solenne | Koordinasi pelayaran dan galangan Mariselle | KINGDOM | KINGDOM-003 | PASS |
| NPC-009 | Elowen Thorne | Pengelolaan hasil hutan Sylvaran | KINGDOM | KINGDOM-004 | PASS |
| NPC-010 | Rashid Qamar | Koordinasi jalur kafilah Sahrad | KINGDOM | KINGDOM-005 | PASS |
| NPC-011 | Aurelian Valthera | Kepala negara Kekaisaran Valthera | EMPIRE | EMPIRE-001 | PASS |
| NPC-012 | Cedric Varen | Kepala negara Kerajaan Valedorn | KINGDOM | KINGDOM-001 | PASS |
| NPC-013 | Tharok Brann | Kepala negara Kerajaan Brannor | KINGDOM | KINGDOM-002 | PASS |
| NPC-014 | Celestine Aureon | Kepala negara Kerajaan Mariselle | KINGDOM | KINGDOM-003 | PASS |
| NPC-015 | Edrien Sylvar | Kepala negara Kerajaan Sylvaran | KINGDOM | KINGDOM-004 | PASS |
| NPC-016 | Nadir Qasrane | Kepala negara Kerajaan Sahrad | KINGDOM | KINGDOM-005 | PASS |
| NPC-017 | Elian Goldriver | Kepala Noble House dengan kepentingan agraria-riverine | KINGDOM | KINGDOM-001 | PASS |
| NPC-018 | Durgan Ironvein | Kepala Noble House dengan kepentingan mineral dan jalur pegunungan | KINGDOM | KINGDOM-002 | PASS |
| NPC-019 | Lysara Tideward | Kepala Noble House dengan kepentingan maritim dan pesisir | KINGDOM | KINGDOM-003 | PASS |
| NPC-020 | Caelen Thornward | Kepala Noble House dengan fungsi frontier hutan dan jalur sungai | KINGDOM | KINGDOM-004 | PASS |
| NPC-021 | Samir Dustveil | Kepala Noble House dengan fungsi kafilah dan frontier arid | KINGDOM | KINGDOM-005 | PASS |
| NPC-022 | Maren Vale | Koordinator lalu lintas sungai Rivergate | SETTLEMENT | SETTLEMENT-003 | PASS |
| NPC-023 | Borin Keld | Koordinator suplai dan angkutan Valecrest | SETTLEMENT | SETTLEMENT-011 | PASS |
| NPC-024 | Selene Varo | Pengelola produksi garam dan suplai Saltmere | SETTLEMENT | SETTLEMENT-019 | PASS |
| NPC-025 | Elira Fen | Pengelola hasil pertanian dan ternak Oakmere | SETTLEMENT | SETTLEMENT-027 | PASS |
| NPC-026 | Rafiq Sahr | Koordinator pastoral dan perdagangan musiman Grassrest | SETTLEMENT | SETTLEMENT-035 | PASS |

## 3. Audit Findings

### A. Empire — PASS

NPC-001 sampai NPC-005 memiliki fungsi langsung pada administrasi, pertahanan, perdagangan, verifikasi, dan logistik **tingkat Kekaisaran**. NPC-011 adalah kepala negara Kekaisaran. Tidak ada alasan untuk menurunkan mereka ke Kingdom/City/Settlement.

**Empire Primary = 6:** NPC-001, 002, 003, 004, 005, 011.

### B. Kingdom — PASS

NPC-006 sampai NPC-010 memiliki fungsi ekonomi/operasional yang didefinisikan dalam konteks faction Kingdom dan cakupan kegiatan kerajaan. Mereka memiliki CITY_ID sebagai lokasi/konteks, tetapi fungsi Canon tidak ditetapkan sebagai administrasi satu kota.

NPC-012 sampai NPC-016 adalah kepala negara masing-masing Kingdom; fungsi utamanya jelas Kingdom-level.

NPC-017 sampai NPC-021 adalah kepala Noble House yang masing-masing beroperasi dalam konteks Kingdom. Noble House tidak otomatis menjadi City/Settlement actor.

**Kingdom Primary = 15:** tiga NPC per Kingdom.

### C. City — PASS / EMPTY

Tidak ada dari 26 NPC yang saat ini memiliki fungsi Canon yang secara eksplisit berpusat pada administrasi atau operasi satu City sebagai basis utama.

Khusus NPC-008 Marina Solenne, record menyebut lingkungan pelabuhan Port Aureon, tetapi role dan faction-nya berada pada fungsi pelayaran/galangan Mariselle yang tercatat sebagai faction Kingdom-level. Karena itu belum cukup bukti untuk mengubahnya menjadi City Primary.

Khusus NPC-006–010, keberadaan `CITY_ID` juga tidak cukup untuk menjadikan mereka City Primary.

**City Primary = 0.**

### D. Settlement — PASS

NPC-022 sampai NPC-026 memiliki fungsi yang secara eksplisit terikat pada satu settlement tertentu dan state/location aktif berada pada settlement tersebut. Mereka dirancang untuk menghidupkan aktor lokal.

**Settlement Primary = 5:** NPC-022, 023, 024, 025, 026.

## 4. Final Primary Scope Result

```text
EMPIRE     = 6
KINGDOM    = 15
CITY       = 0
SETTLEMENT = 5
TOTAL      = 26
```

Partition check:

```text
6 + 15 + 0 + 5 = 26
```

Semua 26 NPC memiliki tepat satu hasil audit. Tidak ditemukan NPC yang membutuhkan reclassification berdasarkan Canon record yang saat ini tersedia.

## 5. Hierarchical Context — Separate Metric

Context geografis tetap dihitung terpisah:

```text
EMPIRE_ID     = 26
KINGDOM_ID    = 20
CITY_ID       = 15
SETTLEMENT_ID = 5
```

`CITY_ID = 15` termasuk NPC-010 yang tercatat pada CITY-019. Ini adalah context, bukan City Primary coverage.

## 6. Decision

**PRIMARY_SCOPE model v1.1 dinyatakan VALID untuk 26 NPC saat ini.**

Tidak ada reclassification yang diperlukan sebelum Batch 2.

Namun, untuk mencegah runtime atau editor melakukan inferensi berbeda, `PRIMARY_SCOPE` sebaiknya menjadi field eksplisit pada record NPC Canon individual pada maintenance berikutnya. Audit ini tidak mengubah identity, role, atau geography Canon yang sudah ada.

## Final Principle

> **Primary Scope harus mengikuti pusat fungsi NPC. Hierarchical containment hanya menjelaskan konteks. NPC Canon dibuat untuk menyediakan aktor dunia yang bermakna bagi Player dan Qwen GM, bukan untuk mengejar angka coverage.**
