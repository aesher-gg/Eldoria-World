# Eldoria World — Action Model v0.1

> **Module:** Action Model  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Action Model mendefinisikan kontrak generik untuk merepresentasikan tindakan yang diproses Runtime Eldoria. Modul ini memisahkan Intent, Action, Result, Consequence, dan State Change agar keputusan Player/NPC tidak otomatis menjadi hasil atau perubahan State.

Modul ini adalah **core runtime infrastructure**, bukan domain-specific resolution system.

## 2. Canonical Boundary

Action Model adalah canonical owner untuk:

- struktur konseptual Action;
- identitas Action;
- actor/action source;
- intent representation;
- target/reference;
- action context;
- input/parameters;
- action dependency dan sequencing metadata;
- action lifecycle/status;
- hubungan Action dengan Resolution.

Action Model bukan owner untuk:

- NPC decision-making;
- combat resolution;
- travel resolution;
- legal resolution;
- relationship/reputation resolution;
- magic/economy/ecology resolution;
- State semantics;
- History semantics;
- State Validation;
- Persistence.

## 3. Core Distinction

```text
INTENT
= apa yang actor ingin lakukan

ACTION
= tindakan terstruktur yang akan diproses

RESULT
= hasil resolution

CONSEQUENCE
= dampak yang mengikuti result

STATE CHANGE
= perubahan State yang benar-benar dihasilkan
```

```text
INTENT ≠ ACTION ≠ RESULT ≠ STATE CHANGE
```

Intent tidak menjamin Action dapat diproses, dan Action tidak menjamin keberhasilan.

## 4. Action Contract

Model konseptual:

```text
ACTION
├── Action ID
├── Actor / Source
├── Intent Reference
├── Action Type / Domain Reference
├── Target(s) / Subject(s) (if applicable)
├── Context
├── Input / Parameters
├── Preconditions / Relevant State References
├── Temporal Context (if applicable)
├── Knowledge Context (if applicable)
├── Dependencies / Sequence Reference (if applicable)
├── Origin / Source
└── Metadata
```

Field yang belum tersedia tidak boleh diisi dengan asumsi.

## 5. Action ID

Setiap Action yang membutuhkan tracking harus memiliki identitas yang memungkinkan Action ditelusuri ke resolution, consequences, State Changes, dan History bila relevan.

Action ID tidak menentukan hasil dan bukan State Change ID.

## 6. Actor

Actor adalah entity yang melakukan atau menjadi sumber Action.

Actor dapat berasal dari:

- Player-controlled character;
- NPC;
- faction/organization jika system mengizinkan;
- world/environmental process;
- system process;
- entity lain yang sah menurut Canon.

Action Model tidak menentukan apakah actor berhak atau mampu melakukan Action; hal tersebut divalidasi berdasarkan State dan domain yang relevan.

## 7. Intent

Intent menyatakan tujuan atau tindakan yang dimaksud actor.

```text
PLAYER / NPC INTENT
↓
ACTION REPRESENTATION
↓
VALIDATION
↓
RESOLUTION
```

Jika Intent ambigu, Runtime dapat mempertahankan ambiguitas atau meminta klarifikasi bila diperlukan. Runtime tidak boleh memilih tujuan yang material secara arbitrer.

## 8. Target and Subject

Action dapat memiliki satu atau beberapa target/subject atau tidak memiliki target.

Target yang disebut Player belum tentu benar-benar tersedia, valid, atau terkena dampak. Target harus divalidasi sebelum resolution.

Target reference tidak otomatis berarti ownership, relationship, hostility, legal status, atau State Change.

## 9. Context

Context adalah informasi yang diperlukan untuk memproses Action, misalnya:

- lokasi;
- Current State reference;
- environment;
- actor condition;
- relevant entity state;
- active event;
- temporal context;
- knowledge context;
- domain-specific constraints.

Context harus berasal dari sumber yang sah dan tidak memperluas knowledge actor secara otomatis.

