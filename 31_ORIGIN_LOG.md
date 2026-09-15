# ELDORIA WORLD — ORIGIN LOG

> **Module:** 31 — Origin Log
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Origin Log mencatat sumber, sebab, mekanisme, dan provenance dari state change, generated entity, information, atau record material.

Origin menjawab: **dari mana fakta atau perubahan ini berasal?**

## 2. Origin Record

Origin material dapat memiliki:

```text
ORIGIN_ID
TIMESTAMP
TRANSACTION_ID / TURN_ID
SOURCE_TYPE
SOURCE_ID
CAUSE
ACTOR_ID
TARGET_ENTITY_ID(S)
METHOD / MECHANISM
INPUT REFERENCES
GENERATION DATA / SEED WHEN RELEVANT
PARENT ORIGIN_ID WHEN APPLICABLE
CONTEXT
```

Field yang belum diketahui = `???`.

## 3. Valid Sources

Source dapat berupa:

- Player Action,
- Character Action,
- NPC Action,
- Monster Action,
- Combat Resolution,
- Quest Resolution,
- World Event,
- System Generation,
- Crafting,
- Alchemy,
- Economy Transaction,
- Magic Resolution,
- Environment,
- Admin Canon,
- atau mechanism sah lain.

## 4. Cause vs Origin

`CAUSE` menjelaskan **mengapa** perubahan terjadi.
`ORIGIN` menjelaskan **dari mana dan melalui mekanisme apa** perubahan tersebut berasal.

Keduanya tidak boleh dipertukarkan bila module memerlukan keduanya.

## 5. State Change Provenance

Material State Change harus dapat ditelusuri:

```text
STATE DELTA
↓
TRANSACTION / TURN
↓
CAUSE
↓
ORIGIN
↓
SOURCE / MECHANISM
```

## 6. Generation Provenance

Dynamic generation yang menghasilkan entity material harus menyimpan informasi yang cukup untuk menjaga continuity, termasuk seed/parameter atau equivalent mechanism bila diperlukan.

Generator tidak boleh menjadi alasan untuk menghapus provenance.

## 7. Information Provenance

Informasi yang diketahui Character/NPC/Player dapat memiliki origin seperti observation, communication, document, rumor, investigation, transaction, event, atau valid source lain.

Informasi yang tidak memiliki source yang sah tidak boleh diperlakukan sebagai knowledge.

## 8. Parent / Chain Origin

Event, quest, state change, atau generated entity dapat berasal dari kejadian sebelumnya.

Origin dapat menunjuk `PARENT_ORIGIN_ID` untuk menjaga causal chain.

## 9. Correction

Jika provenance perlu dikoreksi, buat Origin/Correction record baru.

Origin lama tidak boleh dihapus diam-diam setelah committed.

## 10. Atomicity

Origin yang menyertai material State Change dan History harus dipersistenkan sebagai bagian dari atomic transaction.

Tidak boleh ada Origin yang menyatakan transaction berhasil jika transaction tersebut gagal.

## 11. Idempotency

Origin generation harus terikat pada transaction/event identity.

Retry tidak boleh membuat Origin duplicate untuk transaction yang sama.

## 12. Information Boundary

Origin internal tidak otomatis terlihat oleh Player atau Character.

Visible provenance mengikuti information rules dan knowledge state.

## 13. Validation

Origin Record harus dapat menjawab setidaknya:

- sumbernya apa,
- transaction apa,
- cause apa,
- entity apa yang terdampak,
- mechanism apa yang menghasilkan perubahan,
- dan apakah transaction benar-benar committed.

## 14. Dependencies

`00_CORE_RULES` + `30_HISTORY_SYSTEM` + seluruh module yang menghasilkan material state/entity/information.

Integrasi utama: `25_WORLD_STATE`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `28_MONSTER_STATE`, `29_EVENT_STATE`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 15. Canon Safety

Origin tidak boleh dibuat untuk membenarkan perubahan yang tidak pernah terjadi.

`???` digunakan jika source belum diketahui atau belum resolved.

## 16. Final Principle

> **Origin Log menjaga provenance Eldoria: setiap fakta material harus memiliki jalur yang dapat ditelusuri menuju sumber, cause, mechanism, dan transaction yang sah.**
