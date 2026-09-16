# Eldoria World — INDEX

> **Official Entry Point for AI Game Master**
> **Repository:** `aesher-gg/Eldoria-World`
> **Branch:** `main`
> **World:** Eldoria
> **Genre:** Medieval Fantasy

---

## 1. Repository Authority

Repository ini adalah **Official Canon + Persistent State Source** Eldoria.

```text
REPOSITORY
   ↓
OFFICIAL CANON
   +
PERSISTENT STATE
```

AI GM wajib menggunakan repository sebagai sumber utama untuk Canon dan State yang tersedia.

Conversation / narrative response tidak otomatis menjadi Canon atau persistent State.

---

## 2. How to Use This INDEX

INDEX adalah entry point navigasi, bukan seluruh World Database, bukan Character Save, dan bukan gameplay State.

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

AI GM tidak boleh menganggap informasi yang belum dimuat sebagai Canon yang telah diverifikasi.

---

## 3. Core Architecture

```text
CANON
   ↓
REGISTRY
   ↓
STATE
   ↓
RUNTIME
   ↓
INTERACTION
   ↓
PERSISTENCE
```

Authority:

```text
ADMIN
  └── Repository / Canon

AI GM
  └── Simulation / Resolution / NPC / World / Events

PLAYER
  └── Character decisions / intent
```

---

## 4. Core Modules

### Core Rules

`core/CORE_RULES.md`

Canonical rules for:

- Repository authority;
- Player agency;
- Intent ≠ Result;
- fair simulation;
- Canon / State / History;
- State Change integrity;
- knowledge boundaries;
- world autonomy;
- unknown / undefined handling;
- persistence integrity;
- runtime principles.

### Runtime Turn Model

`core/RUNTIME_TURN_MODEL.md`

Canonical runtime sequence:

```text
LOAD
↓
READ CURRENT STATE
↓
PARSE PLAYER MESSAGE
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
PERSIST
↓
VERIFY
↓
RESPONSE
```

---

## 5. Character Modules

### Player Registry

`characters/players.md`

Official Player / Character registry.

Important:

- registry ≠ gameplay save;
- character must be registered/approved before active play;
- detailed character data belongs to individual character files.

### Character Data Model

`characters/CHARACTER_DATA_MODEL.md`

Canonical structure for Character / NPC data model, including identity, background, origin, attributes, abilities, equipment, relationships, Starting State, Current State, conditions, and history references.

---

## 6. World Canon

### World Foundation

`world/WORLD_FOUNDATION.md`

Core identity, scale, tone, player freedom, world autonomy, peoples/creatures distinction, technology, and supernatural boundary.

### Geography

`world/GEOGRAPHY.md`

Canonical geographic structure, terrain, environment, resources, connectivity, settlements, barriers, mapping, and geographic knowledge boundaries.

### Civilization

`world/CIVILIZATION.md`

Canonical framework for settlement, urbanization, institutions, governance concepts, infrastructure, technology/material culture, culture, education, production/exchange interfaces, and civilization change.

### Peoples / Races

`world/PEOPLES_RACES.md`

Canonical framework for sentient peoples, biology, adaptation, culture, language, demography, relations, and distinction from monsters/wildlife.

### Politics

`world/POLITICS.md`

Canonical owner for political organization, authority, governance, jurisdiction, sovereignty/control, law/institutions, leadership/succession, diplomacy, and political relations.

### Supernatural / Magic

`world/SUPERNATURAL_MAGIC.md`

Canonical framework for supernatural ontology, sources, access, manifestation, rules, limits, costs, risks, failure, learning, magical items, detection/countermeasures, and supernatural interaction.

### Economy

`world/ECONOMY.md`

Canonical owner for economic actors, production, labor, resources, goods/services, ownership, exchange, markets, currency, prices, supply/demand, wealth, credit/debt, taxation, logistics, and economic change.

### Creatures / Ecology

`world/CREATURES_ECOLOGY.md`

Canonical owner for wildlife, monsters, habitat, food webs, populations, lifecycle, behavior, territoriality, ecosystem interaction, monster ecology, domestication/taming context, and ecological processes.

### Factions

`world/FACTIONS.md`

Canonical owner for faction formation, membership, leadership, goals, resources, influence, presence, internal politics, alliances/rivalries, reputation/recognition/legitimacy, and faction relations.

### Other World Systems

`world/OTHER_WORLD_SYSTEMS.md`

Architecture framework for identifying and creating future world systems without duplicating canonical ownership.

---

## 7. World Systems

### System #01 — Time & Calendar

`systems/TIME_AND_CALENDAR.md`

Canonical temporal authority for World Time, Calendar, Duration, Timestamp, Temporal State, Time Advancement, turn-time integration, temporal ordering, and temporal uncertainty.

### System #02 — Health & Injury

`systems/HEALTH_AND_INJURY.md`

Canonical owner for health-state and injury-state representation, conditions, wounds, recovery, treatment, complications, incapacitation, death/irreversible outcomes, and health consequences.

### System #03 — Combat

`systems/COMBAT.md`

Canonical owner for combat/conflict resolution, participants, actions, validation, position/context, attack/defense resolution, maneuvers, retreat/escape/pursuit, surrender/capture, combat end conditions, and combat consequences.

### System #04 — Travel & Movement

`systems/TRAVEL_AND_MOVEMENT.md`

Canonical owner for movement/travel process and resolution, while Geography remains owner of geographic facts and Time remains temporal authority.

### System #05 — NPC Behavior & Agency

`systems/NPC_BEHAVIOR_AND_AGENCY.md`