## 10. Parameters / Input

Action dapat membawa parameter yang eksplisit atau berasal dari valid context.

Parameter bukan hasil resolution. Parameter yang invalid, tidak tersedia, atau bertentangan dengan Canon harus ditangani pada validation stage.

Tidak ada universal parameter schema untuk semua domain.

## 11. Preconditions

Preconditions adalah kondisi yang harus tersedia agar Action dapat diproses.

Precondition validation menjawab:

```text
CAN THIS ACTION BE PROCESSED?
```

bukan:

```text
WILL THIS ACTION SUCCEED?
```

Validation success tidak menjamin Resolution success.

## 12. Action Validation Boundary

Action Validation memeriksa setidaknya ketika relevan:

- actor valid;
- target valid;
- required context tersedia;
- Current State sesuai baseline;
- relevant Canon tersedia;
- required capability/data tersedia;
- constraints terpenuhi;
- dependency/sequence valid;
- temporal context valid.

Action yang tidak lolos validation tidak boleh diperlakukan seolah-olah telah menghasilkan normal resolution.

## 13. Action Status

Status konseptual:

```text
IDENTIFIED
VALID
INVALID
BLOCKED
READY_FOR_RESOLUTION
RESOLVED
CANCELLED
INTERRUPTED
UNRESOLVED
```

Implementasi dapat memakai representasi lain selama semantics tetap terjaga.

Action status tidak sama dengan gameplay Result.

## 14. Resolution Handoff

Action Model menyerahkan Action yang valid kepada Resolution Architecture:

```text
ACTION
↓
ACTION VALIDATION
↓
VALID ACTION
↓
RESOLUTION REQUEST
```

Action Model tidak menentukan outcome.

## 15. Sequential Actions

Satu Turn dapat memiliki beberapa Action.

Jika Action saling bergantung:

```text
ACTION A
↓
RESULT A
↓
WORKING STATE
↓
ACTION B
```

Action B harus menggunakan kondisi yang benar-benar tersedia setelah A, bukan kondisi awal yang sudah tidak berlaku.

Jika Action B bergantung pada keberhasilan A dan A gagal, blocked, atau interrupted, kelanjutan B harus ditentukan oleh aturan relevan, bukan asumsi otomatis.

## 16. Independent Actions

Action yang tidak memiliki causal dependency dapat diproses sesuai Runtime dan domain rules tanpa memaksakan dependency yang tidak ada.

Action Model tidak mengubah process concurrent menjadi sequential tanpa alasan yang sah.

## 17. Working State

Working State adalah representasi sementara hasil Action/Resolution selama Turn.

```text
CURRENT STATE
↓
ACTION
↓
RESULT
↓
WORKING STATE
↓
NEXT ACTION
```

Working State bukan persistence final dan tidak mengubah Starting State.

## 18. Temporal Context

Action dapat memiliki temporal context atau menghasilkan elapsed time jika system yang relevan menetapkannya.

Action Model tidak menentukan duration universal. Time & Calendar tetap menjadi canonical temporal authority.

```text
ACTION
↓
DOMAIN RESOLUTION
↓
VALID TEMPORAL RESULT
```

## 19. Knowledge Boundary

Action harus diproses berdasarkan knowledge yang sah bagi actor dan context yang digunakan.

```text
CANON KNOWLEDGE
≠ CHARACTER KNOWLEDGE
≠ PLAYER KNOWLEDGE
≠ NPC KNOWLEDGE
```

Player mengetahui suatu fakta tidak otomatis membuat character mengetahuinya.

## 20. NPC Boundary

NPC Behavior & Agency menentukan decision/action selection NPC. Action Model hanya merepresentasikan Action yang telah dipilih atau dihasilkan.

```text
NPC BEHAVIOR
↓
ACTION SELECTION
↓
ACTION MODEL
↓
RESOLUTION
```

