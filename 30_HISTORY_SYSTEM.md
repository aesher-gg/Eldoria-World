# ELDORIA WORLD — HISTORY SYSTEM

> **Module:** 30 — History System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

History adalah append-only record mengenai kejadian dan perubahan yang telah berhasil terjadi dalam Eldoria.

History bukan current state dan tidak boleh digunakan untuk menggantikan authoritative current state.

## 2. History Record

Record material dapat memiliki:

```text
HISTORY_ID
TIMESTAMP
SEQUENCE
TURN_ID / TRANSACTION_ID
ENTITY_ID(S)
EVENT / ACTION TYPE
CAUSE
STATE CHANGE / DELTA
ORIGIN_ID
ACTOR_ID
TARGET_ID
LOCATION
CONTEXT
CORRECTION_REFERENCE
```

Field yang belum diketahui = `???`.

## 3. Append-Only

History secara konseptual append-only.

Record yang sudah committed tidak boleh dihapus atau diubah diam-diam untuk menghilangkan contradiction.

Koreksi dibuat sebagai record baru yang menunjuk pada record yang dikoreksi.

## 4. Valid History

History hanya boleh dibuat untuk resolution yang berhasil divalidasi dan committed.

Failed/rejected transaction tidak boleh meninggalkan History yang menyatakan perubahan tersebut terjadi.

## 5. State Relationship

History menjelaskan transisi:

```text
BEFORE STATE
→ CAUSE / ACTION / EVENT
→ RESOLUTION
→ STATE DELTA
→ AFTER STATE
```

Current State tetap menjadi authority untuk kondisi sekarang.

## 6. Origin Link

Setiap material History Record harus memiliki Origin yang dapat menjelaskan sumber kejadian.

History tanpa Origin yang diwajibkan module adalah incomplete.

## 7. Ordering

History record yang saling berinteraksi harus memiliki ordering yang dapat ditentukan melalui timestamp, sequence, transaction identity, atau mekanisme ekuivalen.

## 8. Multi-Entity Events

Satu transaction dapat menghasilkan history untuk beberapa entity.

Semua record harus menunjuk pada transaction/event origin yang sama sehingga hubungan antar perubahan dapat ditelusuri.

## 9. Information Boundary

History internal tidak otomatis menjadi Character/NPC/Player Knowledge.

Apa yang diketahui entity tetap mengikuti information mechanism.

## 10. Idempotency

History generation harus terikat pada transaction identity.

`TURN_ID` yang telah committed tidak boleh membuat duplicate history.

## 11. Correction

Koreksi harus memuat:

```text
CORRECTION_ID
TARGET_HISTORY_ID
CAUSE
ORIGIN
CORRECTED_INTERPRETATION / STATE EFFECT
TIMESTAMP
```

Koreksi tidak menghapus fakta bahwa record sebelumnya pernah committed; koreksi menjelaskan status yang diperbaiki.

## 12. Persistence

History yang menyertai material State Change harus dipersistenkan dalam atomic transaction bersama State dan Origin.

## 13. Retention & Scope

History dapat berada pada world, character, NPC, monster, event, quest, faction, item, party, atau entity lain sesuai kebutuhan persistence.

Module terkait menentukan detail domain history.

## 14. Dependencies

`00_CORE_RULES` + seluruh state module yang menghasilkan material change.

Integrasi utama: `25_WORLD_STATE`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `28_MONSTER_STATE`, `29_EVENT_STATE`, `31_ORIGIN_LOG`, `35_SAVE_PIPELINE`.

## 15. Canon Safety

History tidak boleh menjadi sarana untuk menciptakan fakta yang tidak pernah resolved/committed.

Narrative bukan History Record.

## 16. Final Principle

> **History adalah memori append-only dunia yang hanya mencatat perubahan yang benar-benar committed dan dapat ditelusuri ke origin.**
