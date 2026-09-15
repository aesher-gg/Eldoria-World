# ELDORIA WORLD — WORLD EVENTS

> **Module:** 18 — World Events
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan event sebagai perubahan dunia yang memiliki trigger, scope, timing, resolution, dan konsekuensi.

Event dapat muncul dari Player/NPC/Monster action, faction activity, environment, quest, scheduled condition, atau dynamic generation yang sah.

## 2. Event Identity

Event persisten wajib memiliki:

```text
EVENT_ID
TYPE
TRIGGER
SCOPE
LOCATION / REGION
TIMESTAMP
SEQUENCE
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Event Lifecycle

Event dapat memiliki lifecycle seperti:

```text
TRIGGERED
→ PENDING / ACTIVE
→ RESOLVED
→ COMPLETED / FAILED / CANCELLED
```

State aktual ditentukan resolution.

## 4. Trigger

Trigger dapat berasal dari:

- player action,
- NPC action,
- monster activity,
- faction action,
- quest resolution,
- environmental condition,
- time condition,
- economy condition,
- chain reaction,
- atau generator yang sah.

Tidak ada event material tanpa cause atau trigger yang dapat ditelusuri.

## 5. Scope

Event dapat berskala:

- local,
- settlement,
- regional,
- realm,
- faction,
- atau world-wide,

sesuai mekanisme dan dampaknya.

Scope tidak boleh diperluas tanpa dasar resolution.

## 6. Event Ordering

Ketika beberapa event berinteraksi, ordering harus dapat ditentukan menggunakan:

```text
TIMESTAMP
SEQUENCE
ORIGIN
```

atau mekanisme ekuivalen yang sah.

Event yang telah committed tidak boleh diam-diam dihapus dari History.

## 7. Resolution

Event resolution mempertimbangkan current world state, actor state, trigger, scope, environment, dependencies, dan module terkait.

Flow:

```text
TRIGGER
↓
LOAD RELEVANT STATE
↓
RESOLVE EVENT
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 8. World Consequences

Event dapat mengubah:

- settlements,
- factions,
- NPCs,
- monsters,
- economy,
- quests,
- environment,
- characters,
- reputation,
- dan world state.

Setiap material consequence harus melalui module yang relevan.

## 9. Chain & Cascading Events

Satu event dapat memicu event lain jika condition dan mechanism terpenuhi.

Event turunan harus memiliki origin yang menunjuk pada event penyebab dan tidak boleh dianggap terjadi jika resolution belum menghasilkan trigger yang valid.

## 10. World Agency

Event tidak harus berpusat pada Player.

Dunia dapat menghasilkan perubahan melalui faction, NPC, monster, economy, environment, atau sistem lain yang berjalan sesuai Canon.

## 11. Dynamic Generation

Event dapat digenerate berdasarkan world context.

Generated event yang menjadi material harus memiliki stable identity, origin, generation data, current state, dan history.

Generator tidak boleh menggandakan event yang sudah persisted.

## 12. Information Boundary

Player/Character hanya mengetahui event sesuai information state.

Event dapat berlangsung tanpa diketahui Player jika tidak ada mekanisme discovery/observation/communication.

## 13. Cancellation & Failure

Event dapat gagal atau dibatalkan hanya melalui kondisi/resolution yang sah.

Failure tidak menghapus fact bahwa trigger/event pernah terjadi; History tetap merekam kejadian yang committed.

## 14. Canon Safety

Module ini tidak menetapkan event tetap, kalender event wajib, atau outcome universal.

## 15. Dependencies

`01_WORLD_OVERVIEW` + `02_REALMS_AND_REGIONS` + `03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS` + `12_VITALITY_SURVIVAL`.

Integrasi: `14_MONSTER_ECOSYSTEM`, `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `25_WORLD_STATE`, `29_EVENT_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 16. Final Principle

> **World Event adalah perubahan dunia yang terpicu dan ter-resolve secara nyata; event tidak menunggu Player dan tidak boleh menjadi narasi tanpa state consequence yang sah.**
