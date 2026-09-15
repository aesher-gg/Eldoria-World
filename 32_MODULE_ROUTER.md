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

Setiap turn minimal memerlukan:

```text
INDEX.md
00_CORE_RULES.md
CURRENT RELEVANT STATE
RELEVANT HISTORY / ORIGIN
```

Untuk Player Character, Router harus memastikan Character Registry/Record resmi ditemukan sebelum memakai identity dasar karakter.

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

Jika identity atau state entity memiliki `RACE_CANON_ID`, atau action menyentuh race, Router wajib memuat:

```text
36_RACE_SYSTEM.md
↓
races/CANON_REGISTRY.md
↓
RACE_CANON_ID / RACE DEFINITION
```

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

Jika Canon NPC dengan identity yang sesuai ditemukan, AI GM wajib menggunakannya dan dilarang membuat duplicate Dynamic NPC sebagai pengganti.

### Faction Canon

Jika action menyentuh faction, organization, membership, authority, faction relationship, faction action, atau NPC yang memiliki faction Canon:

```text
04_FACTIONS.md
↓
19_FACTION_SYSTEM.md
↓
factions/CANON_REGISTRY.md
↓
RELEVANT FACTION STATE bila tersedia
```

`04_FACTIONS.md` adalah authority identity/framework; `19_FACTION_SYSTEM.md` adalah authority operational behavior; `factions/CANON_REGISTRY.md` adalah authority untuk faction spesifik yang telah di-Canonize.

Planning documents seperti `world/GOVERNANCE_FACTION_MASTER.md` dan `npcs/COVERAGE_MATRIX_v1.0.md` memberi konteks planning tetapi tidak menggantikan faction identity/state authority.

Membership, rank, authority, access, resources, knowledge, reputation, dan loyalty tidak boleh diasumsikan dari faction registry saja.

### Monster Canon

```text
MONSTER SPECIES REFERENCE
↓
MONSTER CANON REGISTRY / DEFINITION
↓
INDIVIDUAL MONSTER STATE bila ada
```

### Dynamic Entity

Jika tidak ada authoritative entity yang cocok dan module mengizinkan generation, AI GM dapat membuat Dynamic entity sesuai generation rules. Entity yang menjadi material mengikuti persistence threshold dan stable identity requirements.

## 4. ROUTING PRINCIPLE

Router menggunakan domain yang benar-benar disentuh oleh action, bukan sekadar pencocokan kata.

| Intent | Module utama | Module pendukung |
|---|---|---|
| Faction action | `19_FACTION_SYSTEM.md` | `04_FACTIONS.md`, `factions/CANON_REGISTRY.md`, `16_NPC_SYSTEM.md`, `18_WORLD_EVENTS.md`, `20_REPUTATION.md` |
| NPC / social interaction | `16_NPC_SYSTEM.md` | `npcs/CANON_REGISTRY.md`, `27_NPC_STATE.md`, faction registry bila relevan |
| Attack | `13_COMBAT.md` | `12_VITALITY_SURVIVAL.md`, `10_EQUIPMENT_SYSTEM.md`, relevant state, `30_HISTORY_SYSTEM.md`, `31_ORIGIN_LOG.md` |
| Travel | `02_REALMS_AND_REGIONS.md`, `25_WORLD_STATE.md` | `12_VITALITY_SURVIVAL.md`, `26_CHARACTER_STATE.md`, `18_WORLD_EVENTS.md` |
| Trade | `11_ECONOMY.md` | `10_EQUIPMENT_SYSTEM.md`, NPC/faction context bila relevan, `20_REPUTATION.md`, state |
| Quest | `17_QUEST_SYSTEM.md` | NPC, faction, event, reputation, state modules |
| Race / racial identity | `36_RACE_SYSTEM.md` | Race Registry + relevant entity/population state |
| Population / migration by race | `36_RACE_SYSTEM.md` | `02_REALMS_AND_REGIONS.md`, `03_CITIES_AND_SETTLEMENTS.md`, `25_WORLD_STATE.md` |

Module lain tetap mengikuti routing table yang ditetapkan INDEX dan dependency module masing-masing.

## 5. DEPENDENCY LOADING

Dependency module dimuat secara rekursif sampai seluruh requirement terpenuhi. Gunakan `VISITED_SET` atau ekuivalen untuk mencegah duplicate load dan infinite recursion.

## 6. STATE AUTHORITY

Jika action menyentuh state, state module yang sesuai adalah authority untuk kondisi terkini.

```text
CHARACTER_STATE → kondisi karakter
NPC_STATE       → kondisi NPC
MONSTER_STATE   → kondisi monster
WORLD_STATE     → kondisi dunia bersama
EVENT_STATE     → kondisi event persisten
```

Canon Definition/Registry adalah authority identity dan fakta Canon. Current State adalah authority kondisi saat ini.

## 7. HISTORY & ORIGIN

Untuk entity atau perubahan material, Router wajib memasukkan `30_HISTORY_SYSTEM.md` dan `31_ORIGIN_LOG.md` sebagai context persistence yang relevan.

Router tidak membuat record History/Origin; pembuatan dilakukan setelah resolution dan validation sesuai Save Pipeline.

## 8. UNKNOWN / AMBIGUOUS INTENT

Jika intent tidak dapat ditentukan secara sah:

```text
ROUTE = MINIMAL SAFE CONTEXT
OUTCOME = UNRESOLVED
```

Router tidak boleh menebak action.

## 9. INFORMATION BOUNDARY

Router harus memuat hanya information state yang sah untuk actor/resolution. Player knowledge tidak otomatis menjadi Character/NPC/Faction knowledge.

## 10. ROUTING PLAN

Output internal Router minimal:

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
- resolve Player Character identity dari authority resmi;
- load Race authority bila Race relevan;
- check Canon NPC sebelum dynamic NPC generation;
- check specific Canon Faction Registry sebelum faction generation/interpretation;
- tidak resolve outcome;
- tidak mutate state;
- tidak mengarang module/data;
- tidak melewati required dependency;
- tidak menggunakan stale module assumptions;
- menjaga unique entity identity;
- menjaga information boundary;
- menghormati `???`;
- membawa `TURN_ID` ke seluruh pipeline.

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

Jangan mengganti source yang hilang dengan asumsi.

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
