# ELDORIA WORLD — FACTION SYSTEM

> **Module:** 19 — Faction System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan operational behavior faction: bagaimana faction mengubah kebijakan, mengejar tujuan, menggunakan resources, bereaksi terhadap dunia, dan menghasilkan konsekuensi.

Module 04 mendefinisikan identity dan framework dasar faction. Module ini mendefinisikan operational resolution tanpa menggantikan Module 04.

## 2. Operational State

Faction dapat memiliki state seperti:

```text
OBJECTIVES
PRIORITIES
RESOURCES
POLICIES
TERRITORY
INFLUENCE
MEMBERSHIP
ALLIANCES
CONFLICTS
KNOWN_INFORMATION
CURRENT_ACTIONS
```

Nilai aktual berasal dari authoritative state.

## 3. Faction Decision Model

Faction action dapat dipengaruhi oleh:

- goals,
- interests,
- resources,
- leadership,
- internal politics,
- threats,
- opportunities,
- relationships,
- information,
- territory,
- economy,
- reputation,
- quests,
- events,
- dan member capabilities.

Faction memilih tindakan melalui resolution; keberhasilan tidak otomatis.

## 4. Faction Actions

Faction dapat melakukan, bila capability dan context memungkinkan:

- recruit,
- dismiss,
- trade,
- negotiate,
- tax,
- patrol,
- expand influence,
- defend territory,
- sanction,
- ally,
- threaten,
- attack,
- retreat,
- investigate,
- change policy,
- atau tindakan lain yang valid.

## 5. Territory, Claim & Influence

Bedakan:

```text
CONTROL
CLAIM
INFLUENCE
OCCUPATION
```

Perubahan salah satu tidak otomatis mengubah yang lain.

Material territorial change harus melalui world-state resolution.

## 6. Diplomacy

Hubungan faction dapat berubah berdasarkan:

- actions,
- agreements,
- violations,
- trade,
- conflict,
- events,
- reputation,
- resource pressure,
- dan informasi.

Perubahan relationship mengikuti Cause + Origin + State Change + History.

## 7. Membership & Internal Structure

Faction dapat memiliki hierarchy, departments, ranks, contracts, allies, clients, dependents, atau struktur lain.

Membership dan authority tidak otomatis diberikan karena Player meminta.

Promosi, demosi, pengusiran, perekrutan, dan perubahan status memerlukan resolution yang sah.

## 8. Resources

Faction resource dapat mencakup material, currency, manpower, territory, information, infrastructure, military capability, political capital, atau resource lain yang relevan.

Tidak ada angka universal tanpa state/source.

## 9. Information Boundary

Faction bertindak berdasarkan informasi yang benar-benar tersedia bagi faction atau agent-nya.

Player knowledge tidak otomatis menjadi faction knowledge.

## 10. Faction Reaction to Events

World Event dapat memicu faction response.

Response tidak otomatis dan bergantung pada faction state, goals, capabilities, knowledge, dan resolution.

## 11. Faction vs Player

Player dapat memengaruhi faction melalui tindakan yang valid.

Player tidak memiliki kendali otomatis atas:

- kebijakan faction,
- hubungan faction,
- promosi,
- akses,
- perang,
- reward,
- atau keputusan leadership.

## 12. Dynamic Faction Behavior

Faction dapat mengalami perubahan internal dan eksternal tanpa Player hadir ketika world agency mengizinkannya.

Material changes harus dipersistenkan.

## 13. Resolution Flow

```text
FACTION STATE / TRIGGER
↓
IDENTIFY OBJECTIVE / DECISION
↓
CHECK RESOURCES + KNOWLEDGE + CAPABILITY
↓
RESOLVE ACTION
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 14. Cross-System Effects

Faction resolution dapat memengaruhi:

- settlements,
- NPCs,
- characters,
- economy,
- quests,
- events,
- monsters,
- reputation,
- world state.

Module terkait wajib dimuat sesuai konsekuensi.

## 15. Canon Safety

Module ini tidak membuat faction baru secara otomatis dan tidak menetapkan outcome politik universal.

Faction spesifik mengikuti `04_FACTIONS.md`, persistent state, dan valid generation/resolution.

## 16. Dependencies

`04_FACTIONS` adalah identity/framework authority.

Integrasi: `03_CITIES_AND_SETTLEMENTS`, `11_ECONOMY`, `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `20_REPUTATION`, `25_WORLD_STATE`, `27_NPC_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Faction adalah aktor dunia yang mengejar kepentingannya sendiri; hubungan dan keputusan politik merupakan hasil state, informasi, resources, dan resolution.**
