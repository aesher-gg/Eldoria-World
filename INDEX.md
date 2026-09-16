# Eldoria World — Official Canon Index

> **Repository:** `aesher-gg/Eldoria-World`  
> **Branch:** `main`  
> **Status:** Official Canon / Persistent World Source

## Repository Authority

Repository ini adalah **Official Canon + Persistent State Source** Eldoria.

```text
INDEX
  ↓
IDENTIFY RELEVANT MODULES / DATA
  ↓
FETCH SOURCE
  ↓
VALIDATE CONTEXT
  ↓
RUN SIMULATION
```

`INDEX.md` berfungsi sebagai navigator. INDEX bukan database seluruh dunia, bukan Character Save, dan bukan gameplay state.

## Current Architecture

```text
Eldoria-World/
├── INDEX.md
├── README.md
├── core/
│   ├── CORE_RULES.md
│   └── RUNTIME_TURN_MODEL.md
├── characters/
│   ├── players.md
│   ├── CHARACTER_DATA_MODEL.md
│   └── players/
├── world/
│   ├── WORLD_FOUNDATION.md
│   ├── GEOGRAPHY.md
│   ├── CIVILIZATION.md
│   ├── PEOPLES_RACES.md
│   ├── POLITICS.md
│   ├── SUPERNATURAL_MAGIC.md
│   ├── ECONOMY.md
│   ├── CREATURES_ECOLOGY.md
│   ├── FACTIONS.md
│   └── OTHER_WORLD_SYSTEMS.md
├── systems/
│   ├── TIME_AND_CALENDAR.md
│   ├── HEALTH_AND_INJURY.md
│   ├── COMBAT.md
│   └── TRAVEL_AND_MOVEMENT.md
├── state/
│   └── STATE_AND_HISTORY_MODEL.md
└── history/
```

## Core Runtime

### Core Rules

`core/CORE_RULES.md`

Memuat prinsip fundamental Eldoria: Repository authority, Player agency, Intent ≠ Result, fair simulation, no plot armor, Canon/State/History, validation, knowledge boundaries, persistence integrity, dan batas pengembangan Canon.

### Runtime Turn Model

`core/RUNTIME_TURN_MODEL.md`

Pipeline utama:

```text
BOOT / LOAD CONTEXT
↓
READ CURRENT STATE
↓
RECEIVE PLAYER MESSAGE
↓
PARSE
↓
IDENTIFY ACTION / INTENT
↓
VALIDATE
↓
RESOLVE
↓
CONSEQUENCES
↓
STATE CHANGE
↓
HISTORY
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE
```

## Character Architecture

### Player Registry

`characters/players.md`

Registry resmi Player dan Character. Registry bukan gameplay save state.

### Character Data Model

`characters/CHARACTER_DATA_MODEL.md`

Struktur data Character, termasuk Identity, Background, Origin, Physical Profile, Attributes, Abilities, Equipment, Possessions, Relationships, Starting State, Current State, Conditions, History Reference, dan Metadata.

## World Canon

### 1. World Foundation v0.1

`world/WORLD_FOUNDATION.md`

Menetapkan identitas Eldoria sebagai Medieval Fantasy persistent world yang luas, terbuka, otonom, dan berbasis konsekuensi.

Tema:

> **Dunia yang hidup, Player yang bebas, dan cerita yang lahir dari konsekuensi.**

### 2. Geography v0.1

`world/GEOGRAPHY.md`

Kerangka Geography: skala dunia, wilayah, terrain, water systems, climate/environment, resources, travel/connectivity, settlements, boundaries, mapping, knowledge boundary, dan progressive revelation.

### 3. Civilization v0.1

`world/CIVILIZATION.md`

Kerangka Civilization: settlement, urban/rural life, social organization, institutions, governance sebagai kategori konseptual, technology/material culture, infrastructure, culture/daily life, knowledge, production/exchange interface, dan perubahan peradaban.

### 4. Peoples / Races v0.1

`world/PEOPLES_RACES.md`

