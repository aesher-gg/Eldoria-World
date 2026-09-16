# Eldoria World — NPC / Faction Simulation v0.1

> **Module:** Core Architecture — NPC / Faction Simulation  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

NPC / Faction Simulation mendefinisikan orchestration layer untuk memproses aktivitas autonomous NPC dan Faction berdasarkan State, Knowledge, goals, context, constraints, dan proses dunia yang relevan.

Modul ini menutup gap antara:

```text
WORLD CONTEXT
↓
WHO / WHAT NEEDS EVALUATION?
↓
NPC / FACTION PROCESS
↓
DECISION / ACTION
↓
RESOLUTION
↓
CONSEQUENCE
↓
STATE CHANGE
```

Modul ini **bukan** pengganti NPC Behavior & Agency dan **bukan** pemilik struktur/aturan Faction.

## 2. Canonical Boundary

NPC / Faction Simulation owns:

- autonomous-process orchestration;
- actor/process eligibility evaluation;
- selection of relevant NPC/Faction processes for evaluation;
- loading relevant context;
- invoking NPC Behavior & Agency or Faction logic;
- coordinating autonomous action sequences;
- autonomous reaction-loop orchestration;
- handing selected actions to Action Model and Resolution Architecture;
- coordinating consequences and subsequent evaluation;
- provenance/reference for the simulation process.

It does **not** own:

- NPC decision-making rules → `systems/NPC_BEHAVIOR_AND_AGENCY.md`;
- Faction structure/state/goals/membership → `world/FACTIONS.md`;
- generic Action structure → `core/ACTION_MODEL.md`;
- generic Resolution contract → `core/RESOLUTION_ARCHITECTURE.md`;
- domain-specific outcome → relevant domain system;
- temporal authority → `systems/TIME_AND_CALENDAR.md`;
- State/History semantics → `state/STATE_AND_HISTORY_MODEL.md`;
- State integrity → `core/STATE_VALIDATION.md`;
- Persistence → `core/PERSISTENCE.md`.

## 3. Core Distinction

```text
NPC BEHAVIOR & AGENCY
= Apa yang NPC pilih?

FACTIONS
= Apa struktur, kondisi, tujuan, dan hubungan Faction?

NPC / FACTION SIMULATION
= Kapan dan dalam konteks apa autonomous actor/process dievaluasi?

ACTION MODEL
= Bagaimana Action direpresentasikan?

RESOLUTION ARCHITECTURE
= Bagaimana Action menghasilkan Result?

DOMAIN SYSTEM
= Bagaimana outcome domain ditentukan?
```

Simulation layer tidak boleh menjadi “NPC AI v2”.

## 4. Autonomous Processing Model

Konseptual:

```text
CURRENT WORLD / RELEVANT STATE
+
AVAILABLE WORLD INFORMATION
+
ACTOR / FACTION STATE
+
ELIGIBILITY / TRIGGER CONTEXT
↓
SELECT PROCESS TO EVALUATE
↓
LOAD RELEVANT CONTEXT
↓
INVOKE NPC BEHAVIOR / FACTION LOGIC
↓
INTENT / ACTION
↓
ACTION MODEL
↓
RESOLUTION ARCHITECTURE
↓
DOMAIN RESOLUTION
↓
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
VERIFY
↓
REASSESS WHEN REQUIRED
```

## 5. Actor Eligibility

Tidak semua NPC atau Faction harus diproses setiap saat.

Eligibility dapat berasal dari:

- State change;
- Event;
- direct interaction;
- relevant threat/opportunity;
- active goal;
- relationship/reputation context;
- legal/economic/political condition;
- environmental condition;
- scheduled process yang memiliki dasar waktu sah;
- other Canon-defined condition.

```text
VALID BASIS
↓
ELIGIBLE PROCESS
```

Tidak ada universal activity rate, decision frequency, priority score, probability, atau simulation tick dalam v0.1.

## 6. Process Selection

Simulation dapat memilih subset actor/process yang relevan berdasarkan konteks.

Selection harus dapat dijelaskan melalui:

- relevance terhadap perubahan/context;
- active condition;
- actor state;
- valid trigger;
- dependency;
- domain requirement.

