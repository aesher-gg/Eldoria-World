# Eldoria World — World Event Processor v0.1

> **Module:** Core Architecture — World Event Processor  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

World Event Processor mendefinisikan bagaimana Event dunia dibuat, diaktifkan, dijadwalkan bila diperlukan, dievaluasi, diproses, dan diteruskan ke resolution/domain systems tanpa mengambil alih ownership State, History, Time, atau domain-specific mechanics.

Modul ini menutup architectural gap antara:

```text
EVENT
↓
EVENT PROCESSING / ORCHESTRATION
↓
RESULT / CONSEQUENCE
↓
STATE CHANGE
```

World Event Processor adalah **orchestration layer**, bukan generator cerita acak dan bukan pemilik mekanik domain.

## 2. Canonical Boundary

World Event Processor owns:

- Event lifecycle orchestration;
- event activation and deactivation;
- event scheduling when explicitly required by Canon/context;
- trigger/context evaluation;
- event eligibility;
- event ordering and dependency handling;
- event chaining;
- dispatch to relevant resolution/domain system;
- consequence handoff;
- autonomous event processing;
- event provenance and processing references.

World Event Processor does **not** own:

- State semantics → `state/STATE_AND_HISTORY_MODEL.md`;
- History semantics → `state/STATE_AND_HISTORY_MODEL.md`;
- temporal authority → `systems/TIME_AND_CALENDAR.md`;
- generic Action structure → `core/ACTION_MODEL.md`;
- generic Result contract → `core/RESOLUTION_ARCHITECTURE.md`;
- domain-specific resolution → relevant domain system;
- State integrity → `core/STATE_VALIDATION.md`;
- persistence → `core/PERSISTENCE.md`.

## 3. Event vs State Change

```text
EVENT
= kejadian / proses yang diproses dalam simulasi

STATE CHANGE
= perubahan konkret pada State akibat sebab yang sah
```

Satu Event dapat menghasilkan nol, satu, atau beberapa State Changes. Event tidak otomatis berarti State berubah.

Event juga tidak sama dengan narrative response.

## 4. Event Lifecycle

Lifecycle konseptual:

```text
DEFINED / IDENTIFIED
↓
ELIGIBLE?
↓
TRIGGERED / ACTIVATED
↓
CONTEXT EVALUATION
↓
PROCESSING
↓
RESOLUTION / DOMAIN HANDOFF
↓
CONSEQUENCES
↓
STATE CHANGE(S)
↓
VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
↓
COMPLETED / CONTINUING / INTERRUPTED
```

Lifecycle tidak harus menggunakan semua status untuk setiap Event.

## 5. Event Identity and Context

Event yang perlu ditelusuri sebaiknya memiliki konteks yang cukup untuk mengidentifikasi:

```text
Event ID
Event Type / Classification
World Time / Temporal Reference
Geographic / Location Context
Trigger / Cause
Affected Entity / Population
Relevant State References
Relevant History References
Dependencies
Origin / Source
Processing Status
```

Field spesifik tetap mengikuti domain atau data model yang relevan. Tidak ada daftar field universal yang memaksa semua Event memiliki struktur identik.

## 6. Event Eligibility

Event hanya diproses jika terdapat basis yang sah, misalnya:

- kondisi State;
- perubahan State sebelumnya;
- event lain;
- tindakan Player/NPC/Faction;
- kondisi lingkungan;
- kondisi ekonomi/politik/ekologi;
- temporal condition yang memang didefinisikan;
- Canon-specific trigger;
- sumber lain yang valid.

```text
VALID WORLD BASIS
↓
EVENT ELIGIBILITY
↓
EVENT PROCESSING
```

Tidak ada universal event probability, event frequency, importance score, urgency score, atau random-spawn fallback dalam v0.1.

## 7. Event Triggering

Trigger dapat bersifat:

- state-driven;
- action-driven;
- consequence-driven;
- event-driven;
- context-driven;
- time-driven jika Canon memerlukannya.

Time-driven tidak berarti adanya universal simulation tick.

Jika trigger requirement tidak dapat ditentukan dari Canon/data yang tersedia, Event tetap `UNRESOLVED` dan tidak boleh dipaksa aktif dengan asumsi.

## 8. Scheduling

Event dapat memiliki scheduled processing apabila Canon atau konteks menyediakan waktu yang sah.

World Event Processor tidak menetapkan universal:

```text
EVENT CHECK = setiap X menit
EVENT TICK = setiap X jam
```

`TIME & CALENDAR` tetap menjadi canonical temporal authority. Scheduler hanya mengorkestrasi waktu yang telah ditentukan secara sah.

## 9. Event Processing

Processing minimum:

```text
IDENTIFY EVENT
↓
LOAD RELEVANT CONTEXT
↓
VALIDATE ELIGIBILITY
↓
EVALUATE TRIGGER / CONDITIONS
↓
DETERMINE PROCESSING PATH
↓
HAND OFF TO ACTION / RESOLUTION / DOMAIN WHEN REQUIRED
↓
COLLECT RESULT
↓
HAND OFF CONSEQUENCES
↓
GENERATE PROPOSED STATE CHANGES
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
```

Processor mengorkestrasi proses; processor tidak menentukan outcome domain sendiri.

## 10. Domain Delegation

Contoh:

```text
Combat-related Event → COMBAT
Travel-related Event → TRAVEL & MOVEMENT
Legal Event → LAW
Relationship Event → RELATIONSHIPS
Economic Event → ECONOMY
Ecological Event → CREATURES / ECOLOGY
Supernatural Event → SUPERNATURAL / MAGIC
```

