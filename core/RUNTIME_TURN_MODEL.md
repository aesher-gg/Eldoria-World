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
ACTION / INTENT
↓
VALIDATION
↓
RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGE
↓
HISTORY
↓
PERSISTENCE
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
5. IDENTIFY ACTION / INTENT
6. VALIDATE
7. RESOLVE
8. CALCULATE CONSEQUENCES
9. GENERATE STATE CHANGES
10. VALIDATE STATE CHANGES
11. APPLY STATE
12. CREATE HISTORY
13. PERSIST
14. VERIFY PERSISTENCE
15. GENERATE RESPONSE
16. END TURN
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

Jika ditemukan konflik atau ketidakkonsistenan pada State yang diperlukan, runtime tidak boleh diam-diam memilih nilai. Konflik harus diperlakukan sebagai integrity issue sesuai State & History Model.

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

Narasi yang ditulis Player tidak otomatis menjadi fakta State. Fakta yang mengubah State harus melewati resolution dan validation.

## 8. Intent vs Result

Intent hanya menyatakan apa yang ingin dilakukan Player.

```text
INTENT
≠
RESULT
≠
STATE CHANGE
```

Contoh konseptual:

```text
Player: "Aku mencoba membuka pintu."

Intent: membuka pintu
Result: ditentukan oleh resolution
State Change: hanya diterapkan jika hasilnya memang menyebabkan perubahan State
```

AI GM tidak boleh langsung menulis New State berdasarkan keberadaan intent.

## 9. Action Identification

Setiap action yang teridentifikasi harus memiliki konteks yang cukup untuk divalidasi.

Secara konseptual:

```text
Action
├── Action ID
├── Actor
├── Intent
├── Target (jika ada)
├── Context
└── Input / Parameters
```

Struktur ini bersifat konseptual dan dapat diperluas oleh sistem tertentu.

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
- constraint lain yang sah.

Validation tidak menjamin keberhasilan action.

Validation menjawab apakah action dapat diproses secara sah, bukan apakah action pasti berhasil.

## 11. Resolution

Resolution menentukan hasil action berdasarkan Canon, State, konteks, dan mekanik sistem yang relevan.

Hasil dapat berupa:

- success;
- partial success;
- failure;
- blocked;
- delayed;
- interrupted;
- atau hasil lain yang sah menurut sistem terkait.

Runtime tidak boleh memaksakan hasil tertentu hanya demi kebutuhan naratif.

Jika sistem yang diperlukan untuk melakukan resolution belum didefinisikan, runtime tidak boleh menciptakan formula atau mekanik Canon secara spontan.

## 12. Sequential Actions

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

## 13. Working State

Selama satu Turn dengan beberapa action, runtime dapat menggunakan **Working State** sebagai representasi sementara setelah setiap resolution.

Working State bukan persistence final.

