# ELDORIA WORLD — ALCHEMY

> **Module:** 22 — Alchemy
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan alchemy sebagai proses transmutasi, ekstraksi, pencampuran, pemurnian, atau pengolahan bahan menjadi hasil melalui method yang sah dan resolution.

Module ini menetapkan framework, bukan daftar potion, formula, efek, atau angka universal.

## 2. Alchemy Identity

Alchemy operation yang material dapat memiliki:

```text
ALCHEMY_ID
ACTOR_ID
FORMULA_ID / METHOD_ID
INPUTS
TOOLS / VESSEL
LOCATION
REQUIREMENTS
OUTPUTS
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Sources & Methods

Formula/method dapat berasal dari learned knowledge, recipe, discovery, experimentation, teaching, research, magical source, atau generation yang sah.

Tidak ada formula yang dianggap diketahui tanpa source.

## 4. Requirements

Alchemy dapat memerlukan bahan, skill, equipment, vessel, workstation, magic, knowledge, time, location, atau condition tertentu.

Semua requirement harus diverifikasi terhadap current state.

## 5. Resolution

```text
ALCHEMY INTENT
↓
LOAD FORMULA / METHOD
↓
CHECK INPUTS + REQUIREMENTS
↓
CHECK TOOLS + CONDITIONS
↓
RESOLVE RESULT / QUALITY / FAILURE
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

Player memilih eksperimen/tindakan, bukan hasil final.

## 6. Material Transformation

Input dapat dikonsumsi, diubah, tercemar, rusak, atau menghasilkan output sesuai resolution.

Output material harus menggunakan item/equipment state yang relevan.

## 7. Quality, Risk & Failure

Potency, purity, contamination, defects, explosion, waste, partial success, atau failure hanya boleh muncul bila didukung method/system dan kondisi resolution.

Tidak ada automatic perfect result.

## 8. Magic Integration

Alchemy dapat menggunakan atau menghasilkan magical effect jika `09_MAGIC_SYSTEM.md` mengizinkannya.

Magic tidak boleh muncul gratis hanya karena bahan memiliki nama fantastis.

## 9. Time & Environment

Operation yang memerlukan waktu harus menghasilkan time delta.

Temperature, contamination, tools, workstation, storage, environment, dan safety dapat menjadi faktor jika relevan.

## 10. Economy & Ownership

Alchemy dapat mengubah inventory, ownership, currency, market supply, contracts, atau faction resources.

Konsekuensi ekonomi mengikuti `11_ECONOMY.md`.

## 11. Dynamic Generation

Formula, reagent, intermediate, atau output dapat digenerate secara dinamis jika mechanism mengizinkan.

Generated material yang menjadi persistent wajib memiliki stable identity, origin, generation data, current state, dan history.

## 12. Information Boundary

Character hanya menggunakan formula dan knowledge yang tersedia baginya.

Player knowledge tidak otomatis menjadi alchemical knowledge Character.

## 13. Anti-Duplicate & Idempotency

Alchemy transaction dengan `TURN_ID` yang telah committed tidak boleh dijalankan ulang.

Persisted output tidak boleh diganti dengan hasil generator baru hanya karena runtime mengulang process.

## 14. Cross-System Integration

Alchemy dapat berinteraksi dengan crafting, equipment, magic, vitality, economy, quests, factions, pets/companions, dan world state.

Module terkait wajib dimuat jika konsekuensi menyentuh domain tersebut.

## 15. Canon Safety

Module ini tidak menetapkan fixed potion catalog, formula table, universal effects, success rates, potency scale, atau material values.

## 16. Dependencies

`06_ATTRIBUTES` + `08_SKILLS` + `09_MAGIC_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY`.

Integrasi: `12_VITALITY_SURVIVAL`, `21_CRAFTING`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `24_PETS_AND_COMPANIONS`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Alchemy adalah transformasi bahan dan knowledge yang di-resolve berdasarkan method, capability, resources, tools, dan kondisi; hasilnya tidak boleh dipaksakan oleh Player.**
