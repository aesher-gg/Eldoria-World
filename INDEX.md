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
STATE VALIDATION
   ↓
PERSISTENCE
   ↓
VERIFICATION
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

Core infrastructure boundary:

```text
STATE & HISTORY
= State / History / State Change / Origin / Source semantics

STATE VALIDATION
= integrity gate for State Changes

PERSISTENCE
= apply / save validated State and History

VERIFICATION
= confirm persistence result
```

Verification adalah stage/function dalam Persistence Architecture, bukan canonical owner atau modul ketiga.

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
STATE VALIDATION
↓
APPLY / HISTORY
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE
```

### State Validation

`core/STATE_VALIDATION.md`

Canonical integrity layer for:

- State Change validation;
- Current State consistency;
- provenance validation;
- temporal consistency;
- Canon compatibility;
- Change Set / multi-entity consistency;
- conflict detection;
- Unknown / Undefined protection;
- validation status.

Boundary:

```text
RESOLUTION
= what happened

STATE VALIDATION
= whether the resulting State Change can be applied validly
```

State Validation does not own State/History semantics or domain-specific resolution.

### Persistence

`core/PERSISTENCE.md`

Canonical save/persistence architecture for:

- validated Change Set application;
- Current State persistence;
- History persistence;
- provenance preservation;
- persistence lifecycle;
- failure handling;
- recovery/correction workflow;
- duplicate-application protection;
- verification of persisted results.

Boundary:

```text
STATE VALIDATION
= is this change valid?

PERSISTENCE
= can this valid change be applied/saved?

VERIFICATION
= did persistence actually produce the expected result?
```

Verification is part of the Persistence architecture.

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

NPC Behavior does not replace Character Data, Factions, Politics, Economy, Creatures/Ecology, Travel, Combat, Health, Time, Relationships, Reputation, or State/History authority.

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

REPUTATION
= how a subject is regarded by a specific audience/context

STATE & HISTORY
= state / provenance / persistence
```

No universal relationship score, social probability, affection/trust/loyalty formula, relationship decay formula, or quantitative fallback is defined by v0.1.

### System #07 — Reputation

`systems/REPUTATION.md`

Canonical owner for reputation state, reputation lifecycle, reputation formation/change, audience and context, reputation evidence/provenance, information flow, reputation consequences, and integration with NPCs, factions, politics, economy, relationships, and other relevant domains.

Boundary:

```text
REPUTATION
= bagaimana actor / entity dipandang oleh audience tertentu
  dalam konteks tertentu

RELATIONSHIPS
= relationship state / lifecycle / relationship change

NPC BEHAVIOR
= NPC decision-making menggunakan reputation sebagai context

FACTIONS
= faction structure / membership / faction relations

POLITICS
= authority / governance / jurisdiction / legitimacy

ECONOMY
= economic processes / transactions / ownership

STATE & HISTORY
= state / provenance / persistence
```

Reputation dapat bersifat local, group-specific, actor-specific, contextual, asymmetric, dan time-dependent.

No universal reputation score, rating, multiplier, threshold, probability, decay formula, automatic reaction, global reputation ranking, atau quantitative fallback is defined by v0.1.

Reputation is not objective moral truth and does not automatically create relationship, membership, authority, legitimacy, ownership, wealth, transaction, alliance, hostility, or other state.

### System #08 — Law / Legal Procedures

`systems/LAW.md`

Canonical owner for legal rules, legal applicability, jurisdiction-specific legal procedures, legal status, adjudication, enforcement, and legal consequences.

Boundary:

```text
POLITICS
= authority / governance / political jurisdiction

LAW
= legal rules / legal applicability / legal procedures / legal status
  / adjudication / enforcement / legal consequences

STATE & HISTORY
= persistent legal state / provenance / history / persistence
```

Law does not replace Economy, NPC Behavior & Agency, Relationships, Reputation, Combat, Health & Injury, Time & Calendar, Politics, or State & History.

Legal rules require a valid jurisdictional and canonical basis. A political jurisdiction does not automatically imply a universal legal rule.

Important legal distinctions:

```text
FACT
≠ CLAIM
≠ ALLEGATION
≠ RUMOR
≠ EVIDENCE
```

An allegation or claim does not automatically establish a legal violation. Legal resolution depends on applicable rules, jurisdiction, relevant facts/evidence, procedure, authority, and context.

No universal crime list, punishment list, fine amount, prison duration, evidence score, guilt probability, sentence formula, legal severity score, court success probability, corruption probability, limitation period, arrest rule, legal age, legal code, court structure, or quantitative legal fallback is defined by v0.1.

Legal processing follows the relevant legal system's procedures and preserves NPC/faction agency in enforcement. Narrative alone does not create legal state.

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

LAW
→ legal rules / applicability / procedures / legal status / adjudication / enforcement

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

REPUTATION
→ reputation state / audience context / reputation formation and change

STATE & HISTORY
→ state / provenance / persistence structure

STATE VALIDATION
→ State Change integrity / consistency validation

PERSISTENCE
→ validated State/History application, storage, failure handling, and verification
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
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
```

NPC-related processing should additionally use:

```text
NPC CURRENT STATE
↓
NPC KNOWLEDGE
↓
GOALS / MOTIVATIONS
↓
RELEVANT RELATIONSHIP / REPUTATION CONTEXT
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

Reputation-related processing should additionally use:

```text
CURRENT REPUTATION STATE
↓
RELEVANT SUBJECT / AUDIENCE / CONTEXT
↓
RELEVANT ACTION / EVENT / INFORMATION
↓
REPUTATION RESOLUTION
↓
VALIDATED REPUTATION STATE CHANGE
```

Legal-related processing should additionally use:

```text
CURRENT STATE
↓
RELEVANT ACTION / EVENT / CLAIM
↓
LEGAL RELEVANCE?
├── NO → CONTINUE RELEVANT SYSTEM
└── YES
     ↓
  JURISDICTION
     ↓
  APPLICABLE LEGAL RULES
     ↓
  LEGAL PROCEDURE / RESOLUTION
     ↓
  LEGAL RESULT
     ↓
  CONSEQUENCES / ENFORCEMENT
     ↓
  VALIDATED STATE CHANGE
     ↓
  HISTORY
     ↓
  PERSISTENCE
     ↓
  VERIFY
```

Legal resolution must not silently take ownership of non-legal domains. Domain-specific consequences continue through their canonical systems.

---

## 12. Development Status

Current Canon infrastructure:

```text
🟢 CORE RULES
🟢 RUNTIME / TURN MODEL
🟢 STATE VALIDATION
🟢 PERSISTENCE
```

Current Canon systems:

```text
🟢 #01 TIME & CALENDAR
🟢 #02 HEALTH & INJURY
🟢 #03 COMBAT
🟢 #04 TRAVEL & MOVEMENT
🟢 #05 NPC BEHAVIOR & AGENCY
🟢 #06 RELATIONSHIPS
🟢 #07 REPUTATION
🟢 #08 LAW / LEGAL PROCEDURES
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
- State Validation must not determine gameplay resolution.
- Persistence must not repair invalid State Changes silently.
- Interdependent State Changes must preserve required atomicity/integrity.
- Persistence failure and verification failure must remain distinguishable from validation failure.
- Relationship State must use the canonical Relationships system when relationship data is relevant.
- Reputation State must use the canonical Reputation system when reputation data is relevant.
- Reputation must not be treated as universal truth or universal value.
- Legal State and legal consequences must use the canonical Law system when legal data is relevant.
- Legal applicability must be validated against jurisdiction and applicable Canon.
- Legal claims, allegations, rumors, and evidence must not be treated as equivalent.

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
