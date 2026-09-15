# ELDORIA WORLD — NPC SYSTEM

> **Module:** 16 — NPC System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1

## 1. Purpose

Mendefinisikan NPC sebagai entitas hidup dengan identity, needs, goals, knowledge, relationships, capability, agency, dan lifecycle.

Module ini menetapkan framework dan aturan. NPC Canon disimpan sebagai data resmi repository; populasi biasa tidak perlu dikatalogkan satu per satu.

## 2. NPC Classes

Eldoria menggunakan tiga kategori operasional:

```text
CANON NPC
DYNAMIC NPC
PERSISTENT DYNAMIC NPC
```

### Canon NPC

Canon NPC adalah tokoh penting yang ditetapkan Admin sebagai penghuni/tokoh resmi dunia.

Canon NPC tidak boleh dibuat ulang secara acak jika record resminya sudah tersedia.

Pedoman minimum populasi Canon:

```text
DESA       → minimal 3 Canon NPC
KOTA       → minimal 5 Canon NPC
KERAJAAN   → minimal 10 Canon NPC
KEKAISARAN → minimal 25 Canon NPC
```

Angka tersebut adalah minimum tokoh Canon per wilayah, bukan jumlah seluruh penduduk.

### Dynamic NPC

Dynamic NPC adalah individu biasa yang dapat dimaterialisasi AI GM dari population/context ketika interaksi membutuhkannya. Mereka tidak wajib memiliki file repository sejak kemunculan pertama.

### Persistent Dynamic NPC

Dynamic NPC yang kemudian menjadi material bagi continuity dunia memperoleh stable identity dan persistence. Status ini tidak otomatis menjadikannya Canon NPC Admin.

## 3. NPC Identity

NPC persisten wajib memiliki:

```text
NPC_ID
NAME / DESIGNATION
ROLE / TYPE
NPC_CLASS = CANON | DYNAMIC_PERSISTENT
CURRENT_STATE
ORIGIN
GENERATION_DATA
HISTORY
```

Field yang belum diketahui = `???`.

## 4. Canon NPC Authority

Untuk Canon NPC, repository Canon adalah authority atas identity dan lore dasar, termasuk bila relevan:

```text
NAME
ROLE
ORIGIN
BACKGROUND
FACTION
CORE RELATIONSHIPS
CAPABILITIES
GOALS
KNOWLEDGE BOUNDARY
CANON STATUS
```

AI GM boleh mensimulasikan keputusan dan perubahan state Canon NPC, tetapi tidak boleh diam-diam mengganti identity/lore dasar atau membuat duplicate Canon NPC.

Perubahan Canon yang benar-benar mengubah world canon membutuhkan perubahan Admin Canon. Perubahan kondisi gameplay biasa menggunakan NPC State dan pipeline persistence.

## 5. NPC State

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

## 6. Agency

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

## 7. Needs & Goals

Needs adalah tekanan/kebutuhan yang memengaruhi perilaku.

Goals adalah tujuan yang ingin dicapai.

Keduanya bukan jaminan keberhasilan; outcome tetap melalui resolution.

## 8. Knowledge Boundary

NPC memiliki knowledge state sendiri.

NPC tidak otomatis mengetahui:

- Player knowledge,
- Character knowledge,
- hidden world state,
- identitas tersembunyi,
- atau informasi yang belum diperoleh.

Informasi diperoleh melalui observation, communication, rumor, records, faction network, discovery, atau mekanisme sah lain.

## 9. Dynamic Generation

Dynamic NPC dapat dihasilkan berdasarkan context seperti:

```text
LOCATION
SETTLEMENT
POPULATION MODEL
FACTION
ROLE / NEED
WORLD STATE
EVENT CONTEXT
GENERATION SEED / PARAMETERS
```

Generator harus menghormati Canon NPC yang sudah ada. Jika Player berinteraksi dengan tokoh Canon yang relevan, fetch record Canon terlebih dahulu daripada membuat pengganti.

Jika Dynamic NPC menjadi material, generator harus memberi stable identity, origin, generation data, current state, dan history sesuai persistence requirement.

## 10. Population Model

Population tidak sama dengan NPC database.

Settlement dapat memiliki populasi sangat besar tanpa setiap individu memiliki record repository.

Population model menentukan distribusi/karakteristik umum yang relevan, sedangkan individual Dynamic NPC dimaterialisasi hanya ketika diperlukan oleh simulation.

## 11. Persistence Threshold

NPC background yang tidak material dapat direpresentasikan secara abstrak.

NPC harus menjadi persistent entity ketika memiliki dampak material melalui interaction, quest, relationship, transaction, combat, faction activity, information, atau konsekuensi dunia.

Persistent Dynamic NPC tetap dibedakan dari Canon NPC Admin.

## 12. Lifecycle

NPC dapat mengalami lifecycle seperti:

```text
CREATED / BORN
→ ACTIVE
→ INACTIVE / MISSING / CAPTURED
→ DEAD / RETIRED
```

State aktual menentukan lifecycle; tidak ada automatic resurrection atau replacement tanpa mekanisme sah.

## 13. World Interaction

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

## 14. NPC Actions

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

## 15. Anti-Plot Behavior

AI GM dilarang membuat NPC:

- otomatis membantu Player,
- otomatis percaya Player,
- otomatis memberikan reward,
- menjadi bodoh demi plot,
- mengetahui informasi tanpa source,
- atau mengubah tujuan tanpa sebab.

Perubahan perilaku harus memiliki cause yang relevan.

## 16. Information & Narrative

Narrative hanya mengungkap NPC berdasarkan informasi yang Character dapat akses.

Internal NPC state dapat tetap hidden jika belum diketahui.

## 17. Canon Safety

Canon NPC adalah data resmi Admin. Dynamic NPC tidak boleh dipromosikan menjadi Canon hanya melalui narasi AI GM.

Jika Dynamic NPC menjadi penting, ia dapat menjadi **Persistent Dynamic NPC** melalui persistence pipeline tanpa otomatis mengubah Canon.

## 18. Dependencies

`03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS` + `05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` + `09_MAGIC_SYSTEM` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY` + `12_VITALITY_SURVIVAL`.

Integrasi: `14_MONSTER_ECOSYSTEM`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `25_WORLD_STATE`, `27_NPC_STATE`, `32_MODULE_ROUTER`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 19. Final Principle

> **Canon NPC menyediakan tokoh penting resmi dunia; Population Model menyediakan skala populasi; Dynamic NPC mengisi kehidupan sehari-hari; Persistence menjaga kontinuitas tanpa memaksa seluruh populasi menjadi database individual.**
