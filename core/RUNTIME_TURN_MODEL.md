# Eldoria World — Runtime / Turn Model v0.1

> **Module:** Runtime / Turn Model  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Runtime / Turn Model mendefinisikan bagaimana Eldoria memproses satu Player Message menjadi satu Turn simulasi yang terstruktur.

Modul ini menghubungkan:

```text
CHARACTER
↓
CURRENT STATE
↓
PLAYER MESSAGE
↓
INTENT
↓
ACTION MODEL
↓
ACTION VALIDATION
↓
RESOLUTION ARCHITECTURE
↓
DOMAIN RESOLUTION
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
VERIFICATION
↓
RESPONSE
```

Modul ini menetapkan pipeline dan prinsip runtime, bukan mekanik khusus seperti combat, magic, ekonomi, kalender, atau durasi action.

## 2. Runtime Authority

Runtime harus mengikuti authority boundary Eldoria:

```text
ADMIN
└── Repository / Canon

AI GM
└── Simulation / Resolution / NPC / World / Events

PLAYER
└── Character decisions / intent
```

AI GM menjalankan simulasi berdasarkan Canon dan State yang tersedia. Player menentukan keputusan dan intent karakter, tetapi tidak menentukan hasil simulasi.

## 3. Turn Definition

**Satu Player Message = satu Turn.**

Satu Turn dapat berisi:

- nol action;
- satu action;
- beberapa action yang dapat diproses secara berurutan.

Player Message tidak selalu merupakan action. Message dapat berisi dialogue, question, description, meta request, atau kombinasi beberapa unsur.

Runtime harus terlebih dahulu memahami isi message sebelum menentukan apakah terdapat action yang perlu di-resolve.

## 4. Runtime Pipeline

