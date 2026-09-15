# ELDORIA WORLD — CHARACTER SYSTEM

> **Module:** 05 — Character System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1

## 1. Purpose

Module ini mendefinisikan struktur Player Character (PC), identity, lifecycle, knowledge boundary, dan hubungan karakter dengan sistem Eldoria.

Module ini mendefinisikan **schema dan aturan**, bukan katalog karakter atau nilai statistik tetap.

## 2. Player Character Authority

Player Character bukan entity yang boleh dibuat bebas oleh AI GM.

Alur resmi:

```text
PLAYER
↓
memberikan nama + latar belakang + detail karakter
↓
ADMIN
↓
validasi terhadap Canon + template Eldoria
↓
PLAYER REGISTRY / CHARACTER RECORD
↓
CURRENT CHARACTER STATE
↓
AI GM menjalankan roleplay
```

AI GM **tidak boleh membuat Player Character baru, mengganti identity dasar, atau menetapkan background sebagai fakta Canon** tanpa Character Record resmi dari Admin.

Jika karakter baru belum terdaftar, AI GM harus meminta proses registrasi/Admin, bukan mengarang karakter resmi.

## 3. Character Identity

Setiap Player Character persisten wajib memiliki identity stabil:

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

## 4. Player Registry

Registry adalah daftar karakter resmi yang telah didaftarkan Admin.

Registry minimal menghubungkan:

```text
PLAYER_ID
CHARACTER_ID
CHARACTER STATUS
CHARACTER RECORD LOCATION
REGISTRATION ORIGIN
```

Registry tidak menggantikan Current Character State. State terkini tetap authoritative pada state layer yang relevan.

## 5. Character Lifecycle

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

## 6. Current Character State

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

## 7. Character History

Peristiwa material yang memengaruhi karakter dicatat melalui History sesuai `30_HISTORY_SYSTEM.md`.

History bukan pengganti Current State.

## 8. Origin

Data karakter dan perubahan karakter harus dapat ditelusuri melalui Origin sesuai `31_ORIGIN_LOG.md`.

Contoh source yang sah:

- Player creation request,
- Admin registration,
- Player action,
- NPC action,
- World Event,
- Quest Resolution,
- Combat Resolution,
- System Generation,
- Admin Canon.

## 9. Player Agency

Player mengendalikan intent dan tindakan karakter, bukan outcome.

Karakter tidak boleh memperoleh kemampuan, item, status, relationship, atau progression hanya karena Player menyatakannya sebagai fakta.

## 10. Character Knowledge

Pengetahuan karakter adalah bagian dari Information State.

```text
PLAYER KNOWLEDGE ≠ CHARACTER KNOWLEDGE
```

Karakter hanya dapat menggunakan informasi yang secara sah tersedia bagi karakter melalui pengalaman, komunikasi, discovery, skill, atau mekanisme lain yang relevan.

## 11. Progression Boundary

Progression karakter ditentukan oleh module yang relevan:

- Attributes → `06_ATTRIBUTES.md`
- Classes → `07_CLASSES.md`
- Skills → `08_SKILLS.md`
- Magic → `09_MAGIC_SYSTEM.md`

Module ini tidak memberikan progression gratis atau angka perkembangan default.

## 12. Location & Travel

Location karakter adalah bagian dari Current State. Perubahan location harus berasal dari resolution yang sah.

Travel tidak boleh mengubah location tanpa memperhitungkan durasi dan konsekuensi yang relevan.

## 13. Relationships

Character dapat memiliki hubungan dengan NPC, faction, party, pet, companion, quest, settlement, dan entity lain.

Relationship yang menjadi material dan persisten harus memiliki identity/state/history/origin yang sesuai.

## 14. Death & Revival

`DEAD` adalah state, bukan sekadar narasi.

Perubahan dari `DEAD` ke status aktif hanya sah melalui mekanisme revival yang diizinkan oleh module/world.

## 15. Dynamic Character Creation Boundary

AI GM dapat menjalankan **runtime simulation** untuk character-like entities bila module mengizinkan, tetapi itu tidak sama dengan membuat Player Character resmi.

Tidak ada dynamic generation yang boleh menghasilkan atau menggantikan Player Character resmi.

Duplicate identity terhadap `CHARACTER_ID` atau `PLAYER_ID` yang sudah terdaftar dilarang.

## 16. Validation Requirements

Character State Delta minimal harus memeriksa:

- `CHARACTER_ID` valid,
- character terdaftar atau memiliki authority yang sah,
- current state tersedia,
- `STATE_VERSION` cocok,
- perubahan memiliki Cause + Origin,
- prerequisite module terpenuhi,
- tidak ada contradiction,
- `TURN_ID` belum committed.

## 17. Canon Safety

Module ini tidak menetapkan ras, statistik, class, skill, magic, item, atau latar belakang karakter tertentu sebagai fakta Canon.

Detail Player Character berasal dari **Admin Character Registration** berdasarkan input Player, lalu dari state/resolution yang sah.

## 18. Dependencies

Module ini menjadi basis bagi:

`06_ATTRIBUTES` · `07_CLASSES` · `08_SKILLS` · `09_MAGIC_SYSTEM` · `10_EQUIPMENT_SYSTEM` · `12_VITALITY_SURVIVAL` · `13_COMBAT` · `20_REPUTATION` · `23_PARTY_SYSTEM` · `24_PETS_AND_COMPANIONS` · `26_CHARACTER_STATE`.

Registry Player terintegrasi dengan INDEX, Module Router, State Validator, dan Save Pipeline.

## 19. Final Principle

> **Player memberikan identitas dan latar karakter; Admin mendaftarkan Player Character sebagai entitas resmi; AI GM menjalankan karakter tersebut dan sistem menentukan outcome.**
