# ELDORIA WORLD — MODULE ROUTER

> **Module:** 32 — Module Router
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Runtime module selection and loading contract

## 0. PURPOSE

Module Router menentukan module, state, history, origin, dan entity records yang wajib dimuat untuk satu Turn Transaction berdasarkan intent, entity yang terlibat, dan konsekuensi yang mungkin disentuh.

Router tidak menentukan outcome dan tidak mengubah state. Router hanya menghasilkan Routing Plan untuk Action Resolver.

## 1. INPUT

```text
TURN_ID
PLAYER_MESSAGE
ACTOR_ID
RELEVANT_ENTITY_IDS
CURRENT_STATE REFERENCES
INDEX VERSION / CANON VERSION
```

`INDEX.md` wajib telah di-fetch dan diverifikasi pada turn tersebut.

## 2. BASELINE LOAD

Setiap turn minimal memerlukan `INDEX.md`, `00_CORE_RULES.md`, current relevant state, dan relevant history/origin.

## 3. ENTITY DISCOVERY & AUTHORITY

Sebelum membuat entity baru, Router wajib memeriksa sumber entity resmi yang relevan.

### Player Character

```text
PLAYER/CHARACTER REFERENCE
↓
PLAYER REGISTRY / CHARACTER RECORD
↓
CURRENT CHARACTER STATE
```

### Race Canon

Jika `RACE_CANON_ID` atau race-related action relevan:

```text
36_RACE_SYSTEM.md
↓
races/CANON_REGISTRY.md
↓
RACE_CANON_ID / RACE DEFINITION
```

Race tidak boleh ditebak atau dibuat oleh Router.

### Canon NPC

```text
NPC REFERENCE
↓
npcs/CANON_REGISTRY.md
↓
CANON NPC RECORD
↓
NPC STATE bila tersedia
```

Jika Canon NPC sesuai ditemukan, gunakan record tersebut dan jangan membuat duplicate Dynamic NPC.

### Faction Canon

Jika action menyentuh faction, organization, membership, authority, faction relationship, faction action, atau NPC dengan faction Canon:

```text
04_FACTIONS.md
↓
19_FACTION_SYSTEM.md
↓
factions/CANON_REGISTRY.md
↓
RELEVANT FACTION STATE bila tersedia
```

`04_FACTIONS.md` = identity/framework authority.
`19_FACTION_SYSTEM.md` = operational behavior authority.
`factions/CANON_REGISTRY.md` = authority faction spesifik yang telah di-Canonize.

`npcs/COVERAGE_MATRIX_v1_0.md` hanya planning context dan tidak menggantikan faction/identity/state authority.

Membership, rank, authority, access, resources, knowledge, reputation, dan loyalty tidak boleh diasumsikan dari registry saja.

### Dynamic Entity

Jika tidak ada authoritative entity yang cocok dan generation diizinkan, Dynamic entity dapat dibuat sesuai rules. Material entity mengikuti persistence threshold dan stable identity requirements.

## 4. ROUTING PRINCIPLE

Router menggunakan domain yang benar-benar disentuh action, bukan sekadar keyword.

| Intent | Module utama | Registry / support |
|---|---|---|
| Faction action | `19_FACTION_SYSTEM.md` | `04_FACTIONS.md` + `factions/CANON_REGISTRY.md` + relevant state |
| NPC / social interaction | `16_NPC_SYSTEM.md` | `npcs/CANON_REGISTRY.md` + `27_NPC_STATE.md` bila persistent |
| Race | `36_RACE_SYSTEM.md` | `races/CANON_REGISTRY.md` + relevant state |
| Combat | `13_COMBAT.md` | relevant state + equipment/vitality |
| Travel | `02_REALMS_AND_REGIONS.md`, `25_WORLD_STATE.md` | vitality, character state, events |
| Trade | `11_ECONOMY.md` | equipment, NPC/faction context, reputation, state |
| Quest | `17_QUEST_SYSTEM.md` | NPC, faction, event, reputation, state |

Dependency modules tetap mengikuti INDEX dan module masing-masing.

## 5. DEPENDENCY LOADING

Dependency dimuat secara rekursif. Gunakan `VISITED_SET` atau ekuivalen untuk mencegah duplicate load dan infinite recursion.

## 6. STATE AUTHORITY

```text
CHARACTER_STATE → kondisi karakter
NPC_STATE       → kondisi NPC
MONSTER_STATE   → kondisi monster
WORLD_STATE     → kondisi dunia
EVENT_STATE     → kondisi event persisten
```

Canon Definition/Registry adalah authority identity/fakta Canon. Current State adalah authority kondisi terkini.

## 7. HISTORY & ORIGIN

Untuk entity atau perubahan material, Router wajib memasukkan `30_HISTORY_SYSTEM.md` dan `31_ORIGIN_LOG.md` sebagai context yang relevan. Router tidak membuat History/Origin.

## 8. UNKNOWN / AMBIGUOUS INTENT

```text
ROUTE = MINIMAL SAFE CONTEXT
OUTCOME = UNRESOLVED
```

Router tidak boleh menebak action.

## 9. INFORMATION BOUNDARY

Router hanya memuat information state yang sah untuk actor/resolution. Player knowledge tidak otomatis menjadi Character/NPC/Faction knowledge.

## 10. ROUTING PLAN

```text
TURN_ID
ROUTE_STATUS
PRIMARY_MODULES
SECONDARY_MODULES
STATE_SOURCES
CANON_SOURCES
HISTORY_SOURCES
ORIGIN_SOURCES
ENTITY_IDS
DEPENDENCY_GRAPH / LOAD ORDER
INFORMATION_SCOPE
TIME_SCOPE
FAILURE_REASON
```

## 11. ROUTER INVARIANTS

Router wajib:

- fetch/verify INDEX setiap turn;
- resolve Player Character dari authority resmi;
- load Race authority bila relevan;
- check Canon NPC sebelum Dynamic NPC generation;
- check specific Faction Canon Registry sebelum faction interpretation/generation;
- tidak resolve outcome;
- tidak mutate state;
- tidak mengarang module/data;
- tidak melewati dependency;
- tidak memakai stale assumptions;
- menjaga unique identity;
- menjaga information boundary;
- menghormati `???`;
- membawa `TURN_ID`.

## 12. FAILURE

Jika required module, Canon record, faction registry, atau authoritative state tidak tersedia:

```text
ROUTE FAILURE
↓
NO RESOLUTION
↓
NO STATE CHANGE
↓
NO FALSE HISTORY / ORIGIN
```

## 13. HANDOFF

```text
PLAYER MESSAGE
↓
TURN_ID
↓
INDEX VERIFY
↓
MODULE ROUTER
↓
ROUTING PLAN
↓
ACTION RESOLVER
```

> **Module Router menentukan apa yang harus dibaca dan source authority mana yang harus diperiksa; bukan apa yang harus terjadi.**
