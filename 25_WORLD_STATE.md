# ELDORIA WORLD — WORLD STATE

> **Module:** 25 — World State
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

`WORLD_STATE` adalah authoritative persistent snapshot mengenai kondisi bersama Eldoria pada waktu tertentu.

World State menjawab **apa yang sedang terjadi**, bukan daftar seluruh fakta yang pernah ada.

## 2. Authority

Untuk kondisi terkini, World State yang telah berhasil di-commit adalah authoritative.
History dan Origin menjelaskan bagaimana kondisi tersebut terbentuk.
Narrative tidak mengalahkan World State.

## 3. World State Identity

```text
WORLD_ID
STATE_VERSION
WORLD_TIME
CURRENT_CONDITIONS
ACTIVE_EVENTS
REGIONAL_STATE
SETTLEMENT_STATE REFERENCES
FACTION_STATE REFERENCES
ECONOMIC / ENVIRONMENTAL STATE REFERENCES
ACTIVE_WORLD_EFFECTS
ORIGIN
HISTORY REFERENCES
```

Field yang belum diketahui = `???`.

## 4. World Time

World Time menggunakan struktur:

```text
ERA
YEAR
SEASON
DATE
DAY
WEATHER
HOUR
```

World Time dan Local Environment adalah data berbeda.

## 5. Scope

World State dapat menyimpan atau mereferensikan kondisi global, regional, settlement, faction, economy, environment, event, dan perubahan lain yang memiliki dampak bersama.

Detail entity-specific tetap berada pada state entity terkait.

## 6. State Delta

World change harus direpresentasikan sebagai:

```text
BEFORE
→ CAUSE / EVENT / ACTION
→ RESOLUTION
→ STATE DELTA
→ VALIDATION
→ HISTORY / ORIGIN
→ ATOMIC PERSISTENCE
→ AFTER
```

Tidak ada perubahan world state tanpa valid resolution.

## 7. World Agency

World State dapat berubah karena:

- NPC actions,
- monster/ecology changes,
- faction actions,
- economy,
- quests,
- events,
- environment,
- character actions,
- time progression,
- atau mekanisme sistem lain yang sah.

Player bukan satu-satunya sumber perubahan.

## 8. Cross-Entity Consistency

Jika perubahan world memengaruhi entity tertentu, state entity tersebut harus diperbarui secara konsisten dalam transaction yang sama atau melalui event/state mechanism yang sah.

Tidak boleh ada world state yang menyatakan sesuatu telah terjadi sementara authoritative entity state masih secara langsung menyangkalnya tanpa pending/queued mechanism yang valid.

## 9. Information Boundary

World State internal tidak otomatis menjadi Character, NPC, atau Player Knowledge.

Knowledge harus diperoleh melalui valid information mechanism.

## 10. Persistence & Versioning

Setiap persistent World State memiliki `STATE_VERSION` atau mekanisme ekuivalen.

Transaction terhadap versi lama harus ditolak jika versi saat commit telah berubah.

## 11. Dynamic Generation

Dynamic generation dapat mengubah World State hanya setelah generation menjadi valid resolution.

Generated world facts yang material harus memperoleh Origin dan persistence yang cukup untuk continuity.

## 12. Atomicity

World State change yang material harus dipersistenkan bersama History dan Origin yang menyertainya sesuai `35_SAVE_PIPELINE.md`.

Failure berarti tidak ada partial world change.

## 13. Recovery

```text
VERSION CONFLICT / FAILURE
↓
REJECT / ROLLBACK
↓
RELOAD LATEST WORLD STATE
↓
RE-RESOLVE OR ABORT
```

State lama tidak boleh menimpa state baru.

## 14. Dependencies

`01_WORLD_OVERVIEW` + `02_REALMS_AND_REGIONS` + `03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS`.

Integrasi: `14_MONSTER_ECOSYSTEM`, `15_LOOT_GENERATION`, `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `23_PARTY_SYSTEM`, `24_PETS_AND_COMPANIONS`, `29_EVENT_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 15. Canon Safety

Module ini tidak menetapkan fixed world events, political outcomes, economy values, geography, population, or future history.

## 16. Final Principle

> **World State adalah snapshot authoritative dunia yang sedang berlangsung; semua perubahan harus lahir dari resolution dan dipersistenkan secara konsisten.**
