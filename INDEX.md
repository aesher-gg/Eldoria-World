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
OFFICIAL CANON + PERSISTENT STATE
```

Conversation / narrative response tidak otomatis menjadi Canon atau persistent State.

---

## 2. How to Use This INDEX

INDEX adalah entry point navigasi, bukan seluruh World Database, Character Save, atau gameplay State.

```text
INDEX
↓
IDENTIFY RELEVANT MODULES / DATA
↓
FETCH SOURCE
↓
VALIDATE CONTEXT
↓
ACTION MODEL
↓
RESOLUTION ARCHITECTURE
↓
DOMAIN / EVENT / AUTONOMOUS PROCESS
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
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
ACTION MODEL
↓
RESOLUTION ARCHITECTURE
↓
EVENT / AUTONOMOUS ORCHESTRATION
↓
DOMAIN SYSTEMS
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
ACTION MODEL
= struktur dan lifecycle Action

RESOLUTION ARCHITECTURE
= kontrak generic untuk menghasilkan Result

WORLD EVENT PROCESSOR
= event lifecycle / trigger / scheduling / event orchestration / chaining

NPC / FACTION SIMULATION
= autonomous NPC/Faction process orchestration

STATE & HISTORY
= State / History / State Change / Origin / Source semantics

STATE VALIDATION
= integrity gate untuk State Changes

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

Canonical rules for repository authority, Player agency, Intent ≠ Result, fair simulation, Canon / State / History, State Change integrity, knowledge boundaries, world autonomy, Unknown / Undefined handling, persistence integrity, and runtime principles.

### Runtime Turn Model

`core/RUNTIME_TURN_MODEL.md`

Canonical one-Player-Message-per-Turn runtime pipeline, termasuk jalur autonomous Event dan NPC/Faction processing.

```text
LOAD
↓
CURRENT STATE
↓
PLAYER MESSAGE / WORLD PROCESS
↓
INTENT / EVENT / AUTONOMOUS PROCESS
↓
ACTION VALIDATION
↓
RESOLUTION / EVENT ORCHESTRATION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE / NEXT PROCESS
```

### Action Model

`core/ACTION_MODEL.md`

Canonical owner for the generic Action contract, including Action identity, Actor, Intent reference, Target/Subject, Context, Parameters, Preconditions, Dependencies, sequence metadata, lifecycle/status, provenance, and handoff to Resolution.

Boundary:

```text
INTENT ≠ ACTION ≠ RESULT ≠ STATE CHANGE
```

Action Model does not own NPC decision-making, domain mechanics, State semantics, State Validation, or Persistence.

### Resolution Architecture

`core/RESOLUTION_ARCHITECTURE.md`

Canonical generic resolution contract for Resolution Request, domain routing, Resolution Result, outcome status, consequence handoff, temporal result, provenance, and State Change handoff.

Boundary:

```text
ACTION / PROCESS
↓
RESOLUTION REQUEST
↓
RELEVANT DOMAIN RESOLUTION
↓
RESULT
↓
CONSEQUENCES
```

Resolution Architecture does not define a universal gameplay formula, probability, multiplier, score, threshold, damage formula, or difficulty formula.

### World Event Processor

`core/WORLD_EVENT_PROCESSOR.md`

Canonical orchestration layer for Event lifecycle, eligibility, triggers, scheduling when required, processing, event chaining, domain handoff, consequences, and autonomous Event processing.

Boundary:

```text
EVENT
↓
WORLD EVENT PROCESSOR
↓
ACTION / RESOLUTION / DOMAIN
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
```

World Event Processor does not own Time, State/History, Action structure, generic Resolution, domain mechanics, State Validation, or Persistence.

### NPC / Faction Simulation

`core/NPC_FACTION_SIMULATION.md`

Canonical orchestration layer for autonomous NPC/Faction process eligibility, actor/process selection, context loading, invocation of NPC Behavior/Faction logic, autonomous action sequences, and reaction loops.

Boundary:

```text
NPC BEHAVIOR & AGENCY → NPC decision
FACTIONS → Faction structure/state/goals/relations
NPC / FACTION SIMULATION → autonomous orchestration
ACTION MODEL → Action representation
RESOLUTION → generic result contract
DOMAIN → domain outcome
```