Action Model tidak mengambil alih motivasi atau keputusan NPC.

## 21. World / Autonomous Action

Action dapat berasal dari autonomous world process. Sumber tersebut harus memiliki basis yang sah.

Autonomous Action tidak boleh dibuat hanya untuk memajukan plot atau menghukum Player.

## 22. No Forced Outcome

Action Model tidak boleh mengubah Intent menjadi success secara otomatis.

```text
INTENT
≠
GUARANTEED SUCCESS
```

Player agency berarti Player mengendalikan keputusan karakter, bukan hasil dunia.

## 23. Unknown / Undefined

Jika struktur, target, parameter, atau rule yang diperlukan belum diketahui:

```text
UNKNOWN / UNDEFINED
```

harus dipertahankan sampai sumber yang valid tersedia.

Action Model tidak boleh membuat default value, formula, probability, atau aturan baru hanya untuk membuat Action dapat diproses.

## 24. Provenance

Action yang menghasilkan perubahan penting harus dapat ditelusuri melalui Origin/Source yang sesuai.

Action provenance bukan pengganti State Change provenance dan tidak mengambil alih semantics State & History.

## 25. Relationship to Result and State Change

```text
ACTION
↓
RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
```

Action Model tidak boleh membuat State Change hanya karena Action telah dibuat atau divalidasi.

## 26. Error vs Gameplay Failure

Action dapat menghasilkan:

```text
VALID ACTION → FAILURE RESULT
```

Ini berbeda dari:

```text
ACTION / INPUT INVALID
```

dan berbeda pula dari:

```text
RESOLUTION UNRESOLVED
```

Perbedaan tersebut harus dipertahankan oleh Runtime.

## 27. Domain Extension

Domain system boleh memperluas Action dengan field yang diperlukan, selama tidak mengambil alih canonical Action identity atau melanggar ownership.

Contoh:

```text
COMBAT ACTION
TRAVEL ACTION
LEGAL ACTION
SOCIAL ACTION
MAGIC ACTION
```

Ekstensi tersebut tetap menggunakan Action contract generik sebagai fondasi.

## 28. Runtime Integration

```text
PLAYER / NPC / WORLD INPUT
↓
INTENT
↓
ACTION MODEL
↓
ACTION VALIDATION
↓
RESOLUTION ARCHITECTURE
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

## 29. Integrity Rules

- Intent ≠ Action ≠ Result ≠ State Change.
- Action tidak menjamin success.
- Validation tidak menjamin success.
- Action ID bukan State Change ID.
- Target reference bukan bukti ownership atau State Change.
- NPC Behavior tetap memiliki action selection authority.
- Domain systems tetap memiliki resolution authority masing-masing.
- Action Model tidak memiliki universal gameplay formula.
- Action Model tidak menetapkan duration universal.
- Working State bukan persistence final.
- Unknown/Undefined tidak boleh diisi dengan fallback.
- Autonomous Action harus memiliki basis yang sah.
- Narrative tidak menjadi Action atau State hanya karena ditulis.
- Action harus dapat ditelusuri ke Resolution dan State Change ketika relevan.
- Invalid Action tidak boleh diperlakukan sebagai resolved success.
- Gameplay failure tidak boleh disamakan dengan engine/resolution error.

## 30. Dependencies

Action Model bergantung pada:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
characters/CHARACTER_DATA_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
world/OTHER_WORLD_SYSTEMS.md
```

Domain systems menggunakan Action Model sebagai infrastructure dan tetap menjadi owner resolution domain masing-masing.

## 31. Future Extensions

```text
ACTION SERIALIZATION
ACTION QUEUE IMPLEMENTATION
CONCURRENCY MODEL
CANCELLATION PROTOCOL
ADVANCED ACTION COMPOSITION
ACTION REPLAY / AUDIT IMPLEMENTATION
```

Ekstensi tersebut tidak boleh mengubah canonical boundary v0.1.