Kerangka Peoples/Races, sapience/sentience, biology, adaptation, culture, language, social organization, population, migration, inter-peoples relations, serta batas antara Peoples, Monsters, dan Wildlife.

World Foundation tetap menetapkan Orc, Goblin, dan kelompok serupa sebagai monster.

### 5. Politics v0.1

`world/POLITICS.md`

Kerangka Political Organization, Authority, Governance, Legitimacy, Territory/Jurisdiction, Sovereignty/Control, Law/Institutions, Leadership/Succession, Diplomacy, Conflict, Political Actors, Political Knowledge, Autonomy, dan persistence.

Politics v0.1 **tidak** menetapkan daftar kerajaan, negara, penguasa, hukum, batas wilayah, atau sistem pemerintahan universal.

### 6. Supernatural / Magic v0.1

`world/SUPERNATURAL_MAGIC.md`

Kerangka resmi Supernatural / Magic.

Prinsip utama:

- Supernatural umum dan diakui di Eldoria.
- Tidak semua individu dapat menggunakan magic.
- Supernatural tidak otomatis sama dengan magic.
- Magical potential ≠ skill ≠ mastery.
- Magic harus memiliki basis, kondisi, batas, dan konsekuensi yang sesuai.
- Magic tidak otomatis menjadi pengecualian terhadap Canon.
- Efek supernatural persisten mengikuti State & History Model.
- Resolusi magic mengikuti Runtime Turn Model.

V0.1 masih merupakan **framework**, bukan spell list atau sistem mekanik final.

Belum ditetapkan secara universal: mana pool, magic level/tier, final magic schools, spell list, cosmology/source final, named magical entities, artifacts, magical races, universal cost, atau progression system.

### 7. Economy v0.1

`world/ECONOMY.md`

Kerangka resmi Economy Eldoria: economic actors, needs/consumption, production, labor/occupation, resources, goods/services, property/ownership, exchange/trade, markets, currency/money, prices/valuation, supply/demand, wealth/distribution, credit/debt/finance, taxation/public revenue, logistics, infrastructure, regional economies, political/legal economy, Peoples/Races, supernatural effects, economic events/shocks, economic autonomy, character integration, State/History, runtime, data model, progressive development, dan integrity rules.

Economy v0.1 **tidak** menetapkan nama atau jumlah mata uang, kurs, harga, upah, pajak universal, sistem perbankan universal, daftar komoditas lengkap, pasar atau merchant tertentu, wealth tier universal, statistik ekonomi universal, atau formula harga/supply-demand universal.

### 8. Creatures / Ecology v0.1

`world/CREATURES_ECOLOGY.md`

Kerangka resmi Creatures / Ecology Eldoria sebagai fondasi untuk **Wildlife → Monsters → Habitat → Food Chain → Population → Behavior → Ecosystem → Creature–Environment Interaction → Monster Ecology → State/History → Dynamic World**.

Modul mencakup klasifikasi creature, Wildlife, Monsters, habitat, food/nutrition, food web, population, lifecycle/reproduction, behavior, territoriality/range, ecosystem, creature-environment interaction, monster ecology, creature-people interaction, domestication/taming/captivity, population dynamics, ecological events/shocks, ecological autonomy, data models, State/History, runtime, knowledge boundary, progressive development, canon boundary, dependencies, dan integrity rules.

V0.1 **tidak** menetapkan daftar creature/monster/wildlife, biology universal, habitat spesifik, population count, stat block, loot table, taming formula, atau formula ecological simulation universal.

### 9. Factions v0.1

`world/FACTIONS.md`

Kerangka resmi Factions Eldoria: definisi dan identitas faction, formation, tipe konseptual, membership/recruitment, leadership/internal structure, goals/interests/agendas, resources/capabilities, influence/power, geographic presence, internal politics, alliances/rivalries/external relations, reputation/recognition/legitimacy, economy/funding, hubungan dengan Peoples/Races, Civilization, Politics, Supernatural/Magic, Character integration, NPC/faction autonomy, faction events/change, State/History, runtime/resolution, knowledge boundary, data models, progressive development, canon boundary, dependencies, dan integrity rules.

