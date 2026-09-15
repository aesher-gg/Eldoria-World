# ELDORIA WORLD — CHARACTER SYSTEM

> **Module:** 05 — Character System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Module ini mendefinisikan struktur karakter persisten, identity, lifecycle, knowledge boundary, dan hubungan karakter dengan sistem Eldoria.

Module ini mendefinisikan **schema dan aturan**, bukan katalog karakter atau nilai statistik tetap.

## 2. Character Identity

Setiap karakter persisten wajib memiliki identity stabil:

```text
PLAYER_ID
CHARACTER_ID
NAME
STATUS
ORIGIN
HISTORY
CURRENT_STATE
```

`CHARACTER_ID` harus unik dalam World. `PLAYER_ID` mengidentifikasi pemilik/player dan tidak menggantikan identity karakter.

## 3. Character Lifecycle

Lifecycle minimal dapat menggunakan:

```text
CREATED
ACTIVE
INACTIVE
CAPTURED
MISSING
DEAD
RETIRED
```

Status aktual harus berasal dari state/resolution. Daftar ini tidak berarti semua status wajib tersedia pada setiap implementasi.

## 4. Current Character State

Current Character State adalah sumber kebenaran kondisi karakter saat ini.

Field dapat mencakup:

```text
IDENTITY
LOCATION
VITALITY
ATTRIBUTES
CLASS
SKILLS
MAGIC
EQUIPMENT
INVENTORY
CURRENCY
FACTION_RELATIONS
REPUTATION
QUESTS
CONDITIONS
KNOWLEDGE
STATUS
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 5. Character History

Peristiwa material yang memengaruhi karakter dicatat melalui History sesuai `30_HISTORY_SYSTEM.md`.

History bukan pengganti Current State.

## 6. Origin

Data karakter dan perubahan karakter harus dapat ditelusuri melalui Origin sesuai `31_ORIGIN_LOG.md`.

Contoh source yang sah:

- Player creation,
- Player action,
- NPC action,
- World Event,
- Quest Resolution,
- Combat Resolution,
- System Generation,
- Admin Canon.

## 7. Player Agency

Player mengendalikan intent dan tindakan karakter, bukan outcome.

Karakter tidak boleh memperoleh kemampuan, item, status, relationship, atau progression hanya karena Player menyatakannya sebagai fakta.

## 8. Character Knowledge

Pengetahuan karakter adalah bagian dari Information State.

```text
PLAYER KNOWLEDGE ≠ CHARACTER KNOWLEDGE
```

Karakter hanya dapat menggunakan informasi yang secara sah tersedia bagi karakter melalui pengalaman, komunikasi, discovery, skill, atau mekanisme lain yang relevan.

## 9. Progression Boundary

Progression karakter ditentukan oleh module yang relevan:

- Attributes → `06_ATTRIBUTES.md`
- Classes → `07_CLASSES.md`
- Skills → `08_SKILLS.md`
- Magic → `09_MAGIC_SYSTEM.md`

Module ini tidak memberikan progression gratis atau angka perkembangan default.

## 10. Location & Travel

Location karakter adalah bagian dari Current State. Perubahan location harus berasal dari resolution yang sah.

Travel tidak boleh mengubah location tanpa memperhitungkan durasi dan konsekuensi yang relevan.

## 11. Relationships

Character dapat memiliki hubungan dengan NPC, faction, party, pet, companion, quest, settlement, dan entity lain.

Relationship yang menjadi material dan persisten harus memiliki identity/state/history/origin yang sesuai.

## 12. Death & Revival

`DEAD` adalah state, bukan sekadar narasi.

Perubahan dari `DEAD` ke status aktif hanya sah melalui mekanisme revival yang diizinkan oleh module/world.

## 13. Dynamic Character Creation

Karakter baru dapat dibuat melalui mekanisme creation yang sah.

Dynamic generation tidak boleh menghasilkan duplicate identity untuk karakter yang sudah persisten.

Karakter yang menjadi material bagi gameplay harus memperoleh stable identity dan persistence.

## 14. Validation Requirements

Character State Delta minimal harus memeriksa:

- `CHARACTER_ID` valid,
- current state tersedia,
- `STATE_VERSION` cocok,
- perubahan memiliki Cause + Origin,
- prerequisite module terpenuhi,
- tidak ada contradiction,
- `TURN_ID` belum committed.

## 15. Dependencies

Module ini menjadi basis bagi:

`06_ATTRIBUTES` · `07_CLASSES` · `08_SKILLS` · `09_MAGIC_SYSTEM` · `10_EQUIPMENT_SYSTEM` · `12_VITALITY_SURVIVAL` · `13_COMBAT` · `20_REPUTATION` · `23_PARTY_SYSTEM` · `24_PETS_AND_COMPANIONS` · `26_CHARACTER_STATE`.

## 16. Canon Safety

Module ini tidak menetapkan ras, statistik, class, skill, magic, item, atau latar belakang karakter tertentu sebagai fakta Canon.

Detail karakter harus berasal dari data karakter, creation system, generation, atau resolution yang sah.

## 17. Final Principle

> **Character adalah entitas persisten dengan identity dan state; Player memilih tindakan, sistem menentukan hasil.**
