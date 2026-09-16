# Eldoria World — Runtime / Turn Model v0.2

> **Module:** Runtime / Turn Model  
> **Version:** v0.2  
> **Authority:** Official Canon

## 1. Purpose

Runtime / Turn Model mendefinisikan bagaimana Eldoria memproses satu Player Message menjadi satu Turn simulasi yang terstruktur, sekaligus menyediakan jalur untuk autonomous World Event dan NPC/Faction processing.

Runtime menetapkan pipeline dan orchestration boundary, bukan mekanik khusus combat, magic, ekonomi, kalender, atau domain lain.

## 2. Authority

```text
ADMIN
└── Repository / Canon

AI GM
└── Simulation / Resolution / NPC / World / Events

PLAYER
└── Character decisions / intent
```

Repository adalah Official Canon + Persistent State Source.

## 3. Turn Definition

**Satu Player Message = satu Turn.**

Satu Turn dapat memiliki nol, satu, atau beberapa Action. Action yang saling bergantung diproses berurutan menggunakan Working State.

Player Message dapat berisi dialogue, question, description, meta request, dan/atau Action.

## 4. Main Runtime Pipeline

```text
1. BOOT / LOAD CONTEXT
2. READ CURRENT STATE
3. RECEIVE PLAYER MESSAGE
4. PARSE MESSAGE
5. IDENTIFY INTENT / ACTION
6. VALIDATE ACTION
7. BUILD RESOLUTION REQUEST
8. RESOLVE THROUGH RELEVANT DOMAIN
9. GENERATE RESULT
10. CALCULATE CONSEQUENCES
11. GENERATE STATE CHANGES
12. VALIDATE STATE CHANGES
13. APPLY STATE
14. CREATE / UPDATE HISTORY
15. PERSIST
16. VERIFY PERSISTENCE
17. GENERATE RESPONSE
18. END TURN
```

Tidak semua tahap menghasilkan perubahan State. Interaction tanpa Action tetap merupakan Turn yang sah.

## 5. Boot / Load Context

```text
INDEX
↓
RELEVANT CANON / DATA
↓
CURRENT STATE
↓
RELEVANT HISTORY
↓
RUNTIME CONTEXT
```

AI GM tidak wajib memuat seluruh Repository atau History pada setiap Turn. Data yang diperlukan harus benar-benar dimuat sebelum digunakan sebagai Canon/State yang terverifikasi.

Unknown/Undefined tidak boleh diganti asumsi.

## 6. Current State

Current State adalah baseline operasional Turn.

Konflik atau inkonsistensi pada State yang diperlukan tidak boleh diselesaikan diam-diam. Ikuti State & History Model dan State Validation.

Starting State tetap historical baseline dan tidak ditimpa oleh normal gameplay persistence.

## 7. Parse / Intent / Action

```text
PLAYER MESSAGE
├── Intent
├── Action(s)
├── Dialogue
├── Question
├── Description
└── Meta / System Request
```

```text
INTENT
≠
ACTION
≠
RESULT
≠
STATE CHANGE
```

Action terstruktur menggunakan `core/ACTION_MODEL.md`. Player intent tidak otomatis menjadi State.

## 8. Action Validation

Action divalidasi terhadap Current State, Canon, context, target, available data, relevant domain rules, constraints, dan dependencies.

Validation menjawab apakah Action dapat diproses secara sah; validation bukan jaminan keberhasilan.

## 9. Resolution

```text
VALID ACTION
↓
RESOLUTION REQUEST
↓
RELEVANT DOMAIN RESOLUTION
↓
RESULT
↓
CONSEQUENCES
```

`core/RESOLUTION_ARCHITECTURE.md` menyediakan generic contract. Domain system tetap owner outcome domain.

Contoh:

```text
COMBAT → COMBAT
TRAVEL → TRAVEL & MOVEMENT
LEGAL → LAW
RELATIONSHIP → RELATIONSHIPS
REPUTATION → REPUTATION
NPC DECISION → NPC BEHAVIOR & AGENCY
```

