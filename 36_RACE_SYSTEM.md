# ELDORIA WORLD — RACE SYSTEM

> **Module:** 36 — Race System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Authority:** Admin Canon untuk identity/definition ras; runtime modules untuk state dan simulation

## 1. Purpose

Race System mendefinisikan framework ras Eldoria sebagai fondasi yang menghubungkan biological identity, origin, history, migration, population, geography, culture, character, NPC, faction, dan world interaction.

Module ini adalah **framework**, bukan daftar ras final. Ras resmi hanya berasal dari `races/CANON_REGISTRY.md`.

## 2. Core Causal Model

```text
RACE
↓
ORIGIN / HISTORY
↓
MIGRATION / SETTLEMENT
↓
POPULATION DISTRIBUTION
↓
REGION / CULTURAL CONTEXT
↓
KINGDOM / FACTION
↓
NPC / CHARACTER
↓
RELATIONSHIP / CONFLICT / COOPERATION
```

Hubungan ini bersifat contextual dan historis; ras tidak menentukan outcome politik atau perilaku individual secara otomatis.

## 3. Race Authority

```text
races/CANON_REGISTRY.md
        ↓
CANON RACE DEFINITION
        ↓
Character / NPC / Population / Faction / World State
```

Admin berwenang menetapkan, mengubah, atau menghapus definisi Canon.

AI GM tidak boleh menciptakan ras Canon baru, mengubah identity ras, atau mengubah lore Canon melalui narrative atau dynamic generation.

## 4. Race Identity

Setiap ras Canon memiliki stable identity:

```text
RACE_CANON_ID
NAME
CLASSIFICATION
DESCRIPTION
ORIGIN
HISTORY
LIFESPAN / AGING MODEL
BIOLOGICAL TRAITS
INNATE CAPABILITIES
HABITAT / HISTORICAL DISTRIBUTION
CULTURAL VARIATION BOUNDARIES
CANON_ORIGIN
```

Field yang belum ditentukan = `???`.

## 5. Biology & Innate Traits

Ras dapat memiliki perbedaan biologis, sensory profile, lifecycle, lifespan, physical traits, atau innate capability bila ditetapkan Canon.

Innate capability bukan free progression. Kemampuan yang membutuhkan skill, training, class, magic, equipment, atau progression tetap mengikuti module terkait.

Race tidak otomatis menentukan:

- alignment,
- morality,
- intelligence,
- personality,
- profession,
- faction loyalty,
- atau outcome.

## 6. Aging & Lifecycle

Aging dan lifecycle ras ditentukan oleh Canon Race Definition bila tersedia.

Tidak boleh ada universal lifespan atau aging multiplier yang ditebak.

Character/NPC age harus konsisten dengan race definition dan state ketika data tersebut relevan.

## 7. Population Model

Race System menyediakan parameter ras untuk Population Model.

Population Model dapat merepresentasikan:

```text
TOTAL POPULATION
RACE DISTRIBUTION
SETTLEMENT DISTRIBUTION
MIGRATION PRESSURE
DEMOGRAPHIC / ROLE DISTRIBUTION
```

Tidak semua individu harus memiliki record.

Persentase, jumlah, atau dominasi ras tidak boleh ditebak jika belum ditetapkan oleh Canon atau generated population state yang sah.

## 8. Migration & Settlement

Migrasi dapat dipengaruhi oleh:

- sejarah,
- perang,
- ekonomi,
- keamanan,
- lingkungan,
- perdagangan,
- keluarga/komunitas,
- kebijakan faction/kingdom,
- displacement,
- dan faktor sah lainnya.

Ras tidak otomatis terikat pada satu kingdom atau satu habitat. Distribusi harus memiliki dasar geografis, historis, ekologis, sosial, atau population model yang relevan.

## 9. Culture

Race dan culture harus dibedakan.

```text
RACE ≠ CULTURE
RACE ≠ KINGDOM
RACE ≠ FACTION
```

Satu ras dapat memiliki beberapa budaya, bahasa, komunitas, faction, atau identitas politik. Satu kingdom juga dapat memiliki beberapa ras.

Canon boleh menetapkan cultural tendencies atau historical patterns, tetapi tidak boleh mengubahnya menjadi determinisme individual.

## 10. Character Integration

Player Character menggunakan race hanya jika race tersebut ditetapkan dalam Character Record oleh Admin berdasarkan input Player dan Canon.

