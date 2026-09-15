# ELDORIA WORLD — PARTY SYSTEM

> **Module:** 23 — Party System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan party sebagai group persisten atau sementara yang memiliki membership, leadership, objectives, shared context, dan group dynamics.

Module ini menetapkan framework, bukan komposisi party atau bonus universal.

## 2. Party Identity

Party yang menjadi material dapat memiliki:

```text
PARTY_ID
NAME / DESIGNATION
LEADER_ID
MEMBERS
OBJECTIVES
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Membership

Member dapat berupa Character, NPC, Pet/Companion, atau entity lain yang valid.

Membership memiliki status, waktu/peristiwa masuk, dan bila relevan hak/role.

Bergabung, keluar, dikeluarkan, atau diganti tidak boleh terjadi tanpa valid resolution.

## 4. Leadership & Roles

Party dapat memiliki leader dan role seperti scout, defender, support, crafter, navigator, atau role lain bila relevan.

Role tidak otomatis memberikan capability yang tidak dimiliki member.

## 5. Objectives & Decisions

Party dapat memiliki shared objectives, tetapi setiap member tetap memiliki agency.

Party decision dapat dipengaruhi oleh goals, leadership, relationships, trust, knowledge, needs, resources, dan kondisi.

Consensus tidak boleh diasumsikan.

## 6. Group Dynamics

Party dapat mengalami:

- cooperation,
- disagreement,
- conflict,
- trust change,
- loyalty change,
- departure,
- leadership change,
- atau dissolution.

Perubahan material harus memiliki Cause + Origin + State Change + History.

## 7. Shared vs Individual State

Shared party state tidak boleh menggantikan current state individual member.

Inventory, HP, equipment, currency, knowledge, reputation, relationship, dan status tetap milik entity masing-masing kecuali ada mekanisme sharing yang sah.

## 8. Party Actions

Party action dapat mencakup travel, combat, exploration, trade, quest, camp, negotiation, atau aktivitas lain yang diizinkan.

Action tetap harus di-resolve berdasarkan capability dan state tiap actor yang relevan.

## 9. Combat Integration

Dalam combat, party bukan satu entity otomatis.

Setiap combatant mempertahankan identity, state, initiative/tactical position, dan agency sendiri sesuai `13_COMBAT.md`.

## 10. Travel & Time

Party travel menggunakan resolution perjalanan yang berlaku.

Perbedaan kecepatan, condition, terrain, resources, dan keputusan member dapat memengaruhi outcome bila relevan.

Tidak boleh ada teleportasi grup tanpa mechanism sah.

## 11. Dynamic Generation

Party dapat terbentuk melalui character/NPC interaction, faction assignment, quest, contract, event, atau generation yang sah.

Party material wajib memperoleh stable identity, origin, state, dan history.

## 12. Persistence Threshold

Group sementara tidak wajib menjadi persistent bila tidak material.

Party harus dipersistenkan ketika memiliki consequence material seperti quest, contract, shared asset, relationship, combat, faction activity, atau world impact.

## 13. Information Boundary

Knowledge party tidak otomatis sama dengan knowledge setiap member.

Informasi yang diperoleh satu member harus disebarkan hanya melalui komunikasi atau mekanisme yang sah.

## 14. Resolution Flow

```text
PARTY ACTION / MEMBERSHIP CHANGE
↓
LOAD PARTY + RELEVANT MEMBER STATE
↓
CHECK AUTHORITY / CAPABILITY / CONSENT WHERE REQUIRED
↓
RESOLVE
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 15. Canon Safety

Module ini tidak menetapkan party size, universal bonus, automatic loyalty, shared inventory, atau guaranteed cooperation.

## 16. Dependencies

`05_CHARACTER_SYSTEM` + `16_NPC_SYSTEM` + `20_REPUTATION`.

Integrasi: `11_ECONOMY`, `12_VITALITY_SURVIVAL`, `13_COMBAT`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `21_CRAFTING`, `22_ALCHEMY`, `24_PETS_AND_COMPANIONS`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Party adalah kumpulan agen individual dengan tujuan bersama yang tidak menghapus agency, state, knowledge, atau konsekuensi masing-masing member.**