Runtime tidak membuat universal formula, probability, multiplier, score, threshold, atau damage rule.

## 10. Result Status

Status konseptual:

```text
SUCCESS
PARTIAL
FAILURE
BLOCKED
DELAYED
INTERRUPTED
UNRESOLVED
```

`FAILURE` adalah gameplay outcome. `UNRESOLVED` berarti outcome belum dapat ditentukan secara sah karena rule/data/mechanic yang diperlukan belum tersedia.

## 11. Sequential Actions / Working State

Action yang saling bergantung diproses:

```text
ACTION A
↓
RESULT A
↓
WORKING STATE
↓
ACTION B
↓
RESULT B
```

Working State bersifat sementara dan bukan persistence final. Final State Changes tetap harus divalidasi dan dipersist melalui canonical layers.

## 12. Consequences / State Changes

```text
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE(S)
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
```

Consequences harus memiliki basis dari Result, Canon, State, atau relevant system. Tidak boleh dibuat semata-mata untuk menghukum atau menyenangkan Player.

## 13. State Validation

Semua State Change final harus melalui `core/STATE_VALIDATION.md`.

Minimal mencakup target, Previous Value, New Value, Canon compatibility, provenance, temporal consistency, conflicts, dan Change Set consistency.

Interdependent changes divalidasi sebagai integrated Change Set.

## 14. History

History harus mempertahankan provenance yang relevan, termasuk waktu, target/subject, previous/new value, cause, origin, source, consequence, dan record type sesuai State & History Model.

Narrative response bukan History dan bukan bukti persistence.

## 15. Time

`systems/TIME_AND_CALENDAR.md` adalah canonical temporal authority.

Runtime v0.2 tidak menetapkan durasi universal Turn, Action, NPC simulation tick, Event tick, atau interval dunia.

Time-driven processing hanya digunakan bila terdapat basis temporal yang sah.

## 16. World Event Processing

Event dunia dapat diproses melalui `core/WORLD_EVENT_PROCESSOR.md`.

```text
WORLD CONTEXT / EVENT
↓
EVENT ELIGIBILITY
↓
EVENT PROCESSOR
↓
ACTION / RESOLUTION / DOMAIN HANDOFF
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
```

World Event Processor memiliki ownership atas event lifecycle/orchestration, trigger/context evaluation, scheduling bila diperlukan, event chaining, dan consequence handoff.

Event Processor tidak memiliki ownership atas Time, State/History, Action Model, generic Resolution, domain mechanics, State Validation, atau Persistence.

## 17. Event Chaining

Event dapat memicu Event berikutnya jika Result/Consequence menghasilkan trigger yang sah:

```text
EVENT A
↓
RESULT / CONSEQUENCE
↓
VALID TRIGGER
↓
EVENT B
```

Chain harus traceable, mengikuti temporal/dependency constraints, dan tidak boleh menggunakan universal chain depth atau propagation multiplier.

## 18. Autonomous NPC / Faction Processing

Autonomous NPC/Faction processing menggunakan `core/NPC_FACTION_SIMULATION.md`.

```text
WORLD / RELEVANT STATE
↓
PROCESS ELIGIBILITY
↓
SELECT ACTOR / PROCESS
↓
LOAD CONTEXT
↓
NPC BEHAVIOR / FACTION LOGIC
↓
INTENT / ACTION
↓
ACTION MODEL
↓
RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFY
```

Simulation layer mengorkestrasi kapan dan dalam konteks apa actor dievaluasi. `systems/NPC_BEHAVIOR_AND_AGENCY.md` tetap owner NPC decision-making, sedangkan `world/FACTIONS.md` tetap owner Faction structure/state/goals/membership/relations.

## 19. Autonomous Reaction Loop

Result atau State Change dapat menciptakan basis untuk evaluasi berikutnya:

