# Eldoria World — Resolution Architecture v0.1

> **Module:** Resolution Architecture  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Resolution Architecture mendefinisikan kontrak generik untuk memproses Action menjadi Result berdasarkan Canon, Current State, context, dan resolution authority yang relevan.

Modul ini adalah **core runtime infrastructure**. Ia menyediakan kerangka resolution tanpa menciptakan satu formula gameplay universal.

## 2. Canonical Boundary

Resolution Architecture adalah canonical owner untuk:

- Resolution Request;
- resolution context;
- resolution process contract;
- Resolution Result;
- outcome/status representation;
- consequence handoff;
- domain-resolution routing;
- temporal-result handoff;
- State Change generation handoff.

Resolution Architecture bukan owner untuk:

- Action structure;
- NPC decision-making;
- domain-specific rules;
- State semantics;
- History semantics;
- State Validation;
- Persistence.

## 3. Core Resolution Chain

```text
ACTION
↓
ACTION VALIDATION
↓
RESOLUTION REQUEST
↓
RELEVANT DOMAIN RESOLUTION
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
```

Resolution tidak boleh melewati validation atau persistence boundary.

## 4. Resolution Request

Model konseptual:

```text
RESOLUTION REQUEST
├── Resolution ID
├── Action Reference
├── Actor / Source
├── Target / Subject References
├── Current State Reference
├── Working State Reference (if applicable)
├── Canon / Rule References
├── Context
├── Parameters / Inputs
├── Temporal Context
├── Knowledge Context
├── Domain Reference
├── Origin / Source
└── Metadata
```

Request harus cukup untuk mengidentifikasi bagaimana Action akan di-resolve tanpa mengisi data yang belum diketahui dengan asumsi.

## 5. Resolution Authority

Resolution harus diarahkan kepada domain yang memiliki canonical authority atas outcome.

```text
CORE RESOLUTION ARCHITECTURE
            ↓
RELEVANT DOMAIN
            ↓
DOMAIN-SPECIFIC RESULT
```

Contoh:

```text
COMBAT → Combat
TRAVEL → Travel & Movement
LEGAL → Law
RELATIONSHIP → Relationships
REPUTATION → Reputation
HEALTH CONSEQUENCE → Health & Injury
NPC ACTION SELECTION → NPC Behavior & Agency
```

Contoh tersebut menunjukkan routing/ownership, bukan daftar mekanik universal.

## 6. No Universal Resolution Formula

Resolution Architecture tidak menetapkan formula universal seperti:

```text
Success = Attribute × Modifier
```

atau probability, difficulty, multiplier, damage, speed, social score, atau formula lain yang berlaku ke seluruh Eldoria.

Jika sebuah domain memerlukan formula, formula tersebut harus didefinisikan oleh domain Canon yang relevan.

## 7. Resolution Context

Resolution dapat menggunakan:

- Current State;
- Working State;
- Canon rules;
- actor capabilities/data yang tersedia;
- target state;
- environment;
- location;
- temporal context;
- relevant relationships/reputation;
- legal context;
- domain-specific information;
- valid external conditions.

Context harus memiliki basis yang sah dan tidak boleh memperluas knowledge actor secara otomatis.

## 8. Resolution Process

Resolution secara konseptual:

```text
VALID ACTION
↓
IDENTIFY RESOLUTION AUTHORITY
↓
LOAD RELEVANT RULES / STATE
↓
PROCESS ACTION
↓
DETERMINE OUTCOME
↓
GENERATE RESULT
```

Detail proses bergantung pada domain system.

## 9. Result

Model konseptual:

```text
RESOLUTION RESULT
├── Resolution ID
├── Action Reference
├── Status
├── Outcome
├── Consequences
├── State Change References (if any)
├── Temporal Result (if any)
├── Provenance
└── Metadata
```

Result menjelaskan apa yang dihasilkan resolution. Result bukan otomatis persistent State.

## 10. Result Status

Status konseptual yang dapat digunakan:

```text
SUCCESS
PARTIAL
FAILURE
BLOCKED
DELAYED
INTERRUPTED
UNRESOLVED
```

Domain dapat membutuhkan status tambahan selama semantics tetap jelas.

Status ini tidak merupakan universal probability atau score.

## 11. Success

`SUCCESS` berarti resolution menghasilkan outcome yang memenuhi kondisi keberhasilan domain yang relevan.

Success tidak berarti seluruh Action intent pasti tercapai jika domain membedakan tujuan dan outcome.

## 12. Partial Result

`PARTIAL` berarti resolution menghasilkan sebagian outcome atau outcome terbatas sesuai domain rules.

Partial bukan nilai numerik universal dan tidak boleh diterjemahkan ke persentase tanpa rule yang sah.

## 13. Failure

`FAILURE` adalah hasil gameplay yang sah ketika Action dapat diproses tetapi outcome yang diharapkan tidak tercapai.

```text
VALID ACTION
↓
RESOLUTION
↓
FAILURE RESULT
```

