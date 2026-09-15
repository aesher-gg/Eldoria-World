# ELDORIA WORLD — EVENT STATE

> **Module:** 29 — Event State
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

`EVENT_STATE` adalah authoritative persistent snapshot untuk World Event yang material dan sedang/baru selesai diproses.

## 2. Identity

```text
EVENT_ID
STATE_VERSION
TYPE
TRIGGER
SCOPE
LOCATION / REGION
TIMESTAMP
SEQUENCE
CURRENT_STATE
PARTICIPANTS / AFFECTED ENTITIES
CONSEQUENCES
ORIGIN
HISTORY REFERENCES
```

Field yang belum diketahui = `???`.

## 3. Lifecycle

Event dapat memiliki lifecycle:

```text
TRIGGERED
→ PENDING / ACTIVE
→ RESOLVED
→ COMPLETED / FAILED / CANCELLED
```

Status aktual berasal dari resolution dan state.

## 4. Authority

Current Event State yang committed adalah authoritative.

History menjelaskan kejadian sebelumnya; narrative tidak dapat mengganti status event.

## 5. Trigger & Scope

Event dapat dipicu oleh character, NPC, monster, faction, quest, economy, environment, time, chain reaction, atau generation yang sah.

Scope dapat bersifat local, settlement, regional, factional, realm-wide, atau world-wide bila resolution mendukungnya.

## 6. Event Resolution

```text
TRIGGER
↓
LOAD RELEVANT STATE
↓
CHECK CONDITIONS
↓
RESOLVE EVENT
↓
STATE DELTA
↓
VALIDATE
↓
HISTORY + ORIGIN
↓
ATOMIC PERSISTENCE
```

## 7. Consequences

Event dapat mengubah world state, character/NPC/monster state, faction, economy, quests, reputation, environment, atau entity lain.

Affected persistent states harus tetap konsisten dengan event transaction atau mekanisme queued event yang sah.

## 8. Ordering

Event yang berinteraksi harus dapat diurutkan menggunakan `TIMESTAMP`, `SEQUENCE`, dan/atau mekanisme ordering yang sah.

Event tidak boleh diproses ulang hanya karena runtime membaca record yang sama.

## 9. Chain & Cascading Events

Satu event dapat memicu event lain jika kondisi dan module mengizinkannya.

Setiap event turunan harus memiliki Origin yang menunjuk pada event/cause pemicunya.

## 10. Dynamic Generation

Event dapat digenerate secara dinamis berdasarkan world state, time, entity actions, thresholds, environment, atau mechanism yang sah.

Generated event yang material wajib memperoleh stable identity, origin, state, dan history.

## 11. Information Boundary

Event State internal tidak otomatis diketahui Character, NPC, atau Player.

Knowledge mengikuti Information State.

## 12. Concurrency & Idempotency

`STATE_VERSION` melindungi event dari stale overwrite.

`TURN_ID` atau event execution identity mencegah duplicate resolution.

## 13. Atomic Persistence

Event State, affected state changes, History, dan Origin yang menjadi bagian transaction harus konsisten dan atomic sesuai `35_SAVE_PIPELINE.md`.

## 14. Failure & Recovery

Jika resolution, validation, atau persistence gagal, event tidak boleh meninggalkan partial consequence.

Runtime harus reload/re-resolve/abort sesuai recovery rules.

## 15. Canon Safety

Module ini tidak menetapkan fixed event calendar, universal trigger, predetermined outcome, atau future history.

## 16. Dependencies

`18_WORLD_EVENTS` + `25_WORLD_STATE`.

Integrasi: `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `28_MONSTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Event State mempertahankan lifecycle dan konsekuensi event secara authoritative; event hanya menjadi fakta dunia setelah berhasil di-resolve, divalidasi, dan dipersistenkan.**
