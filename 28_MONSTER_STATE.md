# ELDORIA WORLD — MONSTER STATE

> **Module:** 28 — Monster State
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

`MONSTER_STATE` adalah authoritative persistent snapshot kondisi monster individual yang telah menjadi material bagi gameplay.

## 2. Identity

```text
MONSTER_ID
STATE_VERSION
NAME / DESIGNATION
SPECIES / TYPE
STATUS
LOCATION
HABITAT
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
ACTIVE EFFECTS
ORIGIN REFERENCES
GENERATION_DATA
HISTORY REFERENCES
```

Field yang belum diketahui = `???`.

## 3. Authority

Current Monster State yang committed adalah authoritative untuk monster tersebut.

Narrative atau hasil generator baru tidak boleh menggantikan persisted state tanpa valid resolution.

## 4. Ecology Integration

Monster State mengikuti `14_MONSTER_ECOSYSTEM.md`.

Habitat, needs, resources, injury, territory, population context, environment, dan lifecycle dapat memengaruhi perilaku dan survival bila relevan.

## 5. Agency & Knowledge

Monster memiliki behavior dan agency sesuai capability/cognition.

Monster Knowledge berbeda dari Player/Character/NPC Knowledge.

## 6. Materialization

Monster dapat tetap berada pada population-level simulation sampai menjadi material melalui combat, tracking, capture, quest, loot, interaction, atau consequence lain.

Saat material, monster memperoleh stable identity/state.

## 7. State Changes

```text
CURRENT STATE
↓
ACTION / EVENT / ENVIRONMENT
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
```

## 8. Combat & Loot

Combat menggunakan `13_COMBAT.md`.

Jika death atau injury terjadi, state harus diperbarui melalui transaction.

Loot hanya muncul jika resolution menghasilkan eligibility sesuai `15_LOOT_GENERATION.md`.

## 9. Lifecycle

Monster dapat berubah melalui birth/spawn, growth, active state, injury, dormancy, migration, capture, death, removal, atau lifecycle lain yang valid.

Tidak ada automatic respawn setelah death kecuali mechanism yang sah.

## 10. Dynamic Generation

Generator wajib memeriksa `MONSTER_ID` yang sudah persisted sebelum membuat entity baru.

Generated monster yang material harus mempertahankan generation data yang diperlukan untuk continuity.

## 11. Concurrency & Idempotency

`STATE_VERSION` mencegah stale overwrite.

`TURN_ID` mencegah duplicate transaction.

## 12. Atomic Persistence

Monster State, History, dan Origin yang menyertainya harus dipersistenkan secara atomic.

Failure berarti tidak ada partial monster state.

## 13. Dependencies

`12_VITALITY_SURVIVAL` + `13_COMBAT` + `14_MONSTER_ECOSYSTEM` + `15_LOOT_GENERATION`.

Integrasi: `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `25_WORLD_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 14. Canon Safety

Module ini tidak menetapkan fixed monster stats, species catalog, respawn rule, damage, loot, habitat, atau behavior universal.

## 15. Final Principle

> **Monster State mempertahankan continuity monster material sebagai bagian dari ekosistem hidup; generator tidak boleh menghapus atau mengganti state persisten.**