Failure dapat atau tidak dapat menghasilkan consequences sesuai domain.

## 14. Blocked

`BLOCKED` berarti Action tidak dapat melanjutkan proses normal karena constraint yang berlaku.

Blocked harus dibedakan dari failure ketika perbedaan tersebut relevan terhadap consequences atau subsequent actions.

## 15. Delayed

`DELAYED` berarti outcome atau proses belum selesai pada titik resolution saat ini dan membutuhkan proses temporal atau event lanjutan yang sah.

Resolution tidak boleh mengubah delayed menjadi success hanya demi menyelesaikan narrative.

## 16. Interrupted

`INTERRUPTED` berarti proses Action/resolution berhenti karena kondisi atau event yang valid sebelum outcome normal selesai.

Consequences dari interruption harus ditentukan oleh domain yang relevan.

## 17. Unresolved

`UNRESOLVED` digunakan ketika resolution tidak dapat menghasilkan outcome yang sah, misalnya karena rule atau data Canon yang diperlukan belum tersedia.

```text
MISSING CANON / REQUIRED DATA
↓
UNRESOLVED
```

`UNRESOLVED` bukan automatic character failure.

## 18. Validation vs Resolution

```text
ACTION VALIDATION
= apakah Action dapat diproses?

RESOLUTION
= apa hasilnya jika diproses?
```

Validation success tidak menjamin Resolution success.

Resolution tidak boleh memperbaiki Action yang invalid secara diam-diam.

## 19. Intent vs Result

```text
INTENT
↓
ACTION
↓
RESOLUTION
↓
RESULT
```

Player atau NPC menentukan intent/action sesuai authority masing-masing, tetapi Resolution menentukan outcome berdasarkan Canon dan State.

Tidak ada plot protection yang mengubah intent menjadi guaranteed result.

## 20. Consequences

Setelah Result ditentukan, Resolution Architecture mengidentifikasi consequence handoff:

```text
RESULT
↓
CONSEQUENCES
```

Consequences dapat melibatkan:

- Character;
- NPC;
- location;
- resources;
- relationship;
- reputation;
- legal state;
- health/injury;
- world condition;
- event;
- entity lain yang relevan.

Domain yang memiliki canonical ownership tetap menentukan semantics consequence domain tersebut.

## 21. State Change Handoff

Resolution dapat menghasilkan State Change proposal:

```text
RESULT
↓
CONSEQUENCE
↓
STATE CHANGE PROPOSAL
↓
STATE VALIDATION
```

Resolution tidak boleh menganggap proposal tersebut final sebelum State Validation.

## 22. Multiple State Changes

Satu Result dapat menghasilkan beberapa State Changes.

Jika perubahan saling bergantung:

```text
RESULT
↓
CHANGE SET
↓
STATE VALIDATION AS SET
↓
PERSIST AS INTEGRATED RESULT
```

Resolution Architecture tidak menggantikan State Validation dalam menentukan validitas final Change Set.

## 23. Working State

Dalam Turn dengan sequential actions, Resolution menggunakan Working State yang benar-benar dihasilkan resolution sebelumnya.

```text
CURRENT STATE
↓
ACTION A
↓
RESULT A
↓
WORKING STATE A
↓
ACTION B
↓
RESULT B
```

Result yang belum lolos final validation/persistence tidak boleh disebut persistent final State.

## 24. Sequential Resolution

Jika Action B bergantung pada Result A, B harus di-resolve terhadap keadaan yang berlaku setelah A sesuai Runtime.

Jika A gagal, blocked, delayed, atau interrupted, B tidak otomatis berhasil atau tetap terjadi. Kelanjutan ditentukan oleh dependency dan domain rules.

## 25. Concurrent Resolution

Beberapa proses dapat memiliki interval yang beririsan jika Canon dan system mengizinkannya.

Resolution tidak boleh memaksakan urutan hanya demi kemudahan narasi jika tidak ada causal dependency atau rule yang memerlukan urutan.

## 26. Temporal Result

Resolution dapat menghasilkan temporal result seperti elapsed duration atau perubahan temporal context jika domain menetapkannya.

```text
DOMAIN RESOLUTION
↓
VALID TEMPORAL RESULT
↓
TIME & CALENDAR
```

Time & Calendar tetap canonical temporal authority. Resolution Architecture tidak menetapkan duration universal.

## 27. Knowledge Boundary

Resolution harus menggunakan knowledge yang sah untuk proses tersebut.

```text
CANON
≠ CHARACTER KNOWLEDGE
≠ PLAYER KNOWLEDGE
≠ NPC KNOWLEDGE
```

Information yang diketahui GM/Repository tidak otomatis menjadi information yang diketahui actor.

## 28. Provenance

Resolution Result dan State Change yang dihasilkannya harus dapat ditelusuri ke Action, relevant rules, context, Origin, dan Source ketika diperlukan.

Resolution tidak mengambil alih semantics provenance milik State & History.

## 29. Domain Ownership Examples

### Combat

