# ELDORIA WORLD — NPC STATE

> **Module:** 27 — NPC State
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

`NPC_STATE` adalah authoritative persistent snapshot kondisi terkini NPC yang material bagi dunia.

## 2. Identity

```text
NPC_ID
STATE_VERSION
NAME / DESIGNATION
STATUS
LOCATION
VITALITY
ATTRIBUTES
CLASS / ROLE
SKILLS
MAGIC
EQUIPMENT
INVENTORY
CURRENCY
NEEDS
GOALS
RELATIONSHIPS
FACTION RELATIONS
REPUTATION REFERENCES
KNOWLEDGE
CURRENT ACTIVITY
CONDITIONS
ACTIVE EFFECTS
ORIGIN REFERENCES
HISTORY REFERENCES
```

Field yang belum diketahui = `???`.

## 3. Authority

Current NPC State yang telah committed adalah authoritative.
Narrative tidak boleh mengubah kondisi NPC tanpa resolution.

## 4. Agency

NPC State menyimpan kondisi yang digunakan untuk menentukan perilaku dan keputusan NPC.

Goals, needs, knowledge, relationships, capability, resource, dan condition dapat memengaruhi action.

## 5. Knowledge Boundary

NPC Knowledge terpisah dari Player dan Character Knowledge.

NPC tidak otomatis mengetahui informasi yang hanya diketahui Player/Character.

## 6. State Changes

```text
NPC ACTION / WORLD EVENT / EXTERNAL EFFECT
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

## 7. Lifecycle

NPC dapat menjadi active, inactive, missing, captured, dead, retired, atau status lain yang sah.

Status transition harus memiliki cause dan resolution.

## 8. Relationships & Reputation

Relationship dan reputation adalah state/contextual data dan tidak boleh diperlakukan sebagai nilai universal.

Perubahan harus berasal dari evidence atau resolution yang relevan.

## 9. Equipment & Economy

Inventory, possession, ownership, currency, equipment, dan economic effects harus konsisten dengan module terkait.

## 10. Dynamic Generation

NPC dapat digenerate secara dinamis.

NPC material wajib memiliki stable `NPC_ID`, origin, generation data, current state, dan history.

Generator tidak boleh menggandakan NPC persisted hanya karena dipanggil ulang.

## 11. Persistence Threshold

NPC background tidak wajib menjadi persistent individual.

NPC harus dipersistenkan ketika memiliki material interaction seperti dialogue consequence, combat, quest, relationship, transaction, faction role, or world impact.

## 12. Concurrency & Idempotency

`STATE_VERSION` melindungi state dari stale overwrite.

`TURN_ID` melindungi transaction dari duplicate execution.

## 13. Atomic Persistence

NPC State, History, dan Origin yang menyertainya harus dipersistenkan secara atomic.

Failure berarti tidak ada partial NPC change.

## 14. Cross-System Integration

NPC State terhubung dengan character, faction, reputation, quest, event, combat, economy, equipment, vitality, party, dan world state jika relevan.

## 15. Dependencies

`04_FACTIONS` + `05_CHARACTER_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY` + `12_VITALITY_SURVIVAL` + `16_NPC_SYSTEM` + `20_REPUTATION`.

Integrasi: `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `23_PARTY_SYSTEM`, `25_WORLD_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 16. Final Principle

> **NPC State adalah snapshot authoritative kondisi NPC; NPC tetap merupakan agen independen dan state-nya harus berkembang melalui resolution yang dapat ditelusuri.**
