# ELDORIA WORLD — MONSTER ECOSYSTEM

> **Module:** 14 — Monster Ecosystem
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan monster sebagai bagian dari ekosistem hidup yang dapat muncul, bergerak, berkembang, berinteraksi, dan berubah berdasarkan habitat, kebutuhan, kondisi, serta world state.

Module ini menetapkan framework generation dan ecology, bukan katalog monster tetap atau angka balance universal.

## 2. Monster Identity

Monster yang menjadi material bagi gameplay wajib memiliki:

```text
MONSTER_ID
NAME / DESIGNATION
SPECIES / TYPE
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
```

Field yang belum diketahui = `???`.

## 3. Ecological State

State monster dapat mencakup, bila relevan:

```text
LOCATION
HABITAT
POPULATION_CONTEXT
LIFE_STAGE
HEALTH / VITALITY
CONDITION
NEEDS
RESOURCES
TERRITORY
BEHAVIOR_STATE
THREAT_CONTEXT
RELATIONSHIPS
REPRODUCTION / LIFECYCLE STATE
```

Nilai aktual berasal dari state atau generation/resolution yang sah.

## 4. Habitat & Ecology

Monster dipengaruhi oleh:

- terrain,
- climate,
- food/resource availability,
- water,
- shelter,
- season,
- population pressure,
- predators/prey,
- competition,
- settlements,
- factions,
- events,
- dan perubahan lingkungan.

Kecocokan habitat memengaruhi kemungkinan generation dan perilaku, tetapi tidak menjamin hasil tertentu tanpa mekanisme resolution.

## 5. Dynamic Generation

Monster dapat dihasilkan secara dinamis berdasarkan context yang relevan, misalnya:

```text
REGION / LOCATION
HABITAT
ENVIRONMENT
TIME
SEASON
ECOLOGICAL PRESSURE
WORLD STATE
GENERATION SEED / PARAMETERS
```

Generator tidak boleh menggunakan fixed catalog sebagai satu-satunya sumber keberadaan monster.

Jika monster menjadi material, generation menghasilkan stable identity dan data yang cukup untuk continuity.

## 6. Generation Determinism

Generation harus menggunakan seed, parameter, atau mekanisme deterministik ekuivalen bila diperlukan untuk menjaga hasil yang konsisten.

Runtime wajib mencari MONSTER_ID yang sudah persisted sebelum membuat entity baru.

Pemanggilan generator ulang tidak boleh menggandakan monster persisten tanpa resolution yang sah.

## 7. Lifecycle

Monster dapat memiliki lifecycle yang relevan terhadap dunia, termasuk:

```text
SPAWNED / BORN
→ GROWTH / DEVELOPMENT
→ ACTIVE
→ INJURED / DORMANT / MIGRATING
→ DEAD / REMOVED
```

Lifecycle aktual tidak boleh diasumsikan jika tidak didukung state atau module.

## 8. Agency & Behavior

Monster memiliki agency sesuai capability dan cognition-nya.

Behavior dapat dipengaruhi oleh:

- kebutuhan,
- hunger/thirst,
- territory,
- fear,
- aggression,
- social structure,
- injury,
- mating/reproduction,
- resources,
- threats,
- knowledge,
- dan environmental pressure.

Monster tidak wajib menyerang Player dan tidak wajib menghindari Player.

## 9. Population & Persistence Threshold

Tidak setiap organisme harus menjadi entity persisten individual.

Population-level simulation dapat digunakan untuk entity yang belum material.

Ketika individual monster menjadi material bagi gameplay melalui combat, interaction, tracking, capture, quest, loot, atau konsekuensi lain, monster harus memperoleh stable identity/state sesuai kebutuhan persistence.

## 10. Interaction With World

Monster dapat menyebabkan atau mengalami perubahan pada:

- settlement security,
- NPC behavior,
- faction response,
- economy,
- quests,
- events,
- environment,
- character state,
- dan world state.

Setiap perubahan material mengikuti Cause + Origin + State Change + History.

## 11. Combat Integration

Combat terhadap monster menggunakan `13_COMBAT.md`.

Monster current state, capability, condition, positioning, knowledge, dan behavior yang relevan harus dimuat sebelum resolution.

Death, escape, capture, injury, atau perubahan lain harus dipersistenkan sebagai state outcome.

## 12. Loot Integration

Loot dari monster tidak otomatis.

Jika resolution menghasilkan material loot, `15_LOOT_GENERATION.md` menentukan generation berdasarkan source dan context.

## 13. Information Boundary

Character, NPC, faction, dan Player tidak otomatis mengetahui species, location, capability, weakness, population, atau state monster.

Informasi harus mengikuti Information State.

## 14. State Change

Perubahan monster mengikuti:

```text
CURRENT STATE
↓
CAUSE / EVENT / ACTION
↓
RESOLUTION
↓
STATE DELTA
↓
VALIDATION
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 15. Canon Safety

Module ini tidak menetapkan:

- katalog monster tetap,
- stat monster universal,
- damage universal,
- drop table universal,
- habitat absolut,
- atau perilaku tunggal untuk semua monster.

Data spesifik harus berasal dari repository, state, generation, atau resolution yang sah.

## 16. Dependencies

Konteks utama: `02_REALMS_AND_REGIONS`, `03_CITIES_AND_SETTLEMENTS`, `12_VITALITY_SURVIVAL`, `13_COMBAT`.

Integrasi: `15_LOOT_GENERATION`, `16_NPC_SYSTEM`, `18_WORLD_EVENTS`, `25_WORLD_STATE`, `28_MONSTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Monster bukan encounter sekali pakai; monster adalah bagian dari ekosistem hidup yang dapat dihasilkan secara dinamis, memiliki agency, dan menjadi persisten ketika material bagi dunia.**
