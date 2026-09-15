# ELDORIA WORLD — CITIES & SETTLEMENTS

> **Module:** 03 — Cities and Settlements
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan model settlement Eldoria serta hubungan settlement dengan region, faction, NPC, ekonomi, quest, event, dan World State.

## 2. Settlement Types

Settlement dapat menggunakan tipe seperti:

- hamlet,
- village,
- town,
- city,
- fortified settlement,
- outpost,
- camp,
- atau tipe lain yang sah.

Tipe spesifik tidak boleh dianggap fakta tanpa data.

## 3. Persistent Identity

Settlement persisten wajib memiliki:

```text
SETTLEMENT_ID
NAME
TYPE
REGION_ID
CURRENT_STATE
ORIGIN
HISTORY
```

## 4. Settlement State

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

## 5. Services

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

## 6. Economy Context

Settlement dapat menjadi lokasi transaksi, tetapi harga dan ketersediaan ditentukan oleh `11_ECONOMY.md`, local state, supply/demand, event, faction, dan kondisi dunia yang relevan.

Settlement description tidak boleh menjadi alasan otomatis untuk memberikan item atau uang.

## 7. Security

Security dapat memengaruhi:

- crime risk,
- travel,
- combat consequences,
- faction enforcement,
- access,
- quest availability.

Nilai dan efek spesifik ditentukan oleh state/module terkait.

## 8. NPC Integration

NPC yang menetap di settlement tetap memiliki NPC State sendiri. Settlement tidak menggantikan identity atau agency NPC.

NPC knowledge tetap mengikuti Information State.

## 9. Quest & Event Integration

Settlement dapat menjadi source, target, atau affected location bagi quest/event.

Quest/event yang menjadi persisten harus memiliki state, identity, history, dan origin sesuai module masing-masing.

## 10. Dynamic Settlement

Settlement baru dapat dihasilkan bila mekanisme generation mengizinkannya.

Jika menjadi material bagi gameplay, settlement harus dipersistenkan dan tidak boleh diganti dengan settlement baru pada turn berikutnya.

## 11. Destruction & Change

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

## 12. Knowledge Boundary

Player atau Character tidak otomatis mengetahui seluruh settlement state. Informasi seperti harga, jumlah penjaga, konflik internal, atau rahasia harus mengikuti information state dan discovery.

## 13. Dependencies

`02_REALMS_AND_REGIONS` → module ini.

Integrasi utama: `04_FACTIONS`, `11_ECONOMY`, `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `20_REPUTATION`, `25_WORLD_STATE`, `26_CHARACTER_STATE`.

## 14. Canon Safety

Module ini menyediakan schema dan aturan hubungan settlement, bukan katalog kota tetap. Nama dan detail settlement yang belum ditetapkan tidak boleh diperlakukan sebagai Canon.

## 15. Final Principle

> **Settlement adalah entitas dunia yang memiliki state dan konsekuensi, bukan sekadar latar narasi.**
