# ELDORIA WORLD — CANON NPC MASTER PLAN

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Purpose:** Menetapkan arsitektur, prioritas, dan coverage plan Canon NPC sebelum pembuatan record NPC individual.

## 1. Scope

Dokumen ini adalah master planning layer untuk Canon NPC. Dokumen ini **tidak membuat NPC individual**.

Canon NPC adalah tokoh penting resmi yang ditetapkan Admin. Population Model tetap menangani populasi umum; Dynamic NPC tetap dapat dibuat AI GM sesuai `16_NPC_SYSTEM.md`.

## 2. Authority Chain

```text
CANON GEOGRAPHY
↓
POPULATION MODEL
↓
GOVERNANCE / FACTION CONTEXT
↓
FACTION CANON REGISTRY
↓
NPC COVERAGE PLAN
↓
INDIVIDUAL CANON NPC
```

NPC tidak boleh digunakan untuk mengisi kekosongan geography, governance, atau faction.

## 3. Coverage Requirements

Minimum coverage yang harus dipenuhi:

| Scope | Minimum Canon NPC |
|---|---:|
| Empire | ≥25 |
| Setiap Kingdom | ≥10 |
| Setiap City | ≥5 |
| Setiap Settlement | ≥3 |

Coverage adalah **scope relevance**, bukan kewajiban membuat jumlah NPC unik yang sama dengan total coverage.

Satu NPC dapat memenuhi beberapa scope bila secara lore benar-benar relevan. NPC filler dilarang.

## 4. Coverage Hierarchy

### Empire

Canon NPC Empire harus memiliki alasan material untuk beroperasi pada tingkat kekaisaran, misalnya pemerintahan, pertahanan, perdagangan antar-kerajaan, atau fungsi strategis lain yang benar-benar didukung Canon.

### Kingdom

Setiap Kingdom membutuhkan sekurang-kurangnya 10 tokoh Canon yang relevan terhadap governance, security, economy, strategic institutions, atau kepentingan kingdom lainnya.

### City

Setiap City membutuhkan sekurang-kurangnya 5 tokoh Canon yang benar-benar memiliki peran material pada administrasi, ekonomi, keamanan, budaya, infrastruktur, atau institusi lokal.

### Settlement

Setiap Settlement membutuhkan sekurang-kurangnya 3 tokoh Canon yang benar-benar penting bagi komunitas tersebut. Keberadaan mereka tidak boleh ditentukan hanya karena settlement memiliki quota.

## 5. Faction Mapping Principle

NPC dapat dikaitkan dengan faction Canon yang telah tersedia di `factions/CANON_REGISTRY.md`.

Faction context tidak otomatis memberikan kepada NPC:

- rank,
- membership,
- authority,
- access,
- reputation,
- resources,
- knowledge,
- atau loyalty.

Semua atribut individual tersebut harus ditetapkan pada NPC record dan mengikuti resolution/state rules.

Jika tidak ada faction Canon yang relevan, field faction tetap `???` atau menggunakan Dynamic Faction yang sah; jangan membuat faction Canon hanya untuk memenuhi kebutuhan NPC.

## 6. Canon NPC Identity Schema

Setiap NPC individual yang nanti dibuat wajib mengikuti architecture:

```text
NPC_ID
NPC_CLASS: CANON
NAME
RACE_CANON_ID
ROLE / TYPE
SETTLEMENT_ID
CITY_ID
REGION_ID
KINGDOM_ID
EMPIRE_ID
BACKGROUND
ORIGIN
GOALS
CORE_RELATIONSHIPS
CAPABILITIES
KNOWLEDGE_BOUNDARY
FACTION
CANON_ORIGIN
CANON_STATUS
```

`???` digunakan untuk field yang memang belum ditetapkan.

## 7. NPC Design Rules

1. Tidak ada NPC yang dibuat hanya untuk memenuhi angka coverage.
2. NPC harus memiliki fungsi atau kepentingan material dalam dunia.
3. NPC harus memiliki agency sendiri.
4. Race wajib menggunakan `RACE_CANON_ID` yang aktif dari Race Registry.
5. Race tidak boleh menentukan morality, personality, class, faction, atau outcome secara otomatis.
6. Canon NPC tidak boleh dibuat sebagai duplicate dari Dynamic/Persistent NPC yang sudah ada.
7. Dynamic NPC tidak otomatis dipromosikan menjadi Canon NPC.
8. Identity/lore Canon tidak boleh berubah hanya karena narrative runtime.
9. Current state berada pada state layer terpisah dan perubahan material mengikuti History + Origin.
10. Knowledge boundary harus eksplisit dan tidak boleh menjadi omniscient.

## 8. Recommended Role Distribution

Coverage sebaiknya tersebar secara alami di antara:

- governance / administration,
- military / security,
- trade / economy,
- craft / production,
- agriculture / food systems,
- transport / logistics,
- maritime roles bila relevan,
- forestry / frontier roles bila relevan,
- pastoral / caravan roles bila relevan,
- religious / cultural roles bila Canon tersedia,
- specialist / professional roles,
- community roles.

Daftar ini adalah planning guidance, bukan kewajiban setiap wilayah memiliki semua role.

## 9. Generation Order

Pembuatan individual Canon NPC dilakukan setelah Coverage Matrix tervalidasi.

Urutan aman:

```text
EMPIRE CONTEXT
↓
KINGDOM CONTEXT
↓
CITY CONTEXT
↓
SETTLEMENT CONTEXT
↓
FACTION ASSIGNMENT
↓
NPC IDENTITY
↓
RELATIONSHIP / GOALS / CAPABILITIES
↓
CANON VALIDATION
↓
PERSISTENT RECORD
```

## 10. Persistence Boundary

Dokumen ini tidak mengharuskan setiap NPC langsung memiliki Current State file terpisah.

Canon Identity/Lore dan Current State tetap dipisahkan sesuai `16_NPC_SYSTEM.md` dan `27_NPC_STATE.md`.

Jika NPC belum memiliki persistent state material, state yang belum diketahui tetap `???`.

## 11. Validation Gates

Sebelum NPC individual dibuat, Admin wajib memastikan:

```text
[ ] Geography authoritative
[ ] Population context available
[ ] Governance context available
[ ] Relevant faction context available
[ ] Race Canon available
[ ] Coverage need justified by lore
[ ] Role is not quota filler
[ ] No duplicate Canon NPC
[ ] Knowledge boundary defined
[ ] Origin is traceable
```

## 12. Current Planning Status

```text
EMPIRE COVERAGE TARGET: ≥25
KINGDOM COVERAGE TARGET: ≥10 each × 5
CITY COVERAGE TARGET: ≥5 each × 20
SETTLEMENT COVERAGE TARGET: ≥3 each × 40

INDIVIDUAL CANON NPC CREATED BY THIS PLAN: 0

NEXT ARTIFACT: npcs/COVERAGE_MATRIX.md
```

## 13. Final Principle

> **Canon NPC dibuat karena mereka penting bagi dunia; Coverage Matrix mengatur pemerataan, bukan menciptakan alasan palsu untuk keberadaan NPC.**
