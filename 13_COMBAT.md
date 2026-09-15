# ELDORIA WORLD — COMBAT

> **Module:** 13 — Combat
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan combat sebagai stateful resolution antara actor yang memiliki capability, condition, intent, dan agency.

Module ini menetapkan framework, bukan outcome tetap atau angka balance universal.

## 2. Combatants

Combatant dapat berupa:

- Character,
- NPC,
- Monster,
- Pet/Companion,
- atau entity lain yang valid.

Setiap combatant menggunakan current state authoritative miliknya.

## 3. Combat State

Encounter dapat memiliki:

```text
COMBAT_ID
PARTICIPANTS
LOCATION
CURRENT_PHASE / TURN
INITIATIVE MODEL
ENVIRONMENT
OBJECTIVES
CONDITIONS
ACTIVE EFFECTS
STATE_VERSION
HISTORY
ORIGIN
```

Field yang belum diketahui = `???`.

## 4. Combat Flow

```text
DECLARE INTENT
↓
CHECK ACTION / CAPABILITY
↓
LOAD RELEVANT STATE
↓
ACCOUNT FOR ENVIRONMENT / CONDITIONS
↓
RESOLVE ACTION
↓
GENERATE STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
NARRATE RESULT
```

## 5. Player Agency

Player memilih tindakan karakter.

Player tidak menentukan:

- apakah serangan pasti mengenai,
- damage final,
- critical outcome,
- enemy reaction,
- escape success,
- atau outcome lain.

## 6. Combat Factors

Resolution dapat mempertimbangkan:

- attributes,
- skills,
- class,
- magic,
- equipment,
- vitality,
- condition,
- positioning,
- terrain,
- visibility,
- initiative,
- tactics,
- information,
- fatigue,
- dan faktor lain yang relevan.

Formula spesifik hanya berlaku bila ditetapkan oleh system.

## 7. NPC & Monster Agency

NPC dan Monster bertindak berdasarkan state, capability, knowledge, objectives, condition, dan behavior rules.

Mereka tidak menjadi target pasif hanya demi keberhasilan Player.

## 8. Damage & Effects

Damage, status effect, displacement, equipment damage, resource consumption, injury, death, atau perubahan lain harus menjadi State Delta dengan Cause + Origin.

## 9. Environment

Combat dapat mengubah atau dipengaruhi world/terrain/environment bila resolution mengizinkan.

Perubahan material pada world harus dipersistenkan sesuai world-state rules.

## 10. Death & Escape

Death mengikuti `12_VITALITY_SURVIVAL.md`.

Escape, surrender, capture, retreat, atau incapacitation adalah outcome resolution, bukan hak otomatis Player.

## 11. Multiple Actors

Multi-actor combat harus mempertahankan identity masing-masing dan tidak menggabungkan state tanpa dasar.

Order dan concurrency harus konsisten dengan turn transaction/state version.

## 12. Anti-Contradiction

Combat resolution tidak boleh:

- mengabaikan current HP/condition,
- menghidupkan entity tanpa mechanism,
- memberi item/skill gratis,
- menimpa state terbaru,
- atau menyatakan outcome sebelum persistence berhasil.

## 13. Validation

Validator memeriksa participant validity, action legality, target, resources, condition, state version, State Delta, Cause, Origin, dan `TURN_ID`.

## 14. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` + `09_MAGIC_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `12_VITALITY_SURVIVAL` → module ini.

Integrasi: `14_MONSTER_ECOSYSTEM`, `15_LOOT_GENERATION`, `16_NPC_SYSTEM`, `18_WORLD_EVENTS`, `24_PETS_AND_COMPANIONS`, `28_MONSTER_STATE`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 15. Canon Safety

Module ini tidak menetapkan damage table, hit chance, initiative formula, weapon stats, atau combat outcome universal tanpa source yang sah.

## 16. Final Principle

> **Combat adalah simulasi multi-aktor berbasis state; Player memilih aksi, semua pihak memiliki agency, dan sistem menentukan outcome.**