Factions dibedakan dari Political Entity, Civilization, People/Race, Institution, Business, dan Individual. Membership, tujuan, pengaruh, sumber daya, serta hubungan faction harus memiliki dasar yang valid dan tidak boleh diasumsikan hanya untuk kebutuhan narasi.

### 10. Other World Systems v0.1

`world/OTHER_WORLD_SYSTEMS.md`

Kerangka arsitektur untuk world systems yang belum memiliki canonical module khusus. Modul ini menetapkan prinsip **domain boundary, canonical ownership, dependency, runtime integration, State/History integration, autonomous processing, inter-system interaction, knowledge boundary, time dependency, formula discipline, data model, module creation criteria, progressive development, dan integrity**.

Other World Systems **tidak** menetapkan mekanik final seperti combat, health/injury, kalender, travel formula, crafting, progression, quests, events, NPC behavior, relationships/reputation, religion, legal code, settlement management, diplomacy/war, atau formula numerik universal. Kategori tersebut hanya merupakan area potensial yang dapat dikembangkan sebagai modul tersendiri setelah audit dan penetapan Canon.

## Systems

### 1. Time & Calendar v0.1

`systems/TIME_AND_CALENDAR.md`

Canonical temporal authority Eldoria. Menetapkan representasi World Time, Calendar, Duration, Timestamp, Temporal State, time advancement, hubungan Turn dengan waktu, sequential/concurrent processes, temporal ordering, temporal uncertainty, calendar conversion, serta integrasi Runtime, State, History, Character, dan world systems lain.

Time & Calendar v0.1 **tidak** menetapkan nama/jumlah kalender, era, jumlah hari/bulan/tahun, nama hari/bulan, musim universal, durasi Turn, travel/combat/crafting/sleep duration, atau formula temporal universal. Detail tersebut harus ditetapkan secara eksplisit oleh Canon yang berwenang.

**Status:** System spesifik pertama telah ditetapkan. Time & Calendar menjadi canonical owner untuk temporal representation dan calendar rules yang telah didefinisikan.

### 2. Health & Injury v0.1

`systems/HEALTH_AND_INJURY.md`

Canonical owner untuk representasi health-state dan injury-state Eldoria, termasuk injury, wounds, conditions, symptoms, functional impact, recovery, treatment, aggravation, complications, incapacitation, death/irreversible outcomes, serta integrasi dengan Time & Calendar, Character, State/History, Runtime, Combat, Creatures, Supernatural/Magic, Environment, dan Travel.

Health & Injury v0.1 **tidak** menetapkan HP universal, damage formula, armor mitigation, severity scale universal, healing rate, treatment success rate, death threshold, disease list, anatomy universal, resurrection rules, atau formula kesehatan numerik lain. Detail tersebut harus ditetapkan secara eksplisit oleh Canon yang berwenang.

**Status:** System spesifik kedua telah ditetapkan setelah gameplay-need, dependency, dan overlap audit. Health & Injury menjadi canonical owner untuk health/injury representation dan health-state lifecycle yang telah didefinisikan.

### 3. Combat v0.1

`systems/COMBAT.md`

Canonical owner untuk **combat/conflict resolution** Eldoria. Menetapkan framework Combat State, participants, intent/objectives, action model, validation, position/context, initiative/order sebagai konsep yang bergantung pada mekanisme valid, attack/defense resolution, maneuver, retreat/escape, surrender/capture, disengagement, combat end conditions, serta integrasi dengan Health & Injury, Time & Calendar, Character, Creatures/Ecology, Supernatural/Magic, State/History, Geography, Politics, Economy, Factions, dan Runtime.

Combat v0.1 **tidak** menetapkan HP universal, attack/defense formula, damage formula, armor mitigation, initiative formula, critical-hit/dodge percentage, weapon damage table, movement speed, range bands, action points, fixed combat rounds, combat-round duration, level/tier/rank, universal morale formula, universal escape/surrender threshold, atau mekanik numerik universal lain.

Boundary utama:

```text
COMBAT
= combat/conflict resolution

HEALTH & INJURY
= health/injury state and consequences

TIME & CALENDAR
= temporal authority

STATE & HISTORY
= state/provenance/persistence structure
```

