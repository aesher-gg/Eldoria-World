# ELDORIA WORLD — MONSTER ECOSYSTEM

> **Module:** 14 — Monster Ecosystem
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1

## 1. Purpose

Mendefinisikan monster sebagai bagian dari ekosistem hidup yang dapat muncul, bergerak, berkembang, berinteraksi, dan berubah berdasarkan habitat, kebutuhan, kondisi, serta world state.

Module ini menggunakan **Monster Canon terbatas** sebagai fondasi spesies/jenis resmi dan **Dynamic Monster Generation** untuk populasi, individu, dan variasi di runtime.

## 2. Monster Canon Registry

Eldoria memiliki katalog **Monster Canon maksimum 150 jenis/spesies**.

```text
MONSTER CANON
MAXIMUM = 150 TYPES / SPECIES
```

150 adalah batas katalog Canon, **bukan batas jumlah individu monster yang boleh hidup di dunia**.

Monster Canon ditetapkan oleh Admin dan dapat dikelompokkan ke tingkat ancaman/kekuatan yang ditetapkan Canon. Distribusi tingkat tidak boleh ditebak oleh AI GM bila belum ditetapkan.

AI GM tidak boleh menambahkan spesies baru ke Monster Canon hanya melalui generation atau narrative.

## 3. Monster Classes

Secara konseptual:

```text
MONSTER CANON
├── TINGKAT RENDAH
├── TINGKAT MENENGAH
├── TINGKAT TINGGI
└── TINGKAT PUNCAK
```

Nama dan jumlah sub-tier final dapat ditetapkan Admin tanpa mengubah batas maksimum 150 jenis.

Tier Canon menentukan klasifikasi/species capability baseline; individual state tetap dapat berbeda karena umur, kondisi, habitat, mutation/evolution rules, equipment/effect, atau faktor sah lainnya.

## 4. Monster Identity

Monster Canon wajib memiliki stable species identity, misalnya:

```text
MONSTER_CANON_ID
NAME
SPECIES / TYPE
CANON_TIER
CANON_ORIGIN
CANON_DEFINITION
```

Individual monster yang menjadi material wajib memiliki:

```text
MONSTER_ID
MONSTER_CANON_ID (bila berasal dari Canon species)
NAME / DESIGNATION
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
```

Field yang belum diketahui = `???`.

## 5. Ecological State

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

## 6. Habitat & Ecology

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

## 7. Dynamic Generation

Monster dapat dihasilkan secara dinamis berdasarkan context yang relevan, misalnya:

```text
REGION / LOCATION
HABITAT
ENVIRONMENT
TIME
SEASON
ECOLOGICAL PRESSURE
WORLD STATE
MONSTER CANON DEFINITION (jika species Canon)
GENERATION SEED / PARAMETERS
```

Generator boleh memilih monster Canon yang sesuai dengan ecology atau menghasilkan creature dynamic yang diizinkan Canon.

Generator tidak boleh mengubah creature dynamic menjadi Monster Canon baru tanpa Admin Canon.

## 8. Generation Determinism

Generation harus menggunakan seed, parameter, atau mekanisme deterministik ekuivalen bila diperlukan untuk menjaga hasil yang konsisten.

Runtime wajib mencari MONSTER_ID yang sudah persisted sebelum membuat entity baru.

Pemanggilan generator ulang tidak boleh menggandakan monster persisten tanpa resolution yang sah.

## 9. Lifecycle

Monster dapat memiliki lifecycle yang relevan terhadap dunia, termasuk:

```text
SPAWNED / BORN
→ GROWTH / DEVELOPMENT
→ ACTIVE
→ INJURED / DORMANT / MIGRATING
→ DEAD / REMOVED
```

Lifecycle aktual tidak boleh diasumsikan jika tidak didukung state atau module.

## 10. Agency & Behavior

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

## 11. Population & Persistence Threshold

Tidak setiap organisme harus menjadi entity persisten individual.

Population-level simulation dapat digunakan untuk entity yang belum material.

Ketika individual monster menjadi material bagi gameplay melalui combat, interaction, tracking, capture, quest, loot, atau konsekuensi lain, monster harus memperoleh stable identity/state sesuai kebutuhan persistence.

## 12. Interaction With World

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

## 13. Combat Integration

Combat terhadap monster menggunakan `13_COMBAT.md`.

Monster current state, capability, condition, positioning, knowledge, dan behavior yang relevan harus dimuat sebelum resolution.

Death, escape, capture, injury, atau perubahan lain harus dipersistenkan sebagai state outcome.

## 14. Loot Integration

Loot dari monster tidak otomatis.

Jika resolution menghasilkan material loot, `15_LOOT_GENERATION.md` menentukan generation berdasarkan source dan context.

## 15. Information Boundary

Character, NPC, faction, dan Player tidak otomatis mengetahui species, location, capability, weakness, population, atau state monster.

Informasi harus mengikuti Information State.

## 16. State Change

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

## 17. Canon Safety

Monster Canon adalah katalog resmi Admin dengan batas maksimum 150 jenis/spesies.

AI GM tidak boleh:

- menambahkan spesies Canon baru,
- menghapus spesies Canon,
- mengubah tier Canon,
- mengubah identity Canon,
- atau mengubah lore Canon

hanya melalui narrative/generation.

Perubahan Canon membutuhkan Admin Canon update. Perubahan individual tetap menggunakan Monster State dan runtime resolution.

## 18. Dependencies

Konteks utama: `02_REALMS_AND_REGIONS`, `03_CITIES_AND_SETTLEMENTS`, `12_VITALITY_SURVIVAL`, `13_COMBAT`.

Integrasi: `15_LOOT_GENERATION`, `16_NPC_SYSTEM`, `18_WORLD_EVENTS`, `25_WORLD_STATE`, `28_MONSTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 19. Final Principle

> **Monster Canon menyediakan maksimal 150 jenis resmi; population/ecology dan Dynamic Generation menyediakan kehidupan monster dalam jumlah besar; individual yang material dapat menjadi persistent tanpa menjadikan seluruh populasi sebagai database.**