Event dapat melibatkan lebih dari satu domain. Setiap domain tetap mempertahankan ownership atas mekanik dan resolution-nya.

## 11. Event Chaining

Satu Event dapat menyebabkan Event lain apabila hubungan sebab-akibatnya sah:

```text
EVENT A
↓
RESULT / CONSEQUENCE
↓
TRIGGER CONDITION
↓
EVENT B
```

Chaining harus:

- dapat ditelusuri;
- memiliki basis sebab-akibat;
- menghormati temporal ordering;
- tidak membuat loop tanpa kondisi penghentian yang sah;
- tidak mengisi data yang Unknown/Undefined dengan asumsi.

Tidak ada universal chain depth atau event propagation multiplier.

## 12. Autonomous World Events

World Event Processor mendukung Event yang terjadi tanpa input langsung Player.

Contoh sumber:

```text
NPC
FACTION
ENVIRONMENT
ECONOMY
POLITICS
ECOLOGY
SUPERNATURAL PROCESS
OTHER VALID WORLD PROCESS
```

Autonomous ≠ arbitrary.

```text
VALID BASIS
↓
ELIGIBILITY
↓
PROCESS
↓
CONSEQUENCE
↓
VALIDATED STATE CHANGE
```

## 13. Event and Action

Event dapat:

- terjadi sebagai proses dunia;
- menghasilkan Action;
- dipicu oleh Action;
- menghasilkan konsekuensi yang memicu Action lain.

Tetapi:

```text
EVENT ≠ ACTION
```

Jika Event menghasilkan Action, Action tersebut harus menggunakan `core/ACTION_MODEL.md` dan resolution yang relevan.

## 14. Event and Resolution

World Event Processor menggunakan `core/RESOLUTION_ARCHITECTURE.md` ketika Event membutuhkan resolution.

```text
EVENT
↓
PROCESSING CONTEXT
↓
RESOLUTION REQUEST / ACTION
↓
DOMAIN RESOLUTION
↓
RESULT
↓
CONSEQUENCES
```

Processor tidak menciptakan universal formula atau probabilitas.

## 15. State and History Integration

Event yang menghasilkan State Change harus mengikuti State & History Model.

Minimum provenance harus dapat menjawab:

```text
WHAT EVENT?
WHY?
WHEN?
WHO / WHAT WAS AFFECTED?
WHAT RESULTED?
WHAT STATE CHANGED?
WHAT SOURCE / ORIGIN SUPPORTS IT?
```

Event record dan History Record tidak boleh dianggap identik secara otomatis.

## 16. Validation and Persistence

Proposed State Changes dari Event harus melewati:

```text
EVENT RESULT
↓
STATE CHANGE(S)
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
```

Interdependent changes diperlakukan sebagai Change Set sesuai State Validation dan Persistence.

Event Processor tidak boleh menyatakan State telah tersimpan hanya karena processing atau narrative berhasil.

## 17. Unknown / Unresolved

Jika Event memerlukan rule, trigger, waktu, data, atau domain mechanic yang belum didefinisikan:

```text
UNKNOWN / UNDEFINED
→ remain unknown

INSUFFICIENT RESOLUTION BASIS
→ UNRESOLVED
```

Jangan mengganti kekosongan dengan default numerik, random value, atau asumsi narrative.

## 18. Conflicts

Jika Event processing menemukan konflik State, temporal ordering, dependency, atau provenance:

```text
DETECT
↓
PRESERVE TRACEABILITY
↓
VALIDATE SOURCE / CONTEXT
↓
RESOLVE ONLY THROUGH VALID CANON / CORRECTION MECHANISM
```

Conflict tidak boleh diselesaikan diam-diam.

## 19. Runtime Integration

World Event Processor berada di antara generic runtime infrastructure dan domain processing:

```text
RUNTIME
↓
EVENT IDENTIFICATION / ORCHESTRATION
↓
WORLD EVENT PROCESSOR
↓
ACTION / RESOLUTION ARCHITECTURE
↓
DOMAIN SYSTEM
↓
STATE VALIDATION
↓
PERSISTENCE
↓
VERIFICATION
```

World Event Processor juga dapat menerima Event yang berasal dari domain process dan meneruskannya sebagai trigger bagi proses berikutnya.

## 20. Event Processing Status

Status konseptual:

```text
IDENTIFIED
ELIGIBLE
ACTIVATED
PROCESSING
RESOLVED
BLOCKED
DELAYED
INTERRUPTED
UNRESOLVED
COMPLETED
CONTINUING
```

Status digunakan sesuai kebutuhan; tidak semua Event harus melewati semua status.

## 21. Integrity Rules

- Event ≠ State Change.
- Event ≠ Action.
- Event ≠ narrative.
- Event processing membutuhkan basis yang sah.
- Domain system tetap menjadi owner domain resolution.
- Time & Calendar tetap menjadi temporal authority.
- State Validation tetap menjadi integrity gate.
- Persistence tetap menjadi save authority.
- Autonomous Event tidak boleh menjadi random story generator.
- Tidak ada universal event tick, frequency, probability, importance score, urgency score, atau propagation multiplier.
- Unknown/Undefined tidak boleh diisi dengan asumsi.
- Event chain harus traceable dan memiliki basis sebab-akibat.
- Conflict tidak boleh diselesaikan diam-diam.
- AI GM tidak boleh mengklaim persistence tanpa verification.