No universal simulation tick, activity frequency, probability, priority score, or quantitative fallback is defined by v0.1.

### State Validation

`core/STATE_VALIDATION.md`

Canonical integrity layer for State Change and Change Set validation, Current State consistency, provenance, temporal consistency, Canon compatibility, conflict detection, multi-entity consistency, and Unknown / Undefined protection.

### Persistence

`core/PERSISTENCE.md`

Canonical save/persistence architecture for validated Change Set application, Current State and History persistence, provenance preservation, failure handling, recovery/correction, duplicate-application protection, and verification.

---

## 5. Character Modules

### Player Registry

`characters/players.md`

Official Player / Character registry. Registry ≠ gameplay save. Character must be registered/approved before active play.

### Character Data Model

`characters/CHARACTER_DATA_MODEL.md`

Canonical structure for Character / NPC data, including identity, background, origin, attributes, abilities, equipment, relationships, Starting State, Current State, conditions, and History references.

---

## 6. World Canon

```text
world/WORLD_FOUNDATION.md
world/GEOGRAPHY.md
world/CIVILIZATION.md
world/PEOPLES_RACES.md
world/POLITICS.md
world/SUPERNATURAL_MAGIC.md
world/ECONOMY.md
world/CREATURES_ECOLOGY.md
world/FACTIONS.md
world/OTHER_WORLD_SYSTEMS.md
```

Canonical ownership:

```text
WORLD FOUNDATION → world identity / fundamental constraints
GEOGRAPHY → geographic facts / structure
CIVILIZATION → settlements / institutions / civilization processes
PEOPLES / RACES → sentient peoples / biology / culture / demography
POLITICS → authority / governance / jurisdiction / political relations
SUPERNATURAL / MAGIC → supernatural / magical domain
ECONOMY → economic processes / exchange / resources / markets
CREATURES / ECOLOGY → creature biology / ecology / ecological behavior
FACTIONS → organized groups / membership / faction relations
OTHER WORLD SYSTEMS → future-system architecture / ownership discipline
```

World modules remain frameworks where their Canon has not yet defined specific names, numbers, formulas, laws, mechanics, or universal defaults.

---

## 7. World Systems

### System #01 — Time & Calendar

`systems/TIME_AND_CALENDAR.md`

Canonical temporal authority for World Time, Calendar, Duration, Timestamp, Temporal State, Time Advancement, Turn-time integration, temporal ordering, and temporal uncertainty.

### System #02 — Health & Injury

`systems/HEALTH_AND_INJURY.md`

Canonical owner for health/injury state and consequences, conditions, wounds, recovery, treatment, complications, incapacitation, and irreversible health outcomes.

### System #03 — Combat

`systems/COMBAT.md`

Canonical owner for combat/conflict resolution and combat consequences.

### System #04 — Travel & Movement

`systems/TRAVEL_AND_MOVEMENT.md`

Canonical owner for movement/travel process and resolution. Geography remains owner of geographic facts and Time remains temporal authority.

### System #05 — NPC Behavior & Agency

`systems/NPC_BEHAVIOR_AND_AGENCY.md`

Canonical owner for NPC decision-making, agency, motivation, goals, priorities, perception, available information, beliefs/uncertainty, action selection, autonomous behavior, plans, reactions, and knowledge updates.

Boundary:

```text
NPC BEHAVIOR
= decision / agency / action selection

NPC / FACTION SIMULATION
= autonomous orchestration

ACTION MODEL
= action representation

DOMAIN SYSTEMS
= domain-specific action resolution
```

No universal NPC decision formula, probability, personality score, simulation tick, or quantitative fallback is defined by v0.1.

### System #06 — Relationships

`systems/RELATIONSHIPS.md`

Canonical owner for relationship state, lifecycle, formation/change, and relationship consequences/context.

### System #07 — Reputation

`systems/REPUTATION.md`

Canonical owner for reputation state, audience/context, reputation formation/change, evidence/provenance, information flow, and reputation consequences.

### System #08 — Law / Legal Procedures

`systems/LAW.md`

Canonical owner for legal rules, applicability, jurisdiction-specific procedures, legal status, adjudication, enforcement, and legal consequences.

Important distinction:

```text
FACT ≠ CLAIM ≠ ALLEGATION ≠ RUMOR ≠ EVIDENCE
```

No universal legal code, crime list, punishment formula, sentence formula, evidence score, or quantitative legal fallback is defined by v0.1.

---

## 8. State & History

`state/STATE_AND_HISTORY_MODEL.md`

Canonical structure for Current State, State Snapshot, State Change, provenance, History, world state, character/NPC/faction/location state, correction records, and persistence structure.

Starting State remains a historical baseline. Gameplay persistence changes Current State through validated State Changes.

---

## 9. History

`history/`

Persistent event/history records. History preserves provenance and does not silently become a source of new Canon rules.

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

WORLD EVENT PROCESSOR
→ Event lifecycle / triggering / scheduling / processing / chaining / event orchestration

NPC / FACTION SIMULATION
→ autonomous NPC/Faction process orchestration

ACTION MODEL
→ generic Action structure / lifecycle / action contract

RESOLUTION ARCHITECTURE
→ generic Resolution contract / Result / domain routing

STATE & HISTORY
→ state / provenance / history structure

STATE VALIDATION
→ State Change integrity / consistency validation

PERSISTENCE
→ validated State/History application, storage, failure handling, verification
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
ACTION MODEL / EVENT PROCESSOR / AUTONOMOUS SIMULATION
↓
RESOLUTION ARCHITECTURE
↓
RELEVANT DOMAIN SYSTEM
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
```

NPC-related processing additionally uses NPC Current State, NPC Knowledge, goals/motivations, relevant relationship/reputation context, constraints, NPC Behavior & Agency, and then the relevant resolution system.

Event-related processing additionally uses Event context, trigger/eligibility information, World Event Processor, relevant Action/Resolution and domain system.

NPC/Faction autonomous processing uses NPC/Faction Simulation, then NPC Behavior & Agency or Faction logic, followed by Action/Resolution and relevant domain system.

Relationship, Reputation, and Legal processing continue through their respective canonical systems and then return to State Validation and Persistence.

---

## 12. Development Status

Current Canon infrastructure:

```text
🟢 CORE RULES
🟢 RUNTIME / TURN MODEL
🟢 ACTION MODEL
🟢 RESOLUTION ARCHITECTURE
🟢 WORLD EVENT PROCESSOR
🟢 NPC / FACTION SIMULATION
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

---

## 13. Integrity Rules

- Repository is the official Canon and persistent State source.
- One Player Message = one Turn.
- Intent ≠ Action ≠ Result ≠ State Change.
- Action validation does not guarantee success.
- Domain-specific systems retain domain resolution ownership.
- World Event Processor owns event orchestration, not domain mechanics.
- NPC / Faction Simulation owns autonomous orchestration, not NPC decision-making or Faction structure.
- No universal resolution formula is created by core infrastructure.
- Failure, blocked, delayed, interrupted, and unresolved remain distinguishable.
- Current State is the operational baseline.
- Working State is temporary and is not persistence final.
- State Changes must pass State Validation before final application.
- Interdependent Change Sets must be validated and persisted as an integrated result when required.
- Invalid, conflict, or unresolved changes are not final valid State.
- Starting State is not overwritten by normal gameplay persistence.
- History and provenance must remain traceable.
- Unknown / Undefined must not be replaced by invented defaults.
- Autonomous world changes require a valid basis.
- Autonomous processing is not a random story generator.
- No universal Event/NPC/Faction simulation tick, frequency, probability, or priority score exists in current Core v0.1.
- Narrative is not evidence of State or Persistence.
- AI GM must not claim persistence success without verification.
- Validation failure, persistence failure, and verification failure remain distinct.
- Conflicts must not be silently resolved.

---

## 14. Future Architecture

Potential future domains remain intentionally undefined until needed:

```text
ITEMS / EQUIPMENT
PROGRESSION
QUEST / OBJECTIVES
CRAFTING
PROPERTY / SETTLEMENT MANAGEMENT
DIPLOMACY / WAR
KNOWLEDGE / INFORMATION
STORAGE IMPLEMENTATION
CONCURRENCY CONTROL
ADVANCED RECOVERY / TRANSACTION MECHANISMS
```

Selection rule:

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

Future domains must not duplicate existing ownership.