Canonical owner for NPC decision-making, agency, motivation, goals, priorities, perception, available information, beliefs and uncertainty, action candidate selection, autonomous behavior, plans, reactions, knowledge updates, and NPC integration with other world systems.

Boundary:

```text
NPC BEHAVIOR
= decision / agency / action selection

OTHER SYSTEMS
= domain-specific action resolution
```

NPC Behavior does not replace Character Data, Factions, Politics, Economy, Creatures/Ecology, Travel, Combat, Health, Time, or State/History authority.

No universal NPC numerical formula, decision probability, personality score, simulation tick, behavior frequency, or quantitative fallback is defined by v0.1.

### System #06 — Relationships

`systems/RELATIONSHIPS.md`

Canonical owner for relationship state, relationship lifecycle, relationship formation/change, relationship consequences, relationship context, and relationship integration with NPCs, characters, factions, politics, economy, and other relevant domains.

Boundary:

```text
RELATIONSHIPS
= relationship state / lifecycle / relationship change

NPC BEHAVIOR
= NPC decision-making using relationship as context

FACTIONS
= faction structure / membership / faction relations

POLITICS
= political authority / governance / political relations

ECONOMY
= economic processes / transactions / ownership

STATE & HISTORY
= state / provenance / persistence
```

No universal relationship score, social probability, affection/trust/loyalty formula, relationship decay formula, or quantitative fallback is defined by v0.1.

---

## 8. State & History

`state/STATE_AND_HISTORY_MODEL.md`

Canonical structure for:

- Current State;
- State Snapshot;
- State Change;
- provenance;
- History;
- world state;
- character state;
- NPC / faction / location state;
- correction records;
- persistence integrity.

---

## 9. History

`history/`

Persistent event/history records are stored here as the repository develops.

History must preserve provenance and must not become an implicit source of new rules.

---

## 10. Canonical Ownership Map

```text
WORLD FOUNDATION
→ world identity / fundamental constraints

GEOGRAPHY
→ geographic facts / structure

CIVILIZATION
→ settlements / institutions / civilization processes

PEOPLES / RACES
→ sentient peoples / biology / culture / demography

POLITICS
→ authority / governance / jurisdiction / political relations

SUPERNATURAL / MAGIC
→ supernatural / magical domain

ECONOMY
→ economic processes / exchange / resources / markets

CREATURES / ECOLOGY
→ creature biology / ecology / ecological behavior

FACTIONS
→ organized groups / membership / faction relations

TIME & CALENDAR
→ temporal authority

HEALTH & INJURY
→ health / injury state and consequences

COMBAT
→ combat / conflict resolution

TRAVEL & MOVEMENT
→ movement / travel resolution

NPC BEHAVIOR & AGENCY
→ sentient NPC decision-making / agency / action selection

RELATIONSHIPS
→ relationship state / lifecycle / relationship change

STATE & HISTORY
→ state / provenance / persistence
```

Principle:

```text
ONE CANONICAL OWNER
        ↓
CLEAR DEPENDENCIES
        ↓
NO SILENT DUPLICATION
```

---

## 11. Runtime Loading Principle

AI GM should not blindly load every file for every action.

Use:

```text
INDEX
↓
RELEVANT MODULE IDENTIFICATION
↓
SOURCE FETCH
↓
CONTEXT VALIDATION
↓
ACTION / EVENT RESOLUTION
```

NPC-related processing should additionally use:

```text
NPC CURRENT STATE
↓
NPC KNOWLEDGE
↓
GOALS / MOTIVATIONS
↓
CONTEXT / CONSTRAINTS
↓
NPC BEHAVIOR & AGENCY
↓
RELEVANT RESOLUTION SYSTEM
```

Relationship-related processing should additionally use:

```text
CURRENT RELATIONSHIP STATE
↓
RELEVANT ACTOR / ENTITY CONTEXT
↓
RELEVANT ACTION / EVENT
↓
RELATIONSHIP RESOLUTION
↓
VALIDATED RELATIONSHIP STATE CHANGE
```

---

## 12. Development Status

Current Canon systems:

```text
🟢 #01 TIME & CALENDAR
🟢 #02 HEALTH & INJURY
🟢 #03 COMBAT
🟢 #04 TRAVEL & MOVEMENT
🟢 #05 NPC BEHAVIOR & AGENCY
🟢 #06 RELATIONSHIPS
```

Future systems remain undefined until separately designed, audited, canonized, integrated, and verified.

Potential future domains listed by architecture framework are not automatically Canon systems.

---

## 13. Integrity Rules

- Repository is the Official Canon + Persistent State Source.
- Do not invent undefined Canon.
- Do not convert Unknown / Undefined into fallback values.
- Do not duplicate canonical ownership.
- Do not treat narrative as automatic Canon or State.
- Intent ≠ Result ≠ State Change.
- Player agency must be preserved.
- NPC agency must be grounded in valid context.
- NPC Knowledge ≠ Player Knowledge ≠ World Canon.
- Autonomous processing requires a valid basis.
- System-specific resolution must use the canonical owner.
- Persistent State Change requires validation and provenance.
- Persistence must be verified before being claimed.
- Relationship State must use the canonical Relationships system when relationship data is relevant.

---

## 14. Future System Selection

There is no mandatory order for all future systems.

Selection should follow:

```text
IDENTIFY WORLD NEED
↓
CHECK EXISTING CANON OWNER
↓
AUDIT OVERLAP
↓
DEFINE NEW SYSTEM IF NECESSARY
↓
INTEGRATE
↓
VERIFY
```

A future system should only be created when its domain, rules, data model, lifecycle, runtime resolution, dependencies, or integrity requirements justify a separate canonical owner.