Pemilihan actor tidak boleh didasarkan pada kebutuhan narrative semata.

## 7. NPC Processing

Untuk NPC:

```text
NPC CURRENT STATE
+
NPC KNOWLEDGE
+
GOALS / MOTIVATIONS
+
CURRENT CONTEXT
+
CONSTRAINTS
↓
NPC BEHAVIOR & AGENCY
↓
DECISION / INTENT
↓
ACTION MODEL
```

NPC Behavior & Agency tetap menjadi owner keputusan NPC.

Simulation hanya mengorkestrasi kapan dan mengapa proses evaluasi dilakukan.

## 8. Faction Processing

Untuk Faction:

```text
FACTION STATE
+
GOALS / INTERESTS
+
RESOURCES / CAPABILITIES
+
INTERNAL / EXTERNAL CONTEXT
+
RELEVANT INFORMATION
↓
FACTION LOGIC / AUTONOMOUS PROCESS
↓
FACTION INTENT / ACTION
↓
ACTION MODEL
```

Faction Simulation tidak menciptakan struktur, membership, leadership, goals, resources, atau relations yang tidak dimiliki Canon Faction.

## 9. Action Handoff

Setelah actor menghasilkan intent/action:

```text
INTENT
↓
ACTION MODEL
↓
ACTION VALIDATION
↓
RESOLUTION ARCHITECTURE
↓
RELEVANT DOMAIN SYSTEM
```

Simulation tidak boleh langsung mengubah State hanya karena NPC/Faction memilih suatu intent.

## 10. Resolution and Consequences

Outcome tetap ditentukan oleh resolution/domain system.

```text
AUTONOMOUS ACTION
↓
RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE(S)
```

Contoh:

```text
NPC decides to travel → TRAVEL & MOVEMENT resolves
NPC attacks → COMBAT resolves
NPC seeks treatment → HEALTH & INJURY resolves relevant treatment outcome
Faction conducts trade → ECONOMY resolves transaction/process
Faction initiates legal action → LAW resolves legal process
```

Simulation tidak memiliki universal outcome formula.

## 11. Reaction Loop

Setelah outcome diketahui, actor dapat dievaluasi kembali bila result/consequence menghasilkan kondisi yang relevan:

```text
DECISION
↓
ACTION
↓
RESULT
↓
CONSEQUENCE
↓
NEW STATE / NEW INFORMATION
↓
REASSESS
```

Reassessment bukan kewajiban setiap Action. Ia terjadi bila terdapat valid basis untuk proses berikutnya.

## 12. NPC and Faction Interaction

NPC dan Faction dapat saling memengaruhi:

```text
NPC ACTION
↓
FACTION STATE / INFORMATION CHANGE
↓
FACTION PROCESS
↓
FACTION ACTION
↓
NPC RESPONSE
```

Atau sebaliknya.

Setiap actor tetap mempertahankan autonomy dan knowledge boundary masing-masing.

## 13. Knowledge Boundary

Simulation tidak memberikan omniscience.

Harus dibedakan:

```text
CANON FACT
NPC KNOWLEDGE
FACTION KNOWLEDGE
PLAYER KNOWLEDGE
UNCERTAIN / RUMOR
```

Actor hanya dapat membuat keputusan berdasarkan informasi yang tersedia menurut konteksnya.

Player mengetahui sesuatu tidak berarti NPC/Faction mengetahuinya.

## 14. Time Integration

Simulation dapat menggunakan waktu ketika proses memang membutuhkan temporal context.

`systems/TIME_AND_CALENDAR.md` tetap menjadi authority untuk:

- World Time;
- Duration;
- temporal ordering;
- time advancement.

NPC / Faction Simulation tidak menetapkan:

```text
NPC TICK = X jam
FACTION TICK = X hari
```

Process dapat bersifat:

- event-driven;
- context-driven;
- state-driven;
- time-driven jika Canon memberikan dasar temporal.

## 15. Autonomous Does Not Mean Random

Simulation bukan random activity generator.

