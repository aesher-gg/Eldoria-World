# ELDORIA WORLD — FACTIONS

> **Module:** 04 — Factions
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan struktur dasar faction sebagai entitas sosial/politis yang memiliki tujuan, kepentingan, resources, hubungan, dan agency sendiri.

## 2. Faction Identity

Faction persisten wajib memiliki:

```text
FACTION_ID
NAME
TYPE
LEADERSHIP
GOALS
INTERESTS
CURRENT_STATE
ORIGIN
HISTORY
```

Field yang belum diketahui = `???`.

## 3. Faction Types

Faction dapat berupa:

- kingdom,
- noble house,
- guild,
- military order,
- religious organization,
- criminal organization,
- mercantile organization,
- adventuring group,
- tribe,
- local community,
- atau tipe lain yang diizinkan dunia.

Jenis aktual mengikuti data atau generation yang sah.

## 4. Agency

Faction bukan dekorasi naratif. Faction dapat:

- mengejar objective,
- mengalokasikan resources,
- merekrut,
- berdagang,
- bernegosiasi,
- memusuhi,
- membuat aliansi,
- memberi atau mencabut akses,
- bereaksi terhadap event,
- dan mengubah kebijakan.

Semua perubahan material harus melalui resolution dan persistence.

## 5. Goals & Interests

Goals adalah tujuan yang ingin dicapai faction.

Interests adalah kepentingan yang memengaruhi pilihan faction.

Keduanya tidak otomatis berarti faction akan berhasil. Outcome ditentukan oleh kondisi dan resolution.

## 6. Resources

Resource faction dapat mencakup, bila relevan:

- gold/material,
- manpower,
- territory,
- information,
- military capability,
- political influence,
- infrastructure,
- alliances.

Nilai aktual harus berasal dari state atau mekanisme generation yang sah.

## 7. Relations

Hubungan antar-faction dapat memiliki state seperti:

```text
ALLY
FRIENDLY
NEUTRAL
TENSE
HOSTILE
AT_WAR
```

Daftar tersebut adalah kategori operasional, bukan kewajiban semua faction memiliki setiap state.

Perubahan hubungan wajib memiliki Cause + Origin + State Change + History.

## 8. Territory & Influence

Faction dapat memiliki territory atau influence tanpa harus memiliki sovereignty penuh.

Control, influence, dan claim adalah konsep berbeda dan tidak boleh disamakan tanpa aturan module terkait.

## 9. Membership

Character/NPC dapat memiliki relationship dengan faction seperti member, employee, ally, enemy, client, target, atau status lain yang sah.

Membership tidak otomatis memberi akses atau reward; hak dan konsekuensi mengikuti faction state, reputation, contract, dan rules yang relevan.

## 10. Faction Knowledge

Faction hanya menggunakan informasi yang tersedia bagi entity/agent faction menurut Information State.

Player knowledge tidak otomatis menjadi faction knowledge.

## 11. Dynamic Faction

Faction dapat dihasilkan secara dinamis jika generation mengizinkannya.

Faction yang menjadi material harus memperoleh stable identity, origin, generation data, current state, dan history.

## 12. Persistence

Perubahan faction dapat berdampak pada:

- territory,
- settlement,
- NPC,
- economy,
- reputation,
- quests,
- events,
- conflict,
- dan world state.

Module Router wajib memuat module terkait ketika konsekuensi menyentuh domain tersebut.

## 13. Boundary

Module ini mendefinisikan faction sebagai entity dan framework dasar. Detail perilaku politik, reputation, ekonomi, event, dan combat ditentukan module terkait.

## 14. Dependencies

Konteks geografis: `01_WORLD_OVERVIEW`, `02_REALMS_AND_REGIONS`, `03_CITIES_AND_SETTLEMENTS`.

Integrasi utama: `16_NPC_SYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `25_WORLD_STATE`, `27_NPC_STATE`.

## 15. Canon Safety

Module ini tidak membuat katalog faction spesifik. Nama, kekuasaan, hubungan, atau sejarah faction yang belum ditetapkan tetap `???` sampai tersedia melalui sumber yang sah.

## 16. Final Principle

> **Faction memiliki agency dan kepentingan sendiri; Player dapat memengaruhinya, tetapi tidak memiliki kendali otomatis atas outcome faction.**
