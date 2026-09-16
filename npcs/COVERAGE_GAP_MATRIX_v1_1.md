# ELDORIA WORLD — NPC COVERAGE GAP MATRIX v1.1

> **Authority:** Admin
> **Status:** Admin Audit v1.1
> **Audit Date:** 2026-09-16
> **Purpose:** Audit kebutuhan Canon NPC berdasarkan **Primary Base**, bukan sekadar hierarchical containment.

## Primary Base Rule

Setiap NPC memiliki tepat satu `PRIMARY_SCOPE`:

```text
EMPIRE | KINGDOM | CITY | SETTLEMENT
```

`PRIMARY_SCOPE` ditentukan oleh pusat fungsi, pekerjaan, kewenangan, dan aktivitas utama NPC.

`EMPIRE_ID`, `KINGDOM_ID`, `CITY_ID`, dan `SETTLEMENT_ID` tetap dicatat sebagai **hierarchical context**, tetapi tidak otomatis menjadi Primary Base.

> **NPC Canon adalah aktor dunia untuk membuat Eldoria hidup bagi Player ketika Qwen menjalankan dunia sebagai AI Game Master. Coverage bukan alasan membuat NPC filler.**

## Corrected Primary Coverage — 2026-09-16

| Scope | Units | Target | Actual Primary | Gap |
|---|---:|---:|---:|---:|
| Empire | 1 | ≥25 | **6** | **19** |
| Kingdom | 5 | ≥10 each | **15** | **35** |
| City | 20 | ≥5 each | **0** | **100** |
| Settlement | 40 | ≥3 each | **5** | **115** |
| **TOTAL** | **66** | **≥295** | **26** | **269** |

**Primary-base coverage = 26 / 295 = 8.81%.**

## Empire Primary

`EMPIRE-001 Kekaisaran Valthera` = **6 / 25**

- NPC-001 Alaric Veyn
- NPC-002 Seraphine Darr
- NPC-003 Corvin Hale
- NPC-004 Mirelle Ordan
- NPC-005 Garran Voss
- NPC-011 Aurelian Valthera

Jadi **Empire-level NPC yang benar-benar berbasis/fungsi utama di Empire saat ini = 6**, bukan 26.

## Kingdom Primary

- `KINGDOM-001 Valedorn` = 3/10: NPC-006, 012, 017
- `KINGDOM-002 Brannor` = 3/10: NPC-007, 013, 018
- `KINGDOM-003 Mariselle` = 3/10: NPC-008, 014, 019
- `KINGDOM-004 Sylvaran` = 3/10: NPC-009, 015, 020
- `KINGDOM-005 Sahrad` = 3/10: NPC-010, 016, 021

## City Primary

Saat ini **0/5 pada seluruh 20 City**.

NPC yang memiliki `CITY_ID` tetapi fungsi utamanya berada pada level Kingdom tidak dihitung sebagai City Primary.

## Settlement Primary

Batch 1 menghasilkan:

- SETTLEMENT-003 Rivergate = 1/3 — NPC-022
- SETTLEMENT-011 Valecrest = 1/3 — NPC-023
- SETTLEMENT-019 Saltmere = 1/3 — NPC-024
- SETTLEMENT-027 Oakmere = 1/3 — NPC-025
- SETTLEMENT-035 Grassrest = 1/3 — NPC-026

35 settlement lain = 0/3.

Total = **5/120**.

## Hierarchical Context Audit

Konteks geografis aktual yang tercatat saat ini:

| Context | Actual |
|---|---:|
| EMPIRE_ID | 26 |
| KINGDOM_ID | 20 |
| CITY_ID | **15** |
| SETTLEMENT_ID | 5 |

### Bug ditemukan

`NPC-010 Rashid Qamar` memiliki `CITY_ID: CITY-019`, tetapi Matrix lama mencatat `CITY-019 Caravanser = 0`.

Hierarchical City context yang benar = **15**, bukan 14.

## Mengapa 26/25 Empire Salah untuk NPC Coverage

Matrix lama menghitung:

```text
EMPIRE_ID → Empire coverage
```

Akibatnya semua NPC di bawah Kekaisaran otomatis dianggap sebagai NPC Empire.

Padahal:

```text
Empire Primary NPC = 6
NPC dengan EMPIRE_ID = 26
```

Kedua angka ini mempunyai arti berbeda.

Mulai audit v1.1:

```text
PRIMARY_SCOPE: EMPIRE → Empire Base Coverage
EMPIRE_ID: EMPIRE-001 → Empire Context
```

## Faction / Noble House

Faction dan Noble House adalah konteks tambahan tanpa target numerik dalam denominator 295.

Current:

```text
Primary faction assignments: 26
Secondary faction contexts: 5
```

Faction tidak otomatis menentukan Primary Base.

## Batch 1 Reclassification

- NPC-022 Maren Vale → `PRIMARY_SCOPE: SETTLEMENT`
- NPC-023 Borin Keld → `PRIMARY_SCOPE: SETTLEMENT`
- NPC-024 Selene Varo → `PRIMARY_SCOPE: SETTLEMENT`
- NPC-025 Elira Fen → `PRIMARY_SCOPE: SETTLEMENT`
- NPC-026 Rafiq Sahr → `PRIMARY_SCOPE: SETTLEMENT`

Batch 1 tetap valid. Kelima NPC memang dirancang untuk menghidupkan Settlement.

## Development Consequence

Kebutuhan Primary Base saat ini:

```text
Empire    6 / 25   → gap 19
Kingdom  15 / 50   → gap 35
City      0 / 100  → gap 100
Settlement 5 / 120 → gap 115
```

Ini bukan perintah membuat 269 NPC sekaligus.

Setiap batch maksimal 5 NPC dan harus memiliki fungsi dunia yang nyata.

## Batch Selection Rule

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

## Final Principle

> **Basis utama NPC menentukan coverage utama. Hierarchical containment hanya menentukan konteks geografis.**
>
> **Tujuan NPC Canon adalah membuat dunia hidup dan memiliki aktor yang dapat dijalankan Qwen sebagai GM untuk Player, bukan mengejar angka coverage.**