Prinsip:

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
```

Working State memungkinkan action yang berurutan melihat hasil action sebelumnya tanpa menganggap perubahan yang belum tervalidasi sebagai persistence final.

## 14. Consequence Calculation

Setelah resolution, runtime menghitung konsekuensi yang sah.

Konsekuensi dapat memengaruhi:

- karakter;
- NPC;
- lokasi;
- resources;
- relationships;
- event;
- world conditions;
- entity lain yang relevan.

Konsekuensi dapat langsung atau tertunda.

Konsekuensi harus memiliki dasar dari resolution, Canon, State, atau sistem terkait dan tidak boleh dibuat semata-mata untuk menghukum atau menyenangkan Player.

## 15. State Change Generation

State Change dihasilkan dari hasil resolution dan consequence calculation.

```text
RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGE(S)
```

Setiap perubahan harus dapat dikaitkan dengan target dan nilai sebelum/sesudahnya.

State Change harus mengikuti struktur dan integrity rules pada `state/STATE_AND_HISTORY_MODEL.md`.

## 16. State Change Validation

Sebelum diterapkan, State Change harus divalidasi.

Minimal:

- target/subject benar;
- Previous Value cocok dengan State yang menjadi baseline;
- New Value sesuai hasil resolution;
- Canon yang relevan tidak dilanggar;
- Origin/Source tersedia jika diperlukan;
- tidak menghasilkan konflik internal yang diketahui;
- perubahan dapat direkonsiliasi dengan History.

State Change yang gagal validasi tidak boleh dianggap sebagai perubahan final.

## 17. Atomicity of Interdependent Changes

Jika satu resolution menghasilkan beberapa State Changes yang saling bergantung, runtime harus memperlakukan rangkaian tersebut sebagai satu hasil terintegrasi untuk tujuan validasi dan persistence.

Prinsip:

```text
GENERATE ALL RELATED CHANGES
↓
VALIDATE AS A SET
↓
APPLY TOGETHER
↓
PERSIST
```

Tujuannya mencegah State setengah diterapkan ketika salah satu perubahan wajib ternyata invalid.

Detail transaction mechanism akan ditetapkan oleh modul Persistence/Integrity di masa depan.

## 18. History Creation

Setelah State Changes tervalidasi dan diterapkan, runtime membuat History Record untuk perubahan yang memang membutuhkan persistence history.

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

## 19. Time Advancement

Action atau event dapat menyebabkan waktu dunia berubah jika sistem yang relevan mengaturnya.

Runtime v0.1 **tidak menetapkan durasi universal untuk Turn atau action**.

Jika sistem waktu belum memberikan mekanisme atau sumber waktu yang sah, runtime tidak boleh mengarang durasi atau World Time.

Perubahan waktu yang memang terjadi harus diperlakukan sebagai State Change yang tervalidasi bila sistem mendefinisikannya demikian.

## 20. Autonomous World Processing

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

## 21. Knowledge Boundary

Resolution dan narrative harus membedakan:

- Canon Fact;
- Character Knowledge;
- Player Knowledge;
- Uncertain Information.

Player Knowledge tidak otomatis menjadi Character Knowledge.

Rumor atau informasi tidak terverifikasi tidak boleh diperlakukan sebagai fakta hanya karena diketahui Player.

## 22. No Retroactive State

Runtime tidak boleh menambahkan fakta ke masa lalu hanya karena fakta tersebut membantu resolution saat ini.

Jika suatu informasi baru ditemukan, runtime harus membedakan:

```text
WHAT WAS TRUE
vs.
WHAT IS NOW KNOWN
```

Perubahan masa lalu hanya boleh dilakukan melalui mekanisme Canon/State/History yang sah dan dapat diaudit.

## 23. Persistence

Persistence mengikuti prinsip:

```text
VALIDATED STATE CHANGES
↓
APPLY CURRENT STATE
↓
CREATE HISTORY
↓
PERSIST
↓
VERIFY
```

Narrative tidak boleh dianggap sebagai bukti persistence.

Jika persistence gagal atau belum diverifikasi, AI GM tidak boleh menyatakan bahwa perubahan telah tersimpan secara resmi.

Status kegagalan persistence harus dipertahankan untuk ditangani oleh mekanisme Persistence/Integrity yang akan didefinisikan kemudian.

## 24. Response Generation

Response Player dibuat setelah runtime memiliki hasil resolution dan status State/Persistence yang relevan.

Response sebaiknya membedakan secara jelas:

- apa yang Player coba lakukan;
- apa yang benar-benar terjadi;
- konsekuensi yang diketahui;
- perubahan yang relevan terhadap karakter/dunia;
- informasi yang masih tidak pasti.

Narrative harus merepresentasikan hasil simulasi, bukan menentukan hasil simulasi.

## 25. Turn Completion

Satu Turn selesai setelah:

```text
INPUT
↓
ACTION / INTENT PARSED
↓
VALIDATION
↓
RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGES VALIDATED
↓
STATE / HISTORY UPDATED
↓
PERSISTENCE STATUS KNOWN
↓
RESPONSE GENERATED
```

Jika tidak ada action yang perlu di-resolve, Turn tetap dapat selesai sebagai interaction tanpa State Change.

## 26. Failed / Blocked / Interrupted Turn

Turn tidak dianggap gagal hanya karena action gagal.

Failure adalah hasil simulasi yang valid.

Jika action gagal, runtime tetap harus menentukan apakah terdapat:

- State Change lain yang sah;
- waktu yang berlalu;
- konsekuensi;
- History Record yang relevan;
- atau tidak ada perubahan sama sekali.

Semua keputusan tersebut harus berasal dari aturan dan konteks yang relevan.

## 27. Integrity Rules

- Satu Player Message = satu Turn.
- Satu Turn dapat memiliki nol atau beberapa action.
- Action yang saling bergantung diproses berurutan.
- Intent tidak sama dengan Result.
- Validation tidak menjamin keberhasilan.
- Failure, blocked, delayed, dan interrupted adalah hasil yang sah.
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

## 28. Dependencies

Runtime / Turn Model bergantung pada:

```text
INDEX.md
core/CORE_RULES.md
characters/CHARACTER_DATA_MODEL.md
characters/players.md
state/STATE_AND_HISTORY_MODEL.md
```

Sistem berikutnya dapat memperluas Runtime melalui modul khusus tanpa menghapus prinsip inti modul ini.

## 29. Future Extensions

Modul berikut dapat didefinisikan kemudian:

```text
ACTION MODEL
RESOLUTION SYSTEMS
TIME SYSTEM
PERSISTENCE / SAVE PIPELINE
INTEGRITY / VALIDATOR
WORLD EVENT PROCESSOR
NPC / FACTION SIMULATION
SYSTEM-SPECIFIC MECHANICS
```

Ekstensi tidak boleh mengubah aturan Runtime secara diam-diam. Konflik atau kebutuhan pengecualian harus menjadi perubahan Canon eksplisit.