Combat menentukan combat/conflict outcome. Resolution Architecture menyediakan contract dan routing, bukan damage atau combat formula.

### Travel

Travel & Movement menentukan travel/movement outcome. Time & Calendar menentukan temporal authority.

### Law

Law menentukan legal outcome berdasarkan jurisdiction dan applicable rules. Political authority tetap milik Politics.

### Relationships / Reputation

Relationships menentukan relationship state/change; Reputation menentukan socially attributed reputation state/change. NPC Behavior dapat menggunakan keduanya sebagai context untuk decision-making.

### NPC

NPC Behavior menentukan pilihan/keputusan NPC. Resolution domain yang relevan menentukan outcome Action NPC tersebut.

## 30. Failure of Resolution vs System Failure

```text
FAILURE
= valid gameplay outcome

BLOCKED
= action cannot proceed under current constraints

UNRESOLVED
= valid outcome cannot be established from available Canon/data

ENGINE / PROCESS FAILURE
= resolution process itself failed or could not complete
```

Status tersebut tidak boleh dicampur hanya untuk menyederhanakan narrative.

## 31. Unknown / Undefined

Jika rule, value, target, context, atau mechanic yang diperlukan belum didefinisikan:

```text
UNKNOWN / UNDEFINED
```

Resolution Architecture tidak boleh menciptakan fallback, average, default, probability, multiplier, atau formula untuk menutup kekosongan Canon.

## 32. Autonomous World Resolution

NPC, faction, environment, ecology, event, economic process, political process, atau system process dapat menghasilkan Action/Resolution tanpa Player.

Semua tetap harus memiliki basis yang sah dan melewati Action, Resolution, State Validation, dan Persistence boundaries yang relevan.

## 33. No Narrative Resolution

Narrative response tidak menentukan Result.

```text
RESOLUTION
↓
RESULT
↓
NARRATIVE REPRESENTATION
```

Bukan:

```text
NARRATIVE DESIRE
↓
FORCED RESULT
```

## 34. Runtime Integration

```text
PLAYER / NPC / WORLD INPUT
↓
INTENT
↓
ACTION MODEL
↓
ACTION VALIDATION
↓
RESOLUTION REQUEST
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
RESPONSE
```

## 35. State Validation Handoff

Resolution Result yang menghasilkan State Change harus menyerahkan perubahan tersebut kepada `core/STATE_VALIDATION.md`.

Resolution tidak boleh menganggap New Value valid hanya karena resolution telah selesai.

## 36. Persistence Handoff

Hanya validated Change Set yang boleh diteruskan ke `core/PERSISTENCE.md`.

```text
RESULT
↓
STATE CHANGE
↓
STATE VALIDATION
↓
VALIDATED CHANGE SET
↓
PERSISTENCE
```

Persistence tidak menentukan atau memperbaiki gameplay Result.

## 37. Integrity Rules

- Resolution tidak menentukan Action selection Player.
- NPC Behavior tetap memiliki action-selection authority NPC.
- Intent ≠ Result.
- Action ≠ Result.
- Result ≠ State Change.
- Action Validation ≠ Resolution.
- Validation tidak menjamin success.
- Domain-specific systems tetap menjadi owner mechanics dan outcome domain mereka.
- Tidak ada universal resolution formula pada v0.1.
- Tidak ada universal probability, multiplier, score, threshold, atau difficulty formula.
- Failure adalah gameplay result yang sah.
- Unresolved tidak boleh diperlakukan otomatis sebagai character failure.
- Blocked, delayed, interrupted, failure, dan unresolved harus dapat dibedakan.
- Working State digunakan untuk sequential resolution dan bukan persistence final.
- Multi-entity/interdependent State Changes diserahkan sebagai Change Set untuk validation.
- Temporal result mengikuti Time & Calendar authority.
- Unknown/Undefined tidak boleh diisi dengan fallback.
- Narrative tidak menentukan outcome.
- Provenance harus tetap dapat ditelusuri.
- Resolution tidak boleh melewati State Validation dan Persistence boundary.
- Autonomous resolution memerlukan basis yang sah.

## 38. Dependencies

Resolution Architecture bergantung pada:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
core/ACTION_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
core/STATE_VALIDATION.md
core/PERSISTENCE.md
world/OTHER_WORLD_SYSTEMS.md
```

Resolution juga bergantung pada domain system yang relevan untuk setiap Action.

## 39. Future Extensions

```text
RESOLUTION PLUGIN CONTRACTS
DETERMINISTIC RESOLUTION IMPLEMENTATION
UNCERTAINTY / RANDOMNESS IMPLEMENTATION
RESOLUTION TRACE FORMAT
RESOLUTION REPLAY
CONCURRENCY / CONFLICT ENGINE
EVENT-DRIVEN RESOLUTION
TRANSACTIONAL RESOLUTION SUPPORT
```

Ekstensi tersebut harus tetap tunduk pada canonical ownership dan tidak boleh menciptakan universal gameplay mechanics secara diam-diam.
