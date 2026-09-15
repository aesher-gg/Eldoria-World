# ELDORIA WORLD — MODULE ROUTER

> **Module:** 32 — Module Router
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Runtime module selection and loading contract

## 0. PURPOSE

Module Router menentukan module, state, history, dan origin yang wajib dimuat untuk satu Turn Transaction berdasarkan intent, entity yang terlibat, dan konsekuensi yang mungkin disentuh.

Router **tidak menentukan outcome** dan tidak mengubah state. Router hanya menghasilkan Routing Plan untuk Action Resolver.

## 1. INPUT

Router menerima:

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

State yang relevan ditentukan dari actor, target, lokasi, action, dan konsekuensi yang dapat disentuh.

Module yang pernah dimuat pada turn sebelumnya tidak dianggap masih authoritative.

## 3. ROUTING PRINCIPLE

Router menggunakan **domain yang benar-benar disentuh oleh action**, bukan sekadar pencocokan kata pada Player Message.

Contoh:

| Intent | Module utama | Module pendukung |
|---|---|---|
| Attack | 13 Combat | 12 Vitality, 10 Equipment, 26/27/28 State, 30/31 |
| Travel | 02 Regions, 25 World State | 12 Vitality, 26 Character State, 18 Events, 30/31 |
| Trade | 11 Economy | 10 Equipment, 16 NPC, 20 Reputation, 26/27 State |
| Craft | 21 Crafting | 08 Skills, 10 Equipment, 11 Economy, 26 State |
| Alchemy | 22 Alchemy | 08 Skills, 09 Magic, 10 Equipment, 12 Vitality, 26 State |
| Magic | 09 Magic | 08 Skills, 10 Equipment, 12 Vitality, 26 State |
| Quest | 17 Quest | 16 NPC, 19 Faction, 18 Events, 20 Reputation, state modules |
| Faction action | 19 Faction | 04 Factions, 16 NPC, 18 Events, 20 Reputation |
| Companion | 24 Pets/Companions | 23 Party, 12 Vitality, 13 Combat, 26/27/28 State |
| Party | 23 Party | relevant member state, 13 Combat or 02 Travel when applicable |
| Monster/ecology | 14 Monster Ecosystem | 28 Monster State, 12/13, 15 Loot when applicable |
| Loot | 15 Loot | 10 Equipment, 11 Economy, source state, 30/31 |
| World event | 18 World Events | 25 World State, affected entity states, 30/31 |
| Reputation | 20 Reputation | 04 Factions, 16 NPC, 26 Character State |

Tabel adalah panduan domain, bukan daftar module yang selalu wajib dimuat seluruhnya. Konsekuensi aktual menentukan load final.

## 4. DEPENDENCY LOADING

Dependency module dimuat secara rekursif sampai seluruh requirement terpenuhi.

Runtime harus menggunakan mekanisme `VISITED_SET` atau ekuivalen untuk:

- mencegah duplicate load,
- mencegah infinite recursion,
- menangani referensi silang,
- dan menjaga dependency graph tetap deterministik.

Dependency reference tidak memberi module hak untuk mengubah authority layer module lain.

## 5. STATE AUTHORITY

Jika action menyentuh state, state module yang sesuai adalah authority untuk kondisi terkini.

Contoh:

```text
CHARACTER_STATE → kondisi karakter
NPC_STATE       → kondisi NPC
MONSTER_STATE   → kondisi monster
WORLD_STATE     → kondisi dunia bersama
EVENT_STATE     → kondisi event persisten
```

Narrative tidak boleh menggantikan state.

## 6. HISTORY & ORIGIN

Untuk entity atau perubahan material, Router wajib memasukkan:

```text
30_HISTORY_SYSTEM.md
31_ORIGIN_LOG.md
```

sebagai context persistence yang relevan.

Router tidak membuat record History/Origin; pembuatan dilakukan setelah resolution dan validation sesuai Save Pipeline.

## 7. UNKNOWN / AMBIGUOUS INTENT

Jika intent tidak dapat ditentukan secara sah:

```text
ROUTE = MINIMAL SAFE CONTEXT
OUTCOME = UNRESOLVED
```

Router tidak boleh menebak action hanya untuk menghindari `???`.

Jika informasi tambahan diperlukan, Action Resolver menangani kebutuhan klarifikasi/resolution tanpa membuat fakta baru.

## 8. ENTITY DISCOVERY

Jika Player merujuk entity yang belum memiliki ID persisten:

1. cek state persisten yang relevan;
2. cek History/Origin bila diperlukan;
3. gunakan dynamic generation hanya jika module mengizinkan dan resolution memerlukannya;
4. generated entity material harus mendapat identity, Origin, Generation Data, State, dan History.

Jangan membuat entity pengganti jika entity persisten sudah ditemukan.

## 9. TIME-AWARE ROUTING

Jika action mengubah atau bergantung pada waktu, Router wajib memuat module/state waktu yang relevan.

Action yang memakan waktu harus dirutekan sehingga time delta diproses sebelum resolution lanjutan yang bergantung pada waktu tersebut.

## 10. INFORMATION BOUNDARY

Router harus memuat hanya information state yang sah untuk actor/resolution.

```text
WORLD KNOWLEDGE
CHARACTER KNOWLEDGE
NPC KNOWLEDGE
PLAYER KNOWLEDGE
```

Pengetahuan Player tidak otomatis menjadi pengetahuan Character/NPC.

## 11. ROUTING PLAN

Output internal Router minimal:

```text
TURN_ID
ROUTE_STATUS
PRIMARY_MODULES
SECONDARY_MODULES
STATE_SOURCES
HISTORY_SOURCES
ORIGIN_SOURCES
ENTITY_IDS
DEPENDENCY_GRAPH / LOAD ORDER
INFORMATION_SCOPE
TIME_SCOPE
FAILURE_REASON (jika ada)
```

Output ini adalah data runtime, bukan narrative.

## 12. ROUTER INVARIANTS

Router wajib:

- fetch/verify INDEX setiap turn;
- tidak resolve outcome;
- tidak mutate state;
- tidak mengarang module/data;
- tidak melewati required dependency;
- tidak menggunakan stale module assumptions;
- menjaga unique entity identity;
- menjaga information boundary;
- menghormati `???`;
- membawa `TURN_ID` ke seluruh pipeline.

## 13. FAILURE

Jika required module atau authoritative state tidak tersedia:

```text
ROUTE FAILURE
↓
NO RESOLUTION
↓
NO STATE CHANGE
↓
NO FALSE HISTORY / ORIGIN
```

Jangan mengganti module yang hilang dengan asumsi.

## 14. HANDOFF

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

Final principle:

> **Module Router menentukan apa yang harus dibaca; bukan apa yang harus terjadi.**