Pipeline minimum:

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
14. CREATE HISTORY
15. PERSIST
16. VERIFY PERSISTENCE
17. GENERATE RESPONSE
18. END TURN
```

Setiap tahap harus selesai atau menghasilkan status yang jelas sebelum tahap berikutnya bergantung padanya.

## 5. Boot / Load Context

Sebelum memproses Turn, AI GM harus memuat konteks yang relevan dari Repository.

Prinsip:

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

AI GM tidak wajib memuat seluruh Repository atau seluruh History pada setiap Turn.

Konteks minimum harus cukup untuk:

- mengidentifikasi karakter;
- mengetahui Current State yang berlaku;
- mengetahui Canon yang relevan;
- mengambil History yang relevan ketika diperlukan untuk resolution atau continuity.

Jika data penting tidak tersedia, AI GM tidak boleh menggantinya dengan asumsi sebagai fakta Canon.

## 6. Read Current State

Current State adalah baseline operasional Turn.

Sebelum action diproses, runtime harus menggunakan State yang telah divalidasi sebagai kondisi awal.

Jika ditemukan konflik atau ketidakkonsistenan pada State yang diperlukan, runtime tidak boleh diam-diam memilih nilai. Konflik harus diperlakukan sebagai integrity issue sesuai State & History Model dan State Validation.

## 7. Receive & Parse Player Message

Runtime menerima satu Player Message sebagai input Turn.

Parsing bertujuan memisahkan unsur yang relevan, misalnya:

```text
PLAYER MESSAGE
├── Intent
├── Action(s)
├── Dialogue
├── Question
├── Description
└── Meta / System Request
```

Tidak semua unsur harus menghasilkan simulasi.

Narasi yang ditulis Player tidak otomatis menjadi fakta State. Fakta yang mengubah State harus melewati resolution dan State Validation.

## 8. Intent vs Action vs Result

Intent menyatakan apa yang ingin dilakukan. Action adalah representasi terstruktur yang diproses Runtime. Result adalah outcome yang dihasilkan Resolution.

```text
INTENT
≠
ACTION
≠
RESULT
≠
STATE CHANGE
```

Action Model menjadi canonical contract untuk representasi Action. Runtime tidak boleh langsung menulis New State berdasarkan keberadaan intent.

## 9. Action Model

Action yang teridentifikasi diproses melalui `core/ACTION_MODEL.md`.

Secara konseptual:

```text
ACTION
├── Action ID
├── Actor / Source
├── Intent Reference
├── Target(s) / Subject(s)
├── Context
├── Input / Parameters
├── Relevant State References
├── Temporal / Knowledge Context
├── Dependencies / Sequence Reference
└── Origin / Source
```

Action ID harus memungkinkan resolution dan perubahan terkait ditelusuri bila diperlukan.

## 10. Action Validation

Sebelum resolution, runtime harus memeriksa apakah action dapat diproses berdasarkan:

- Current State;
- Canon yang relevan;
- lokasi dan konteks;
- kondisi karakter;
- kemampuan/data yang memang tersedia;
- target;
- aturan sistem yang relevan;
- constraint lain yang sah;
- dependency atau sequence yang berlaku.

Validation menjawab apakah Action dapat diproses secara sah, bukan apakah Action pasti berhasil.

Invalid Action tidak boleh diperlakukan sebagai normal resolved success.

## 11. Resolution Architecture

Action yang valid diserahkan kepada `core/RESOLUTION_ARCHITECTURE.md`.

```text
VALID ACTION
↓
RESOLUTION REQUEST
↓
RELEVANT DOMAIN RESOLUTION
↓
RESULT
```

Resolution Architecture menyediakan kontrak generic. Domain system tetap menjadi canonical owner untuk resolution masing-masing.

Contoh:

```text
COMBAT ACTION → COMBAT
TRAVEL ACTION → TRAVEL & MOVEMENT
LEGAL ACTION → LAW
RELATIONSHIP ACTION → RELATIONSHIPS
REPUTATION ACTION → REPUTATION
NPC ACTION SELECTION → NPC BEHAVIOR & AGENCY
```

Runtime tidak boleh menciptakan formula atau mekanik Canon secara spontan ketika domain yang diperlukan belum didefinisikan.

## 12. Resolution Result

Result harus dibedakan dari Action dan State Change.

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

`FAILURE` adalah gameplay outcome yang sah. `UNRESOLVED` berarti outcome yang sah belum dapat ditentukan karena rule/data yang diperlukan belum tersedia. Keduanya tidak boleh dicampur.

## 13. Sequential Actions

Jika satu Player Message mengandung beberapa action, action yang saling bergantung diproses secara berurutan.

```text
ACTION A
↓
RESULT A
↓
UPDATED WORKING STATE
↓
ACTION B
↓
RESULT B
```

Action berikutnya harus menggunakan kondisi yang benar-benar berlaku setelah action sebelumnya.

Jika action sebelumnya gagal, diblokir, atau terinterupsi, action berikutnya tidak otomatis dianggap berhasil atau tetap terjadi. Runtime harus menentukan kelanjutannya berdasarkan hasil dan aturan yang relevan.

## 14. Working State

Selama satu Turn dengan beberapa action, runtime dapat menggunakan **Working State** sebagai representasi sementara setelah setiap resolution.

Working State bukan persistence final.

```text
CURRENT STATE
↓
WORKING STATE
↓
ACTION / RESOLUTION
↓
WORKING STATE
↓
...
↓
VALIDATE FINAL STATE CHANGES
↓
PERSIST
↓
VERIFY
```

Working State memungkinkan action yang berurutan melihat hasil action sebelumnya tanpa menganggap perubahan yang belum tervalidasi sebagai persistence final.

## 15. Consequence Calculation

Setelah resolution, runtime menghitung konsekuensi yang sah.

Konsekuensi dapat memengaruhi:

- karakter;
- NPC;
- lokasi;
- resources;
- relationships;
- reputation;
- legal state;
- event;
- world conditions;
- entity lain yang relevan.

Konsekuensi dapat langsung atau tertunda.

Konsekuensi harus memiliki dasar dari resolution, Canon, State, atau sistem terkait dan tidak boleh dibuat semata-mata untuk menghukum atau menyenangkan Player.

## 16. State Change Generation

State Change dihasilkan dari hasil resolution dan consequence calculation.

```text
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE(S)
```

Setiap perubahan harus dapat dikaitkan dengan target dan nilai sebelum/sesudahnya.

State Change harus mengikuti struktur dan integrity rules pada `state/STATE_AND_HISTORY_MODEL.md`.

## 17. State Change Validation

Sebelum diterapkan, State Change harus diproses melalui canonical `core/STATE_VALIDATION.md`.

Minimal:

- target/subject benar;
- Previous Value cocok dengan State yang menjadi baseline;
- New Value sesuai hasil resolution;
- Canon yang relevan tidak dilanggar;
- Origin/Source tersedia jika diperlukan;
- tidak menghasilkan konflik internal yang diketahui;
- perubahan dapat direkonsiliasi dengan History.

Jika beberapa perubahan saling bergantung, perubahan tersebut divalidasi sebagai Change Set sesuai State Validation.

State Change atau Change Set yang gagal validasi tidak boleh dianggap sebagai perubahan final.

## 18. Atomicity of Interdependent Changes

Jika satu resolution menghasilkan beberapa State Changes yang saling bergantung, runtime harus memperlakukan rangkaian tersebut sebagai satu hasil terintegrasi untuk tujuan validasi dan persistence.

```text
GENERATE ALL RELATED CHANGES
↓
VALIDATE AS A SET
↓
PERSIST AS INTEGRATED RESULT
↓
VERIFY
```

Detail transaction mechanism, rollback, dan storage implementation mengikuti boundary `core/PERSISTENCE.md` dan belum ditentukan secara teknis oleh v0.1.

## 19. History Creation

Setelah State Changes tervalidasi dan diterapkan sesuai Persistence architecture, runtime membuat atau mempertahankan History Record untuk perubahan yang memang membutuhkan persistence history.

History harus menghubungkan perubahan dengan:

- waktu;
- subject/target;
- previous/new state atau value;
- cause;
- origin;
- source;
- consequence;
- record type.

History bukan narrative response. Narrative dibuat setelah proses State/History selesai atau setelah status persistence diketahui.

## 20. Time Advancement

Action atau event dapat menyebabkan waktu dunia berubah jika sistem yang relevan mengaturnya.

Runtime v0.1 **tidak menetapkan durasi universal untuk Turn atau action**.

Jika sistem waktu belum memberikan mekanisme atau sumber waktu yang sah, runtime tidak boleh mengarang durasi atau World Time.

Perubahan waktu yang memang terjadi harus diperlakukan sebagai State Change yang tervalidasi bila sistem mendefinisikannya demikian.

## 21. Autonomous World Processing

Runtime dapat memproses perubahan dunia yang bukan berasal dari Player, misalnya:

```text
NPC ACTION
EVENT
ENVIRONMENTAL PROCESS
FACTION ACTIVITY
SYSTEM PROCESS
```

Perubahan autonomous harus tetap mengikuti Canon, State, validation, resolution, provenance, dan History.

Runtime tidak boleh membuat dunia bergerak secara arbitrer hanya untuk menghasilkan cerita.

## 22. Knowledge Boundary

Resolution dan narrative harus membedakan:

- Canon Fact;
- Character Knowledge;
- Player Knowledge;
- Uncertain Information.

Player Knowledge tidak otomatis menjadi Character Knowledge.

Rumor atau informasi tidak terverifikasi tidak boleh diperlakukan sebagai fakta hanya karena diketahui Player.

## 23. No Retroactive State

Runtime tidak boleh menambahkan fakta ke masa lalu hanya karena fakta tersebut membantu resolution saat ini.

Jika suatu informasi baru ditemukan, runtime harus membedakan:

```text
WHAT WAS TRUE
vs.
WHAT IS NOW KNOWN
```

Perubahan masa lalu hanya boleh dilakukan melalui mekanisme Canon/State/History yang sah dan dapat diaudit.

## 24. Persistence

Persistence mengikuti canonical `core/PERSISTENCE.md`:

```text
VALIDATED STATE CHANGES
↓
APPLY CURRENT STATE
↓
PERSIST STATE / HISTORY
↓
VERIFY
```

Persistence hanya menerima perubahan yang memenuhi validation requirement. Invalid, conflict, atau unresolved changes tidak boleh dipersist sebagai final valid State.

Narrative tidak boleh dianggap sebagai bukti persistence.

Jika persistence gagal atau verification belum berhasil, AI GM tidak boleh menyatakan bahwa perubahan telah tersimpan secara resmi. Status persistence harus tetap dibedakan dari gameplay result.

## 25. Response Generation

Response Player dibuat setelah runtime memiliki hasil resolution dan status State/Persistence yang relevan.

Response sebaiknya membedakan secara jelas:

- apa yang Player coba lakukan;
- apa yang benar-benar terjadi;
- konsekuensi yang diketahui;
- perubahan yang relevan terhadap karakter/dunia;
- informasi yang masih tidak pasti;
- status persistence/verification jika relevan.

Narrative harus merepresentasikan hasil simulasi, bukan menentukan hasil simulasi.

## 26. Turn Completion

Satu Turn selesai setelah:

```text
INPUT
↓
INTENT / ACTION PARSED
↓
ACTION VALIDATION
↓
RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGES VALIDATED
↓
STATE / HISTORY UPDATED
↓
PERSISTENCE STATUS KNOWN
↓
VERIFICATION STATUS KNOWN
↓
RESPONSE GENERATED
```

Jika tidak ada action yang perlu di-resolve, Turn tetap dapat selesai sebagai interaction tanpa State Change.

## 27. Failed / Blocked / Interrupted Turn

Turn tidak dianggap gagal hanya karena action gagal.

Failure adalah hasil simulasi yang valid.

Jika action gagal, runtime tetap harus menentukan apakah terdapat:

- State Change lain yang sah;
- waktu yang berlalu;
- konsekuensi;
- History Record yang relevan;
- atau tidak ada perubahan sama sekali.

Semua keputusan tersebut harus berasal dari aturan dan konteks yang relevan.

## 28. Integrity Rules

- Satu Player Message = satu Turn.
- Satu Turn dapat memiliki nol atau beberapa action.
- Intent ≠ Action ≠ Result ≠ State Change.
- Action yang saling bergantung diproses berurutan.
- Validation tidak menjamin keberhasilan.
- Failure, blocked, delayed, interrupted, dan unresolved adalah status yang dapat sah sesuai konteks.
- Current State harus menjadi baseline Turn.
- Working State bukan persistence final.
- State Change harus tervalidasi sebelum menjadi perubahan final.
- State Changes yang saling bergantung harus divalidasi sebagai satu hasil terintegrasi.
- Previous Value harus sesuai dengan State sebelumnya.
- History harus dapat menelusuri perubahan penting.
- Narrative bukan sumber State atau persistence.
- Autonomous world changes harus memiliki dasar yang sah.
- Unknown/Undefined tidak boleh diisi dengan asumsi.
- Runtime tidak boleh mengarang formula atau mekanik yang belum didefinisikan.
- Runtime tidak menetapkan durasi Turn universal pada v0.1.
- AI GM tidak boleh mengklaim persistence berhasil tanpa verifikasi.
- Konflik State/History tidak boleh diselesaikan diam-diam.
- State Validation tidak menentukan gameplay resolution.
- Persistence tidak memperbaiki invalid State Change secara diam-diam.
- Validation failure, persistence failure, dan verification failure harus tetap dibedakan.
- Domain systems tetap menjadi canonical owner untuk resolution masing-masing.

## 29. Dependencies

Runtime / Turn Model bergantung pada:

```text
INDEX.md
core/CORE_RULES.md
core/ACTION_MODEL.md
core/RESOLUTION_ARCHITECTURE.md
characters/CHARACTER_DATA_MODEL.md
characters/players.md
state/STATE_AND_HISTORY_MODEL.md
core/STATE_VALIDATION.md
core/PERSISTENCE.md
```

Domain systems tetap menjadi canonical owner untuk resolution masing-masing. Runtime, Action Model, Resolution Architecture, State Validation, dan Persistence tidak menggantikan ownership tersebut.

## 30. Future Extensions

Fondasi berikut dapat dikembangkan kemudian tanpa mengubah boundary v0.1:

```text
WORLD EVENT PROCESSOR
NPC / FACTION SIMULATION
SYSTEM-SPECIFIC MECHANICS
STORAGE IMPLEMENTATION
CONCURRENCY CONTROL
ADVANCED RECOVERY / TRANSACTION MECHANISMS
ACTION QUEUE IMPLEMENTATION
RESOLUTION PLUGIN CONTRACTS
RESOLUTION REPLAY / TRACE IMPLEMENTATION
```

`STATE VALIDATION` dan `PERSISTENCE` bukan lagi future extensions kosong; keduanya telah memiliki canonical architecture masing-masing.
