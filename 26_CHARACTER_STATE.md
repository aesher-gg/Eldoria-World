# ELDORIA WORLD — CHARACTER STATE

> **Module:** 26 — Character State
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

`CHARACTER_STATE` adalah authoritative persistent snapshot kondisi terkini satu Character.

## 2. Identity

```text
PLAYER_ID
CHARACTER_ID
STATE_VERSION
STATUS
LOCATION
WORLD_TIME / LOCAL TIME REFERENCE
VITALITY
ATTRIBUTES
CLASS
SKILLS
MAGIC
EQUIPMENT
INVENTORY
CURRENCY
FACTION RELATIONS
REPUTATION REFERENCES
QUESTS
CONDITIONS
KNOWLEDGE
ACTIVE EFFECTS
ORIGIN REFERENCES
HISTORY REFERENCES
```

Field yang belum diketahui = `???`.

## 3. Authority

Current Character State yang telah committed adalah sumber kebenaran kondisi karakter.
Narrative lama tidak boleh mengalahkan state terbaru.

Persistent History menjelaskan perubahan masa lalu dan tidak menggantikan current state.

## 4. Identity Separation

`PLAYER_ID` mengidentifikasi Player.
`CHARACTER_ID` mengidentifikasi Character.

Satu tidak boleh digunakan sebagai pengganti yang lain.

## 5. State Snapshot & Delta

Perubahan karakter mengikuti:

```text
CURRENT STATE
↓
ACTION / EVENT / EFFECT
↓
RESOLUTION
↓
STATE DELTA
↓
VALIDATION
↓
HISTORY + ORIGIN
↓
ATOMIC PERSISTENCE
↓
NEW STATE
```

## 6. Valid Changes

Perubahan dapat menyentuh vitality, attributes, skills, class, magic, equipment, inventory, currency, location, reputation, faction relation, quest, condition, knowledge, atau status jika resolution mengizinkannya.

Tidak ada perubahan hanya karena Player menyatakannya sebagai fakta.

## 7. Knowledge Boundary

Character Knowledge harus dipisahkan dari Player Knowledge dan World Knowledge.

Character tidak otomatis mengetahui hidden state, NPC intention, monster weakness, event, location, atau information lain yang belum diperoleh secara sah.

## 8. Location & Time

Location Character harus konsisten dengan travel/action resolution.

Jika action menghabiskan waktu, time delta harus diterapkan sebelum state berikutnya digunakan.

## 9. Equipment & Inventory

Equipped item, possessed item, owned item, location, quantity, dan condition harus konsisten dengan `10_EQUIPMENT_SYSTEM`.

Tidak boleh ada duplicate possession melalui state yang bertentangan.

## 10. Vitality

HP, stamina, hunger, thirst, injury, condition, dan recovery mengikuti `12_VITALITY_SURVIVAL`.

Tidak ada free heal atau recovery tanpa valid cause.

## 11. Progression

Class, skill, magic, attributes, dan progression hanya berubah melalui mekanisme module yang relevan.

Tidak ada free level, skill, spell, atau capability.

## 12. Lifecycle

Character status dapat mencakup:

```text
CREATED
ACTIVE
INACTIVE
CAPTURED
MISSING
DEAD
RETIRED
```

Transisi status harus memiliki cause, resolution, validation, history, dan origin.

## 13. Concurrency & Idempotency

Setiap state memiliki `STATE_VERSION` atau mekanisme ekuivalen.

Transaction menggunakan `TURN_ID` unik.

Transaction lama tidak boleh menimpa state baru dan turn yang sudah committed tidak boleh dieksekusi ulang.

## 14. Atomic Persistence

Character State, material History, dan Origin yang menyertainya harus dipersistenkan secara atomic.

Failure menghasilkan no partial character state.

## 15. Dynamic Data

Generated class, skill, item, quest, relationship, condition, atau entity reference dapat masuk ke Character State hanya setelah valid generation/resolution.

## 16. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` + `09_MAGIC_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY` + `12_VITALITY_SURVIVAL`.

Integrasi: `13_COMBAT`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `23_PARTY_SYSTEM`, `24_PETS_AND_COMPANIONS`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Character State adalah satu-satunya snapshot authoritative kondisi Character saat ini; setiap perubahan harus dapat ditelusuri ke resolution, cause, history, dan origin.**
