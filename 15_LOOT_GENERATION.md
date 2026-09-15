# ELDORIA WORLD — LOOT GENERATION

> **Module:** 15 — Loot Generation
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan dynamic loot generation yang logis terhadap source, context, ownership, rarity, condition, dan resolution.

Module ini menetapkan framework generation, bukan fixed drop table atau hadiah universal.

## 2. Loot Identity

Loot yang menjadi material bagi gameplay wajib memiliki:

```text
ITEM_ID
NAME
TYPE
QUALITY / TIER
SOURCE
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
```

`ITEM_ID` harus stabil setelah item menjadi persistent.

## 3. Valid Sources

Loot dapat berasal dari mekanisme yang sah seperti:

- monster remains,
- NPC possession,
- container,
- settlement/faction resource,
- quest resolution,
- world event,
- crafting/material recovery,
- discovery,
- atau source lain yang diizinkan module.

Player tidak memperoleh loot hanya karena meminta hadiah.

## 4. Source-Logical Generation

Generation mempertimbangkan context yang relevan, misalnya:

```text
SOURCE_ID
SOURCE_TYPE
LOCATION
ENVIRONMENT
SOURCE_STATE
EVENT / COMBAT RESULT
DISCOVERY CONTEXT
GENERATION SEED / PARAMETERS
```

Loot harus memiliki hubungan logis dengan source.

Tidak ada kewajiban setiap source menghasilkan loot.

## 5. Generation Determinism

Jika generation menghasilkan item material, seed/parameter atau mekanisme deterministik ekuivalen harus dipertahankan bila diperlukan untuk mencegah hasil berubah secara tidak sah ketika runtime diulang.

Generator wajib memeriksa item atau generation record yang sudah persisted sebelum menghasilkan replacement baru.

## 6. Persistence Threshold

Loot yang hanya bersifat abstrak atau belum material tidak harus menjadi individual persistent item.

Jika item diberikan, diambil, dipindahkan, diperdagangkan, dilengkapi, dikonsumsi, atau menjadi penting bagi gameplay, item harus memiliki identity/state yang dapat ditelusuri.

## 7. Ownership & Possession

Loot generation tidak otomatis menentukan hak kepemilikan.

Bedakan:

```text
OWNER
POSSESSOR
LOCATION
LOOT RIGHTS / ACCESS
```

Hak mengambil loot mengikuti source, resolution, contract, faction rules, law, atau mekanisme lain yang sah.

## 8. Condition & Quantity

Item generated dapat memiliki condition, durability, quantity, charges, atau atribut lain bila relevan.

Nilai tidak boleh menggunakan default universal tanpa source atau formula yang sah.

## 9. Anti-Duplicate Rule

Loot dari satu resolution yang telah committed tidak boleh digenerate ulang sebagai loot baru hanya karena turn atau generator dipanggil kembali.

`TURN_ID`, source identity, generation data, dan history dapat digunakan untuk menjaga idempotency dan continuity.

## 10. Economy Integration

Loot yang masuk ke market dapat memengaruhi supply, demand, scarcity, dan value sesuai `11_ECONOMY.md`.

Value bukan otomatis sama dengan selling price.

## 11. Equipment Integration

Item equipment mengikuti `10_EQUIPMENT_SYSTEM.md` untuk identity, condition, ownership, effects, requirements, dan persistence.

Generated effect tidak boleh melampaui capability yang sah.

## 12. Quest/Event Integration

Quest reward atau event reward hanya menjadi state change setelah resolution yang valid menghasilkan reward tersebut.

Reward tidak boleh dianggap guaranteed sebelum outcome resolved and committed.

## 13. Information Boundary

Player/Character tidak otomatis mengetahui isi container, drop source, rarity, hidden property, atau ownership tanpa mekanisme yang memberikan informasi tersebut.

## 14. Resolution Flow

```text
SOURCE / EVENT
↓
CHECK LOOT ELIGIBILITY
↓
GENERATE USING VALID CONTEXT
↓
ASSIGN IDENTITY / ORIGIN
↓
GENERATE STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY
↓
NARRATE DISCOVERY
```

## 15. Canon Safety

Module ini tidak menetapkan fixed:

- drop table,
- rarity percentages,
- item prices,
- reward quantities,
- quality values,
- atau guaranteed rewards.

Semua data spesifik harus berasal dari source, state, generation mechanism, atau resolution yang sah.

## 16. Dependencies

`10_EQUIPMENT_SYSTEM` + `11_ECONOMY` + `13_COMBAT` + `14_MONSTER_ECOSYSTEM`.

Integrasi: `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `21_CRAFTING`, `22_ALCHEMY`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Loot adalah konsekuensi logis dari source dan resolution, bukan hadiah yang muncul untuk memuaskan Player.**
