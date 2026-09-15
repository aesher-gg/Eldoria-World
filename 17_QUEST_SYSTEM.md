# ELDORIA WORLD — QUEST SYSTEM

> **Module:** 17 — Quest System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan quest sebagai objective-driven state yang dapat berasal dari kebutuhan NPC, tujuan faction, world event, discovery, contract, atau generation yang sah.

Module ini menetapkan framework, bukan katalog quest atau reward tetap.

## 2. Quest Identity

Quest persisten wajib memiliki:

```text
QUEST_ID
TITLE / DESIGNATION
SOURCE
ISSUER / ORIGINATOR
OBJECTIVES
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Quest State

Quest dapat memiliki state seperti:

```text
AVAILABLE
ACCEPTED
ACTIVE
PROGRESSING
COMPLETED
FAILED
EXPIRED
CANCELLED
```

Tidak semua quest harus menggunakan semua state.

## 4. Quest Sources

Quest dapat muncul melalui:

- NPC need,
- NPC goal,
- faction objective,
- world event,
- discovery,
- contract,
- settlement problem,
- character interaction,
- atau generator yang sah.

Player request tidak dengan sendirinya menciptakan quest.

## 5. Objectives

Objective harus dapat dikaitkan dengan kondisi yang dapat di-resolve, misalnya:

```text
TARGET
LOCATION
ITEM / RESOURCE
ACTION
INFORMATION
RELATIONSHIP
SURVIVAL
EVENT RESPONSE
```

Objective tidak boleh dianggap selesai hanya karena Player menyatakan telah menyelesaikannya.

## 6. Acceptance

Quest menjadi ACTIVE/ACCEPTED hanya jika acceptance mechanism dan prerequisites terpenuhi.

Acceptance dapat memiliki:

- contract,
- faction requirement,
- reputation requirement,
- payment,
- deadline,
- permission,
- atau condition lain yang sah.

## 7. Progression

Progress quest harus berasal dari validated state changes.

Contoh:

```text
ACTION / EVENT
↓
RESOLUTION
↓
OBJECTIVE CONDITION MET
↓
QUEST STATE DELTA
↓
VALIDATION
↓
PERSISTENCE
```

## 8. Failure & Expiry

Quest dapat gagal karena outcome, deadline, issuer state, objective destruction, faction change, death, atau kondisi lain yang sah.

Failure bukan otomatis punishment; konsekuensinya ditentukan oleh resolution dan source.

## 9. Rewards

Reward hanya diberikan setelah completion resolution yang valid.

Reward dapat berupa item, currency, access, reputation, information, relationship change, capability, atau konsekuensi lain bila diizinkan.

Tidak ada guaranteed reward tanpa basis.

## 10. Dynamic Generation

Quest dapat digenerate dari world context menggunakan input seperti:

```text
NPC NEEDS / GOALS
FACTION OBJECTIVES
WORLD EVENTS
LOCATION CONDITIONS
CHARACTER CONTEXT
CURRENT WORLD STATE
GENERATION SEED / PARAMETERS
```

Generated quest yang menjadi material harus memiliki stable identity dan persistence.

## 11. Anti-Duplicate Generation

Quest yang sudah persisted tidak boleh digenerate ulang sebagai quest baru hanya karena generator dipanggil kembali.

Runtime harus memeriksa QUEST_ID dan generation identity sebelum membuat replacement.

## 12. Information Boundary

Character hanya mengetahui quest information yang diperoleh melalui issuer, discovery, communication, records, atau mekanisme lain yang sah.

Hidden objectives tidak otomatis diketahui Player/Character.

## 13. World Consequences

Quest dapat memengaruhi:

- NPC,
- faction,
- settlement,
- economy,
- monster ecosystem,
- world events,
- reputation,
- character state,
- dan world state.

Module terkait wajib dimuat jika konsekuensi menyentuh domain tersebut.

## 14. Quest Resolution

```text
QUEST STATE
↓
PLAYER / NPC / WORLD ACTION
↓
RESOLVE OBJECTIVE
↓
GENERATE STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
↓
REWARD / CONSEQUENCE RESOLUTION
```

Reward dan consequence yang material harus ikut transaction sesuai aturan atomic persistence.

## 15. Canon Safety

Module ini tidak menetapkan fixed quest list, objective formula universal, deadline universal, atau reward table universal.

## 16. Dependencies

`05_CHARACTER_SYSTEM` + `16_NPC_SYSTEM` + `18_WORLD_EVENTS` + `19_FACTION_SYSTEM` + `20_REPUTATION`.

Integrasi: `10_EQUIPMENT_SYSTEM`, `11_ECONOMY`, `14_MONSTER_ECOSYSTEM`, `15_LOOT_GENERATION`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `29_EVENT_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Quest adalah state yang lahir dari kebutuhan dan kondisi dunia; completion, failure, reward, dan consequence semuanya merupakan hasil resolution.**
