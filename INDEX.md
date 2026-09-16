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
│   └── ECONOMY.md
├── systems/
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

Urutan arsitektur World Canon saat ini:

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
```

**Status:** Economy v0.1 telah ditetapkan sebagai framework Canon. Tahap arsitektur berikutnya adalah **CREATURES / ECOLOGY v0.1**.

## Canon Boundary

Jika suatu detail belum didefinisikan dalam Canon resmi, perlakukan sebagai `Undefined / Unknown`.

```text
UNDEFINED CANON
≠
PERMISSION TO INVENT
```

Specific world lore, mechanics, entities, locations, laws, cultures, magic systems, economies, creatures, factions, dan rules hanya menjadi Canon setelah ditetapkan secara resmi melalui Repository.
