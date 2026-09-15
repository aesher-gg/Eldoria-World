# ELDORIA WORLD — NPC SYSTEM

> **Module:** 16 — NPC System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan NPC sebagai entitas hidup dengan identity, needs, goals, knowledge, relationships, capability, agency, dan lifecycle.

Module ini menetapkan framework, bukan katalog NPC tetap.

## 2. NPC Identity

NPC persisten wajib memiliki:

```text
NPC_ID
NAME / DESIGNATION
ROLE / TYPE
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
```

Field yang belum diketahui = `???`.

## 3. NPC State

State dapat mencakup, bila relevan:

```text
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
FACTION_RELATIONS
REPUTATION
KNOWLEDGE
CURRENT_ACTIVITY
CONDITIONS
STATUS
STATE_VERSION
```

Nilai aktual harus berasal dari state atau resolution yang sah.

## 4. Agency

NPC memiliki kemampuan mengambil keputusan sesuai capability, knowledge, needs, goals, relationships, resources, dan kondisi.

NPC dapat:

- bekerja,
- berdagang,
- bepergian,
- membantu,
- menolak,
- berbohong,
- bernegosiasi,
- bertarung,
- melarikan diri,
- merekrut,
- membuat keputusan sosial,
- atau melakukan tindakan lain yang sah.

NPC tidak dipaksa mengikuti plot Player.

## 5. Needs & Goals

Needs adalah tekanan/kebutuhan yang memengaruhi perilaku.

Goals adalah tujuan yang ingin dicapai.

Keduanya bukan jaminan keberhasilan; outcome tetap melalui resolution.

## 6. Knowledge Boundary

NPC memiliki knowledge state sendiri.

NPC tidak otomatis mengetahui:

- Player knowledge,
- Character knowledge,
- hidden world state,
- identitas tersembunyi,
- atau informasi yang belum diperoleh.

Informasi diperoleh melalui observation, communication, rumor, records, faction network, discovery, atau mekanisme sah lain.

## 7. Relationships

NPC dapat memiliki hubungan dengan:

- Character,
- NPC lain,
- Faction,
- Settlement,
- Monster,
- atau entity lain.

Hubungan dapat memengaruhi trust, cooperation, hostility, access, trade, information, dan decisions sesuai resolution.

## 8. Dynamic Generation

NPC dapat dihasilkan secara dinamis berdasarkan context seperti:

```text
LOCATION
SETTLEMENT
FACTION
ROLE / NEED
WORLD STATE
EVENT CONTEXT
GENERATION SEED / PARAMETERS
```

Jika NPC menjadi material, generator harus memberi stable identity, origin, generation data, current state, dan history.

## 9. Persistence Threshold

NPC background yang tidak material dapat direpresentasikan secara abstrak.

NPC harus menjadi persistent entity ketika memiliki dampak material melalui interaction, quest, relationship, transaction, combat, faction activity, information, atau konsekuensi dunia.

## 10. Lifecycle

NPC dapat mengalami lifecycle seperti:

```text
CREATED / BORN
→ ACTIVE
→ INACTIVE / MISSING / CAPTURED
→ DEAD / RETIRED
```

State aktual menentukan lifecycle; tidak ada automatic resurrection atau replacement tanpa mekanisme sah.

## 11. World Interaction

NPC dapat memengaruhi dan dipengaruhi oleh:

- economy,
- settlement,
- faction,
- reputation,
- quests,
- events,
- combat,
- monsters,
- environment,
- dan world state.

Module Router wajib memuat module yang relevan terhadap konsekuensi.

## 12. NPC Actions

NPC action mengikuti pipeline yang sama dengan actor lain:

```text
INTENT / NEED / GOAL
↓
CAPABILITY + KNOWLEDGE CHECK
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

## 13. Anti-Plot Behavior

AI GM dilarang membuat NPC:

- otomatis membantu Player,
- otomatis percaya Player,
- otomatis memberikan reward,
- menjadi bodoh demi plot,
- mengetahui informasi tanpa source,
- atau mengubah tujuan tanpa sebab.

Perubahan perilaku harus memiliki cause yang relevan.

## 14. Information & Narrative

Narrative hanya mengungkap NPC berdasarkan informasi yang Character dapat akses.

Internal NPC state dapat tetap hidden jika belum diketahui.

## 15. Canon Safety

Module ini tidak menetapkan katalog NPC, personality template wajib, moral alignment universal, atau outcome sosial universal.

NPC spesifik berasal dari repository, persistent state, atau dynamic generation yang sah.

## 16. Dependencies

`03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS` + `05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` + `09_MAGIC_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY` + `12_VITALITY_SURVIVAL`.

Integrasi: `14_MONSTER_ECOSYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `25_WORLD_STATE`, `27_NPC_STATE`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **NPC adalah agen dunia yang hidup; mereka memiliki tujuan dan pengetahuan sendiri, sehingga hubungan dengan Player harus menjadi hasil simulasi, bukan skrip.**