**Status:** System spesifik ketiga telah ditetapkan setelah full Canon dependency dan overlap audit. Combat menjadi canonical owner untuk combat/conflict resolution.

### 4. Travel & Movement v0.1

`systems/TRAVEL_AND_MOVEMENT.md`

Canonical owner untuk **travel/movement process dan resolusi perpindahan actor melalui ruang/wilayah** Eldoria. Modul ini mencakup Travel State, actor/movement context, origin/destination validation, route/path, terrain/environment/obstacles, movement method/transport, travel duration integration, ongoing/paused/delayed/interrupted/diverted travel, group travel, pursuit/escape, encounter/hazard context, serta integrasi dengan Health & Injury, Economy, Creatures/Ecology, Combat, Supernatural/Magic, Politics, Time & Calendar, State/History, dan Runtime.

Travel & Movement v0.1 **tidak** menetapkan movement speed, jarak universal, travel duration universal, terrain multiplier, stamina/exhaustion formula, hunger/thirst formula, encounter rate/table, hazard probability, mount/vehicle/ship speed, carrying capacity, travel cost, route-efficiency formula, teleportation/fast-travel rules, chase formula, escape threshold, atau mekanik numerik universal lain.

Boundary utama:

```text
GEOGRAPHY
= spatial facts / structure

TRAVEL & MOVEMENT
= movement process / resolution

TIME & CALENDAR
= temporal authority

HEALTH & INJURY
= health consequences

ECONOMY
= economic consequences

CREATURES / ECOLOGY
= ecological context

COMBAT
= combat/conflict resolution

STATE & HISTORY
= persistent state / provenance
```

**Status:** System spesifik keempat telah dibuat setelah gameplay-need, dependency, dan full Canon overlap audit. Travel & Movement menjadi canonical owner untuk proses travel/movement tanpa mengambil alih domain modul lain.

## State & History

`state/STATE_AND_HISTORY_MODEL.md`

Menetapkan hubungan:

```text
CANON
├── aturan / fakta resmi
STATE
├── kondisi yang berlaku sekarang
HISTORY
└── rekam kejadian / perubahan
```

State Change yang persisten harus memiliki Cause/Origin/Source yang valid dan dapat diverifikasi.

## Module Loading Principle

AI GM tidak perlu memuat seluruh repository untuk setiap tindakan. Gunakan INDEX untuk menentukan modul yang relevan, lalu fetch sumber resmi sebelum resolusi.

```text
INDEX
↓
RELEVANT MODULES / DATA
↓
FETCH
↓
VALIDATE
↓
RESOLVE
```

## Canon Development Order

Arsitektur World Canon inti telah menyelesaikan rangkaian:

```text
WORLD FOUNDATION
↓
GEOGRAPHY
↓
CIVILIZATION
↓
PEOPLES / RACES
↓
POLITICS
↓
SUPERNATURAL / MAGIC
↓
ECONOMY
↓
CREATURES / ECOLOGY
↓
FACTIONS
↓
OTHER WORLD SYSTEMS
↓
TIME & CALENDAR
↓
HEALTH & INJURY
↓
COMBAT
↓
TRAVEL & MOVEMENT
```

**Status:** Other World Systems v0.1 telah ditetapkan sebagai architecture framework. Time & Calendar v0.1, Health & Injury v0.1, Combat v0.1, dan Travel & Movement v0.1 telah dibuat setelah dependency dan overlap audit. Sistem berikutnya harus dipilih berdasarkan kebutuhan gameplay, dependency, dan audit Canon; tidak ada urutan wajib untuk semua system berikutnya.

## Canon Boundary

Jika suatu detail belum didefinisikan dalam Canon resmi, perlakukan sebagai `Undefined / Unknown`.

```text
UNDEFINED CANON
≠
PERMISSION TO INVENT
```

Specific world lore, mechanics, entities, locations, laws, cultures, magic systems, economies, creatures, factions, dan rules hanya menjadi Canon setelah ditetapkan secara resmi melalui Repository.
