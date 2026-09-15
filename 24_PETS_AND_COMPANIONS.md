# ELDORIA WORLD — PETS & COMPANIONS

> **Module:** 24 — Pets and Companions
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan pet dan companion sebagai entity yang dapat memiliki identity, state, agency, relationship, progression, dan lifecycle sendiri.

Module ini menetapkan framework, bukan katalog pet/companion atau kemampuan universal.

## 2. Entity Identity

Pet/companion persisten wajib memiliki:

```text
COMPANION_ID
NAME / DESIGNATION
TYPE / SPECIES
OWNER_ID / RELATIONSHIP
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Agency

Companion bukan equipment hidup.

Mereka dapat memiliki:

- needs,
- goals,
- preferences,
- fears,
- knowledge,
- relationships,
- capability,
- condition,
- dan keputusan sendiri.

Agency aktual mengikuti capability dan cognition entity.

## 4. Relationship & Ownership

Bedakan:

```text
OWNER
KEEPER
ALLY
CONTRACT
BOND
DEPENDENT
```

Status relationship tidak otomatis berarti ownership atau obedience.

Perubahan relationship/ownership harus memiliki Cause + Origin + State Change + History.

## 5. Acquisition

Pet/companion dapat diperoleh melalui:

- taming,
- adoption,
- rescue,
- contract,
- purchase,
- inheritance,
- discovery,
- faction mechanism,
- quest resolution,
- atau mekanisme lain yang sah.

Tidak ada companion gratis tanpa valid acquisition mechanism.

## 6. Needs & Care

Companion dapat membutuhkan food, water, rest, shelter, medical care, training, social interaction, habitat, atau resource lain bila relevan.

Kebutuhan yang diabaikan dapat menghasilkan state consequences melalui resolution.

## 7. Training & Progression

Training dapat memengaruhi skill, behavior, trust, capability, atau relationship bila system mendukungnya.

Progression tidak otomatis berhasil hanya karena Player melakukan training.

## 8. Combat Integration

Companion dapat menjadi combatant jika capability dan context memungkinkan.

Mereka menggunakan current state dan agency sendiri dalam `13_COMBAT.md`.

Player tidak otomatis menentukan serangan, damage, survival, atau keputusan companion.

## 9. Party Integration

Companion dapat menjadi member party melalui `23_PARTY_SYSTEM.md`.

Membership tidak menghapus individual state atau agency.

## 10. Lifecycle

Companion dapat mengalami:

```text
CREATED / BORN
→ ACTIVE
→ INJURED / MISSING / CAPTURED / DORMANT
→ DEAD / RETIRED / RELEASED
```

Revival hanya melalui mekanisme sah.

## 11. Dynamic Generation

Companion dapat digenerate secara dinamis berdasarkan species, habitat, relationship context, discovery, event, quest, atau mekanisme lain yang sah.

Entity material wajib memiliki stable identity, origin, generation data, state, dan history.

## 12. Persistence Threshold

Entity yang hanya bersifat background tidak harus dipersistenkan individual.

Companion harus menjadi persistent ketika memiliki ownership, contract, relationship, quest role, combat role, material interaction, atau consequence dunia.

## 13. Information Boundary

Player/Character tidak otomatis mengetahui seluruh capability, needs, loyalty, health, knowledge, atau hidden traits companion.

Informasi mengikuti Information State.

## 14. State Changes

```text
ACTION / EVENT / NEED
↓
RESOLUTION
↓
STATE DELTA
↓
VALIDATION
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 15. Cross-System Integration

Companion dapat berinteraksi dengan:

- party,
- combat,
- vitality,
- equipment,
- economy,
- NPCs,
- monsters,
- quests,
- factions,
- reputation,
- world state.

Module terkait wajib dimuat ketika konsekuensi menyentuh domain tersebut.

## 16. Canon Safety

Module ini tidak menetapkan fixed species list, loyalty score, combat bonus, growth rate, taming chance, atau automatic obedience.

## 17. Dependencies

`05_CHARACTER_SYSTEM` + `08_SKILLS` + `12_VITALITY_SURVIVAL` + `13_COMBAT` + `16_NPC_SYSTEM` + `23_PARTY_SYSTEM`.

Integrasi: `10_EQUIPMENT_SYSTEM`, `11_ECONOMY`, `14_MONSTER_ECOSYSTEM`, `15_LOOT_GENERATION`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `28_MONSTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 18. Final Principle

> **Pet dan companion adalah entitas hidup dengan state dan agency sendiri; hubungan, training, loyalty, dan outcome harus lahir dari simulasi, bukan kepemilikan otomatis.**