AI GM tidak boleh memilih atau mengganti ras Player Character secara otomatis.

Race menjadi bagian dari Character identity/state bila schema Character menetapkannya sebagai field relevan.

## 11. NPC Integration

NPC dapat memiliki race yang berasal dari:

```text
CANON NPC RECORD
atau
VALID DYNAMIC NPC GENERATION
```

Dynamic NPC tidak boleh menggunakan ras yang tidak sah menurut Canon Registry.

Race tidak menentukan personality, loyalty, goals, atau outcome NPC secara otomatis.

## 12. Monster Boundary

Monster Species/Type mengikuti `14_MONSTER_ECOSYSTEM.md` dan Monster Canon Registry.

Race System tidak boleh mencampur identity ras humanoid/people dengan Monster Canon tanpa definisi Canon yang eksplisit.

Jika suatu entity memiliki klasifikasi yang ambigu, statusnya `???` sampai authority yang sah tersedia.

## 13. Faction & Political Integration

Faction dan kingdom dapat memiliki:

- demographic composition,
- migration history,
- racial representation,
- cultural relationships,
- policies,
- tensions,
- alliances,
- atau conflicts

bila didukung Canon/state.

Race tidak otomatis menentukan political allegiance.

## 14. Relationship & Conflict

Race dapat menjadi salah satu context dalam relationship atau conflict, tetapi outcome tetap berasal dari history, evidence, goals, knowledge, resources, policy, event, dan resolution yang relevan.

Tidak boleh ada universal hostility/friendship tanpa source Canon atau state.

## 15. Mixed Race / Subrace

Mixed race, hybrid lineage, subrace, clan, ethnicity, atau cultural subgroup hanya sah jika mekanisme/definition Canon mengizinkannya.

Jangan menganggap semua ras dapat bercampur atau semua subrace merupakan ras terpisah tanpa Canon definition.

## 16. Dynamic Generation

AI GM boleh memilih ras untuk Dynamic NPC/Population hanya dari Canon Registry dan berdasarkan context yang relevan.

Generation dapat menggunakan:

```text
LOCATION
REGION
SETTLEMENT
POPULATION MODEL
MIGRATION CONTEXT
CULTURAL CONTEXT
FACTION
HISTORY
EVENT
GENERATION PARAMETERS / SEED
```

Generation tidak boleh:

- membuat Canon Race baru,
- mengubah Canon definition,
- mengubah sejarah resmi,
- atau memaksakan racial distribution yang tidak didukung source.

## 17. State & Persistence

Race definition adalah Canon layer.

Race-related current condition seperti lokasi, status, affiliation, relationship, migration status, atau demographic state berada pada state layer yang relevan.

Material changes mengikuti:

```text
CAUSE
→ RESOLUTION
→ STATE DELTA
→ VALIDATION
→ HISTORY + ORIGIN
→ ATOMIC PERSISTENCE
```

## 18. Information Boundary

Pengetahuan mengenai race, lineage, traits, ancestry, population, atau cultural identity tidak otomatis diketahui Character/NPC/Player.

Disclosure mengikuti Information State dan valid information mechanism.

## 19. Canon Safety

`???` berarti Unknown / Unresolved.

AI GM tidak boleh mengisi data race yang belum Canon dengan asumsi.

Player input tentang ras adalah input Character Registration, bukan perubahan Race Canon.

## 20. Dependencies

Core context:

`01_WORLD_OVERVIEW` · `02_REALMS_AND_REGIONS` · `03_CITIES_AND_SETTLEMENTS` · `05_CHARACTER_SYSTEM` · `06_ATTRIBUTES` · `16_NPC_SYSTEM` · `25_WORLD_STATE`

Integration:

`19_FACTION_SYSTEM` · `20_REPUTATION` · `26_CHARACTER_STATE` · `27_NPC_STATE` · `28_MONSTER_STATE` · `30_HISTORY_SYSTEM` · `31_ORIGIN_LOG` · `32_MODULE_ROUTER` · `33_ACTION_RESOLVER` · `34_STATE_VALIDATOR` · `35_SAVE_PIPELINE`

Authority:

`races/CANON_REGISTRY.md`

## 21. Final Principle

> **Race adalah Canon identity yang menjadi salah satu fondasi sejarah, migrasi, populasi, wilayah, budaya, dan hubungan dunia; tetapi ras tidak menentukan kepribadian atau outcome individual secara otomatis.**
