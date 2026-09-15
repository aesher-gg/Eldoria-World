# ELDORIA WORLD — CITIES & SETTLEMENTS

> **Module:** 03 — Cities and Settlements
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1

## 1. Purpose

Mendefinisikan model settlement Eldoria serta hubungan settlement dengan hierarki Kekaisaran → Kerajaan → Kota → Desa, region, faction, NPC, ekonomi, quest, event, dan World State.

## 2. Settlement Hierarchy

Settlement mengikuti struktur administratif utama:

```text
KEKAISARAN
└── KERAJAAN
    └── KOTA
        └── DESA / SETTLEMENT TERKAIT
```

`Kekaisaran` dan `Kerajaan` adalah level politik yang ditangani terutama oleh `02_REALMS_AND_REGIONS` dan faction/governance modules. Module ini berfokus pada Kota, Desa, dan settlement.

## 3. Settlement Types

Settlement dapat menggunakan tipe seperti:

- village,
- town,
- city,
- fortified settlement,
- outpost,
- hamlet,
- camp,
- atau tipe lain yang sah.

Tipe spesifik tidak boleh dianggap fakta tanpa data.

Untuk hierarchy Canon:

- **Kota** adalah settlement tingkat kota di bawah Kerajaan.
- **Desa** adalah settlement tingkat desa yang secara normal berada di bawah Kota.
- Settlement lain dapat memiliki parent administratif berbeda bila Canon menentukannya secara eksplisit.

## 4. Persistent Identity

Settlement persisten wajib memiliki:

```text
SETTLEMENT_ID
NAME
TYPE
PARENT_ID
KINGDOM_ID
REGION_ID
CURRENT_STATE
ORIGIN
HISTORY
```

`PARENT_ID` harus menunjuk ke parent yang benar-benar tersedia dalam Canon/State.

Untuk Kota, `KINGDOM_ID` wajib diketahui bila kota merupakan bagian dari hierarchy utama. Untuk Desa, `PARENT_ID` normalnya menunjuk ke `CITY_ID`.

Field yang belum diketahui = `???`.

## 5. Settlement State

Current State dapat mencakup bila relevan:

```text
POPULATION
SECURITY
GOVERNANCE
ECONOMY
SERVICES
INFRASTRUCTURE
FACTION_INFLUENCE
ACTIVE_EVENTS
```

Field yang belum diketahui tetap `???`.

## 6. Population Model

Settlement dapat memiliki populasi sangat besar tanpa setiap individu memiliki record repository.

Population Model menangani distribusi agregat seperti:

- total population,
- density,
- occupation distribution,
- demographic structure,
- service demand,
- security pressure,
- dan karakteristik lokal lain yang diperlukan.

Angka atau distribusi yang belum ditentukan tetap `???`.

Population Model menjadi input Dynamic NPC Generation, bukan pengganti Canon NPC Registry.

## 7. Canon NPC Prerequisite

Canon NPC dibuat secara sistematis berdasarkan settlement yang sudah memiliki identity.

Minimum coverage:

```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC
KEKAISARAN → ≥ 25 Canon NPC
```

Ketentuan:

1. Parent geography/settlement harus sudah memiliki identity Canon yang jelas.
2. Canon NPC harus memiliki `NPC_ID` unik.
3. Canon NPC harus memiliki role yang bermakna terhadap wilayahnya.
4. Tidak semua penduduk harus menjadi Canon NPC.
5. Canon NPC tidak dibuat acak untuk mengisi angka; setiap tokoh harus mempunyai fungsi, latar, goals, relationships, capabilities, dan alasan keberadaan yang konsisten dengan parent wilayah.
6. Jika wilayah belum benar-benar ditetapkan, jangan membuat NPC yang seolah-olah tinggal di wilayah tersebut.

## 8. Canon NPC Distribution Principle

Minimum coverage bukan berarti semua NPC harus memiliki peran yang sama.

Distribusi harus mewakili kebutuhan dunia, misalnya bila relevan:

- pemerintahan,
- keamanan,
- perdagangan,
- layanan masyarakat,
- agama/budaya,
- guild/faction,
- profesi penting,
- informasi lokal,
- atau kepentingan konflik.

Peran aktual ditentukan Admin berdasarkan Canon wilayah dan tidak boleh dianggap otomatis tersedia hanya karena kategori tersebut disebutkan.

## 9. Services

Settlement dapat menyediakan service seperti:

- inn,
- market,
- blacksmith,
- healer,
- stable,
- guild/faction office,
- temple,
- guard post,
- workshop,
- atau service lain.

Ketersediaan aktual harus berasal dari settlement data/state atau generation yang sah.

## 10. Economy Context

Settlement dapat menjadi lokasi transaksi, tetapi harga dan ketersediaan ditentukan oleh `11_ECONOMY.md`, local state, supply/demand, event, faction, dan kondisi dunia yang relevan.

Settlement description tidak boleh menjadi alasan otomatis untuk memberikan item atau uang.

## 11. Security

Security dapat memengaruhi:

- crime risk,
- travel,
- combat consequences,
- faction enforcement,
- access,
- quest availability.

Nilai dan efek spesifik ditentukan oleh state/module terkait.

## 12. NPC Integration

NPC yang menetap di settlement tetap memiliki NPC State sendiri. Settlement tidak menggantikan identity atau agency NPC.

NPC knowledge tetap mengikuti Information State.

Canon NPC harus terdaftar pada `npcs/CANON_REGISTRY.md` dan memiliki record Canon yang dapat dirujuk. Dynamic NPC tidak otomatis menjadi Canon.

## 13. Quest & Event Integration

Settlement dapat menjadi source, target, atau affected location bagi quest/event.

Quest/event yang menjadi persisten harus memiliki state, identity, history, dan origin sesuai module masing-masing.

## 14. Dynamic Settlement

Settlement baru dapat dihasilkan bila mekanisme generation mengizinkannya.

Jika menjadi material bagi gameplay, settlement harus dipersistenkan dan tidak boleh diganti dengan settlement baru pada turn berikutnya.

Dynamic settlement tidak otomatis menjadi World Canon.

## 15. Destruction & Change

Settlement dapat berubah, rusak, ditinggalkan, berkembang, atau berada di bawah kekuasaan baru jika resolution menghasilkan perubahan yang valid.

Perubahan material mengikuti:

```text
CAUSE
→ ORIGIN
→ STATE DELTA
→ VALIDATION
→ ATOMIC PERSISTENCE
→ HISTORY
```

## 16. Knowledge Boundary

Player atau Character tidak otomatis mengetahui seluruh settlement state. Informasi seperti harga, jumlah penjaga, konflik internal, atau rahasia harus mengikuti information state dan discovery.

## 17. Dependencies

`02_REALMS_AND_REGIONS` → module ini.

Integrasi utama: `04_FACTIONS`, `11_ECONOMY`, `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `20_REPUTATION`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `32_MODULE_ROUTER`.

## 18. Canon Safety

Module ini menyediakan schema dan aturan hubungan settlement, bukan katalog seluruh kota/desa. Nama, jumlah, dan detail settlement yang belum ditetapkan tidak boleh diperlakukan sebagai Canon.

## 19. Final Principle

> **Kita membangun wilayah terlebih dahulu, lalu membangun tokoh Canon yang hidup di dalam wilayah tersebut; populasi massal tetap ditangani Population Model dan Dynamic NPC.**
