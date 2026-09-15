# ELDORIA WORLD — RACE CANON REGISTRY

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Purpose:** Registry resmi ras Canon Eldoria

## 1. Authority

File ini adalah registry resmi untuk identity dan definition ras Canon Eldoria.

AI GM boleh menggunakan ras yang terdaftar untuk Character, NPC, Population Model, Faction, dan runtime generation sesuai rules.

AI GM **tidak boleh** membuat ras Canon baru, mengubah definition, atau menghapus ras Canon melalui narrative/runtime generation.

Perubahan registry membutuhkan Admin Canon update.

## 2. Race Identity Contract

Setiap ras Canon yang terdaftar wajib memiliki stable:

```text
RACE_CANON_ID
NAME
CLASSIFICATION
DESCRIPTION
ORIGIN
HISTORY
LIFESPAN / AGING MODEL
BIOLOGICAL TRAITS
INNATE CAPABILITIES
HABITAT / HISTORICAL DISTRIBUTION
CULTURAL VARIATION BOUNDARIES
CANON_ORIGIN
```

Field yang belum ditetapkan = `???`.

## 3. Canon vs Runtime

```text
CANON RACE DEFINITION
        ↓
Population / Character / NPC / Faction / World Simulation
        ↓
CURRENT STATE
```

Race Canon adalah identity/definition.
Current population, location, migration, relationship, affiliation, dan kondisi lain berada pada state layer yang relevan.

## 4. Population Rule

Registry tidak menentukan jumlah individu.

Satu ras dapat memiliki populasi sangat besar tanpa file individual untuk setiap anggota.

Distribusi populasi ditentukan oleh Canon geography, history, migration, culture, settlement context, faction policy, environment, dan Population Model yang sah.

## 5. Classification Rule

`CLASSIFICATION` digunakan untuk membedakan kategori Canon yang memang ditetapkan Admin.

Subrace, hybrid/mixed lineage, ethnicity, clan, cultural group, atau species/monster type tidak otomatis menjadi Race Canon terpisah.

## 6. Current Canon Registry

### RACE-001

```text
RACE_CANON_ID: RACE-001
NAME: ???
CLASSIFICATION: ???
DESCRIPTION: ???
ORIGIN: ???
HISTORY: ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: ???
INNATE CAPABILITIES: ???
HABITAT / HISTORICAL DISTRIBUTION: ???
CULTURAL VARIATION BOUNDARIES: ???
CANON_ORIGIN: ???
STATUS: RESERVED / NOT YET CANONIZED
```

> Slot ini sengaja belum diisi. Penetapan ras resmi dilakukan melalui Admin Canon setelah arsitektur Race System selesai diaudit.

### RACE-002+

Belum ditetapkan.

## 7. Canonization Gate

Sebelum sebuah ras menjadi Canon:

```text
PROPOSAL
↓
CHECK WORLD HISTORY
↓
CHECK GEOGRAPHY
↓
CHECK CULTURE
↓
CHECK MONSTER BOUNDARY
↓
CHECK CHARACTER / NPC INTEGRATION
↓
ADMIN CANON DECISION
↓
REGISTRY ENTRY
```

Nama atau konsep yang muncul dalam brainstorming, Player input, atau AI GM generation **belum menjadi Canon** sampai masuk registry.

## 8. No Guessing

Jika Race Canon Registry belum menentukan suatu fakta:

```text
VALUE = ???
```

AI GM tidak boleh mengubah `???` menjadi angka, sejarah, habitat, lifespan, kemampuan, atau distribusi yang dianggap resmi tanpa authority.

## 9. Integration

Race Registry diakses melalui:

`INDEX.md` → `36_RACE_SYSTEM.md` → `races/CANON_REGISTRY.md`

Runtime state dan persistence mengikuti:

`26_CHARACTER_STATE` · `27_NPC_STATE` · `28_MONSTER_STATE` · `30_HISTORY_SYSTEM` · `31_ORIGIN_LOG` · `32_MODULE_ROUTER` · `33_ACTION_RESOLVER` · `34_STATE_VALIDATOR` · `35_SAVE_PIPELINE`.

## 10. Current Status

```text
REGISTRY_STATUS: READY
CANON_RACE_COUNT: 0
RACE_CANON_SLOTS: OPEN
```

Tidak ada ras resmi yang ditetapkan oleh file ini sampai Admin mengisi entry Canon.

## Final Principle

> **Race Canon Registry adalah satu-satunya authority identity/definition ras resmi Eldoria; registry tidak menentukan populasi individual, dan AI GM tidak boleh menambah Canon Race secara spontan.**