```text
VALID WORLD BASIS
↓
ELIGIBILITY
↓
CONTEXT
↓
ACTOR DECISION / PROCESS
↓
ACTION
↓
RESOLUTION
```

Randomness hanya boleh digunakan jika domain/Canon yang relevan secara eksplisit mendukungnya. Core v0.1 tidak menyediakan random fallback.

## 16. State and History

Autonomous processing dapat menghasilkan State Changes pada:

- NPC;
- Faction;
- Player;
- location;
- economy;
- political conditions;
- relationships;
- reputation;
- legal state;
- environment;
- other persistent entities.

Semua perubahan harus mengikuti:

```text
RESULT
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY / PROVENANCE
↓
PERSISTENCE
↓
VERIFICATION
```

Starting State tidak boleh ditimpa.

## 17. Multiple Autonomous Processes

Jika beberapa process saling bergantung:

```text
PROCESS A
↓
RESULT A
↓
WORKING STATE
↓
PROCESS B
↓
RESULT B
```

Urutan harus mengikuti temporal order, dependency, dan context yang sah.

Jika beberapa State Changes saling bergantung, perubahan tersebut diproses sebagai Change Set sesuai State Validation/Persistence.

Simulation tidak mengklaim transaction/rollback mechanism yang belum didefinisikan.

## 18. World Event Integration

NPC/Faction Simulation dapat berinteraksi dengan World Event Processor:

```text
WORLD EVENT
↓
NPC / FACTION ELIGIBILITY
↓
DECISION
↓
ACTION
↓
RESOLUTION
↓
CONSEQUENCE
```

Atau:

```text
NPC / FACTION ACTION
↓
RESULT
↓
EVENT TRIGGER / WORLD EVENT
```

World Event Processor tetap owner event orchestration; NPC/Faction Simulation tetap owner autonomous actor orchestration.

## 19. Failure / Blocked / Unresolved

Autonomous process dapat menghasilkan:

```text
SUCCESS
PARTIAL
FAILURE
BLOCKED
DELAYED
INTERRUPTED
UNRESOLVED
```

Failure tidak berarti process “salah”; itu dapat menjadi outcome simulasi yang sah.

`UNRESOLVED` digunakan ketika required rule/data/mechanic belum tersedia atau resolution tidak dapat ditentukan secara sah.

## 20. Conflict Handling

Jika autonomous processing menemukan konflik:

```text
DETECT CONFLICT
↓
PRESERVE TRACEABILITY
↓
VALIDATE RELEVANT STATE / SOURCES
↓
EXPLICIT CORRECTION OR CANON PROCESS IF REQUIRED
```

Simulation tidak boleh diam-diam memilih State yang bertentangan.

## 21. Persistence Boundary

Simulation menghasilkan proposed results/change sets. Final State tetap melewati:

```text
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
```

Narrative tidak menjadi bukti bahwa autonomous processing telah dipersist.

## 22. No Universal Simulation Tick

v0.1 secara sengaja tidak mendefinisikan:

- NPC simulation tick;
- Faction simulation tick;
- universal world tick;
- universal activity frequency;
- universal decision frequency;
- universal actor priority score;
- universal probability of action.

Hal tersebut hanya dapat didefinisikan oleh Canon/domain tertentu pada masa depan jika benar-benar diperlukan.

## 23. Integrity Rules

- NPC Behavior & Agency tetap owner NPC decision-making.
- Factions tetap owner Faction structure/state/goals/membership/relations.
- Simulation adalah orchestration layer, bukan decision replacement.
- Intent ≠ Action ≠ Result ≠ State Change.
- Autonomous action tetap harus melewati Action Model dan relevant resolution.
- Domain system tetap owner domain outcome.
- Actor knowledge tidak omniscient.
- Autonomous ≠ random.
- Tidak ada universal simulation tick/frequency/probability/priority score.
- Time & Calendar tetap temporal authority.
- State Validation tetap integrity gate.
- Persistence tetap save authority.
- Unknown/Undefined tidak boleh diisi dengan asumsi.
- Conflicts tidak boleh diselesaikan diam-diam.
- Autonomous processing membutuhkan valid basis.
- AI GM tidak boleh mengklaim persistence tanpa verification.