```text
DECISION
↓
ACTION
↓
RESULT
↓
CONSEQUENCE
↓
NEW STATE / INFORMATION
↓
REASSESS WHEN JUSTIFIED
```

Reassessment harus memiliki basis yang sah. Autonomous processing bukan random story generation.

## 20. NPC / Faction Knowledge Boundary

Simulation harus membedakan:

```text
CANON FACT
NPC KNOWLEDGE
FACTION KNOWLEDGE
PLAYER KNOWLEDGE
RUMOR / UNCERTAIN INFORMATION
```

Actor tidak omniscient. Player Knowledge tidak otomatis menjadi NPC/Faction Knowledge.

## 21. Autonomous World Processing

Runtime dapat memproses perubahan non-Player dari:

```text
NPC
FACTION
EVENT
ENVIRONMENT
ECONOMY
POLITICS
ECOLOGY
SUPERNATURAL PROCESS
OTHER VALID WORLD PROCESS
```

Autonomous change harus memiliki valid basis dan mengikuti Action/Resolution atau Event architecture yang relevan, kemudian State Validation, History, Persistence, dan Verification.

## 22. Conflict / Unknown Handling

```text
CONFLICT
↓
DETECT
↓
PRESERVE TRACEABILITY
↓
VALIDATE SOURCES / STATE
↓
EXPLICIT CORRECTION / VALID PROCESS
```

Konflik tidak boleh diselesaikan diam-diam.

Jika required rule/data/mechanic tidak tersedia, gunakan `UNKNOWN / UNDEFINED` atau `UNRESOLVED` sesuai konteks. Jangan membuat fallback.

## 23. No Retroactive State

Runtime tidak boleh menambahkan fakta ke masa lalu hanya untuk membenarkan resolution saat ini.

```text
WHAT WAS TRUE
≠
WHAT IS NOW KNOWN
```

Perubahan historical hanya melalui mekanisme Canon/State/History yang sah dan dapat diaudit.

## 24. Persistence / Verification

```text
VALIDATED CHANGE SET
↓
APPLY
↓
PERSIST
↓
VERIFY
```

Persistence mengikuti `core/PERSISTENCE.md`. AI GM tidak boleh menyatakan perubahan tersimpan resmi tanpa verification.

Validation failure, persistence failure, dan verification failure tetap berbeda.

## 25. Response Generation

Response dibuat setelah Result dan status State/Persistence yang relevan diketahui.

Narrative harus merepresentasikan hasil simulasi, bukan menentukan hasil simulasi.

## 26. Turn Completion

```text
INPUT
↓
PARSE
↓
VALIDATE
↓
RESOLVE
↓
CONSEQUENCES
↓
VALIDATE STATE
↓
PERSIST
↓
VERIFY
↓
RESPONSE
```

Untuk autonomous processing, Event Processor atau NPC/Faction Simulation dapat menjadi orchestration entry point sebelum Action/Resolution dan tetap berakhir pada validation/persistence/verification.

## 27. Integrity Rules

- Satu Player Message = satu Turn.
- Intent ≠ Action ≠ Result ≠ State Change.
- Action yang saling bergantung diproses berurutan.
- Working State bukan persistence final.
- Domain system tetap owner domain resolution.
- World Event Processor adalah owner event orchestration, bukan domain mechanics.
- NPC/Faction Simulation adalah owner autonomous orchestration, bukan NPC decision-making atau Faction structure.
- NPC Behavior & Agency tetap owner NPC decision.
- Factions tetap owner Faction state/structure/goals/membership/relations.
- Time & Calendar tetap temporal authority.
- State Validation tetap integrity gate.
- Persistence tetap save authority.
- Autonomous ≠ random.
- Tidak ada universal simulation tick/frequency/probability/priority score.
- Unknown/Undefined tidak boleh diisi asumsi.
- Conflict tidak boleh diselesaikan diam-diam.
- Autonomous changes membutuhkan valid basis.
- AI GM tidak boleh mengklaim persistence tanpa verification.
