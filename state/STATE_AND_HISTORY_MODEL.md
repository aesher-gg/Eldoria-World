# Eldoria World — State & History Model v0.1

> **Module:** State & History Model  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

State & History Model mendefinisikan fondasi data untuk **persistent world** Eldoria.

Modul ini menetapkan bagaimana kondisi dunia dan karakter direpresentasikan, bagaimana perubahan dicatat, bagaimana asal perubahan ditelusuri, dan bagaimana Current State tetap dapat diaudit melalui History.

Modul ini mendefinisikan struktur dan prinsip integritas. Modul ini **belum** menetapkan atribut karakter, formula combat, ekonomi, magic, durasi action, atau mekanik sistem dunia tertentu.

## 2. Core Principle

Eldoria menggunakan tiga konsep yang saling berhubungan tetapi tidak boleh dicampur:

```text
CANON
├── Aturan / fakta resmi
│
STATE
├── Kondisi yang berlaku sekarang
│
HISTORY
└── Rekam kejadian / perubahan yang menjelaskan bagaimana State terbentuk
```

Repository adalah Official Canon + Persistent State Source.

State menjawab:

> **"Apa kondisinya sekarang?"**

History menjawab:

> **"Bagaimana kondisi itu menjadi seperti sekarang?"**

Canon menjawab:

> **"Aturan atau fakta resmi apa yang menjadi dasar?"**

Ketiganya tidak boleh diperlakukan sebagai data yang sama.

## 3. State Scope

State dapat dimiliki oleh berbagai subject yang relevan terhadap simulasi, termasuk:

- Character;
- NPC;
- lokasi;
- organisasi/faction;
- property atau aset;
- event yang sedang aktif;
- kondisi dunia;
- entitas lain yang memang membutuhkan persistence.

Tidak semua entitas harus memiliki State terpisah. State hanya dibuat ketika suatu kondisi perlu diketahui, divalidasi, atau dipertahankan oleh runtime.

## 4. World State vs Character State

### World State

Merepresentasikan kondisi dunia yang berlaku pada suatu waktu.

Contoh kategori konseptual:

- world time;
- kondisi lingkungan;
- event aktif;
- kondisi lokasi;
- kondisi sosial/politik;
- kondisi ekonomi;
- status faction atau organisasi;
- perubahan dunia lain yang relevan.

Field final ditentukan oleh modul sistem yang relevan.

### Character State

Merepresentasikan kondisi terkini karakter.

Contoh kategori konseptual:

- current location;
- kondisi fisik;
- resources;
- equipment aktif;
- possessions;
- relationships aktif;
- effects/conditions;
- status gameplay.

Struktur Character State harus kompatibel dengan Character Data Model.

## 5. Starting State vs Current State

### Starting State

Starting State adalah snapshot resmi kondisi karakter ketika karakter memasuki gameplay.

Starting State:

- dibuat dan divalidasi sebelum gameplay;
- menjadi baseline historis karakter;
- tidak ditimpa oleh perkembangan gameplay;
- tetap dapat dirujuk untuk mengetahui kondisi awal.

### Current State

Current State adalah snapshot kondisi karakter yang berlaku sekarang.

Current State:

- berasal dari Starting State dan perubahan yang tervalidasi;
- menjadi dasar Turn berikutnya;
- dapat berubah selama gameplay;
- harus konsisten dengan State Changes yang diterapkan.

Prinsip:

```text
STARTING STATE
      ↓
VALIDATED STATE CHANGES
      ↓
CURRENT STATE
```

Starting State dan Current State tidak boleh diperlakukan sebagai satu field yang dapat saling menimpa.

## 6. State Snapshot

State Snapshot adalah representasi kondisi yang berlaku pada suatu titik waktu.

Secara konseptual:

```text
State Snapshot
├── State ID / Snapshot Reference
├── Subject ID
├── State Type
├── World Time
├── Current Values
├── Version / Revision
└── Validation Status
```

Field tersebut adalah struktur konseptual. Sistem tertentu dapat menambahkan field sesuai kebutuhan tanpa melanggar prinsip State & History.

State Snapshot harus menggambarkan kondisi yang benar-benar berlaku, bukan rencana, intent, rumor, atau hasil yang belum tervalidasi.

## 7. State Change

State Change adalah perubahan terverifikasi dari satu State menuju State berikutnya.

Struktur minimum konseptual:

```text
State Change
├── Change ID
├── Target / Subject ID
├── Field / Property
├── Previous Value
├── New Value
├── Origin
├── Source
├── World Time
└── Validation Status
```

### Previous Value

Nilai yang berlaku sebelum perubahan.

### New Value

Nilai yang berlaku setelah perubahan berhasil diterapkan.

### Origin

Asal perubahan, misalnya action Player, action NPC, event, system process, environmental change, atau sumber valid lain yang ditentukan sistem.

### Source

Referensi yang menjelaskan dasar perubahan, seperti action/event ID, aturan Canon, system process, atau sumber data lain yang relevan.

State Change tidak boleh hanya menyatakan bahwa suatu perubahan terjadi tanpa dasar yang dapat ditelusuri ketika traceability diperlukan.

## 8. State Change Lifecycle

State Change mengikuti prinsip:

```text
CAUSE / EVENT / ACTION
        ↓
VALIDATE
        ↓
RESOLVE
        ↓
CALCULATE CONSEQUENCES
        ↓
GENERATE STATE CHANGE
        ↓
VALIDATE STATE CHANGE
        ↓
APPLY
        ↓
CURRENT STATE
        ↓
HISTORY RECORD
```

State Change tidak boleh diterapkan hanya karena Player menyatakan intent atau karena AI GM telah menuliskan hasil dalam narrative.

## 9. Event vs State Change

**Event** dan **State Change** adalah konsep berbeda.

### Event

Event adalah kejadian yang menjadi bagian dari simulasi dan dapat menyebabkan satu atau beberapa perubahan.

### State Change

State Change adalah perubahan konkret pada data State sebagai akibat dari action, event, system process, atau sebab valid lainnya.

Satu event dapat menghasilkan:

```text
EVENT
├── State Change A
├── State Change B
└── State Change C
```

Sebaliknya, suatu State Change dapat berasal dari proses sistem yang tidak direpresentasikan sebagai event dunia terpisah, selama Origin/Source-nya sah dan dapat ditelusuri.

## 10. History Record

History Record adalah catatan persisten mengenai kejadian atau perubahan yang signifikan bagi continuity, provenance, atau audit.

Struktur minimum konseptual:

```text
History Record
├── History / Event / Change ID
├── World Time
├── Subject / Target
├── Previous State / Value
├── New State / Value
├── Cause
├── Origin
├── Source
├── Consequence
└── Record Type
```

`Record Type` dapat membedakan, misalnya, event, state change, correction, atau jenis record lain yang akan ditetapkan sistem.

History tidak harus menyimpan setiap perubahan transient yang tidak memiliki nilai continuity atau audit. Namun perubahan yang penting bagi State, continuity, atau integritas harus dapat ditelusuri.

## 11. State ↔ History Relationship

State dan History saling terkait tetapi memiliki fungsi berbeda:

```text
HISTORY
  ↓
VALIDATED CHANGES
  ↓
STATE
```

dan:

```text
CURRENT STATE
  ↓
TRACE ORIGIN
  ↓
HISTORY / SOURCE
```

Current State adalah snapshot operasional. History adalah rekam provenance/kronologi.

History tidak boleh dianggap sebagai pengganti Current State untuk kebutuhan runtime normal, dan Current State tidak boleh dianggap cukup untuk menjelaskan asal-usul perubahan penting.

## 12. Provenance / Origin

Setiap perubahan penting harus memiliki provenance yang dapat ditelusuri.

Minimal hubungan yang diharapkan:

```text
CURRENT STATE
     ↓
STATE CHANGE
     ↓
ORIGIN
     ↓
SOURCE
     ↓
HISTORY / EVENT / ACTION
```

Origin harus menjelaskan **mengapa** perubahan terjadi. Source harus menunjuk pada dasar atau record yang dapat digunakan untuk memverifikasi perubahan tersebut.

Jika suatu perubahan membutuhkan provenance tetapi Origin/Source tidak tersedia, perubahan tersebut tidak boleh dianggap tervalidasi.

## 13. History Immutability

History adalah rekam masa lalu dan tidak boleh dihapus atau ditimpa secara diam-diam untuk menghilangkan kejadian.

Jika terjadi kesalahan data atau koreksi:

```text
ORIGINAL RECORD
      ↓
CORRECTION RECORD
```

Correction Record harus menjelaskan bahwa terdapat koreksi terhadap record sebelumnya dan menjaga traceability terhadap record asli.

Current State dapat diperbaiki melalui proses yang sah, tetapi koreksi penting terhadap data historis tetap harus dapat diaudit.

## 14. State Consistency

Current State yang baru harus konsisten dengan State sebelumnya dan perubahan yang tervalidasi.

Setidaknya harus diperiksa:

- target/subject benar;
- Previous Value sesuai dengan State sebelum perubahan;
- New Value sesuai dengan hasil resolution;
- perubahan tidak melanggar Canon yang relevan;
- Origin/Source tersedia ketika diwajibkan;
- perubahan tidak menghasilkan konflik internal yang diketahui;
- State setelah perubahan dapat direkonsiliasi dengan History yang dibuat.

Jika validasi gagal, State Change tidak boleh diterapkan sebagai perubahan final.

## 15. Multiple State Changes

Satu action atau event dapat menghasilkan beberapa State Changes.

Contoh konseptual:

```text
ACTION
 ↓
RESOLUTION
 ├── Character location changes
 ├── Resource changes
 └── NPC relationship changes
```

Perubahan yang saling bergantung harus diproses dengan urutan yang konsisten.

Jika sebuah rangkaian perubahan harus diperlakukan sebagai satu hasil terintegrasi, runtime sebaiknya menerapkan validasi sebelum perubahan final dipersist agar tidak meninggalkan State setengah diterapkan.

## 16. Failed / Interrupted Actions

Action yang gagal, diblokir, tertunda, atau terinterupsi tidak otomatis menghasilkan perubahan yang dimaksud Player.

Namun action tersebut dapat menghasilkan perubahan lain yang sah, misalnya konsekuensi, kondisi, atau waktu yang telah berlalu, jika sistem yang relevan memang mengaturnya.

Prinsip:

```text
INTENT ≠ STATE CHANGE
```

State hanya berubah berdasarkan hasil resolution yang tervalidasi.

## 17. Temporal Integrity

State selalu terkait dengan suatu titik waktu atau konteks waktu yang relevan.

World Time pada State Change dan History harus berasal dari sumber waktu yang sah dalam Runtime.

Modul ini tidak menetapkan kalender, musim, durasi Turn, atau formula waktu universal. Aturan tersebut dibuat dalam sistem waktu/runtime yang relevan.

Tidak boleh membuat waktu fiktif hanya untuk melengkapi record ketika sumber waktu yang sah belum tersedia.

## 18. Unknown / Undefined State

Tidak semua field harus memiliki nilai yang diketahui.

Jika suatu nilai belum ditentukan secara sah, sistem harus mempertahankan status **Unknown / Undefined** sesuai representasi yang ditetapkan sistem terkait.

Unknown tidak boleh diubah menjadi nilai konkret hanya untuk mengisi snapshot.

Contoh:

```text
Known: Current Location = Town A
Unknown: Exact population of Town A
```

Unknown State bukan izin untuk membuat fakta baru.

## 19. Conflict Handling

Jika terdapat konflik antara Canon, Current State, Starting State, atau History, konflik harus dianggap sebagai **integrity issue**, bukan diselesaikan secara diam-diam dengan memilih salah satu sumber.

Prinsip minimum:

```text
DETECT CONFLICT
↓
PRESERVE TRACEABILITY
↓
VALIDATE RELEVANT SOURCES
↓
APPLY EXPLICIT CORRECTION / CANON CHANGE
```

Mekanisme resolusi konflik yang lebih rinci dapat ditetapkan oleh modul Integrity/Persistence di masa depan.

## 20. Character File Relationship

Character File mengikuti Character Data Model dan dapat memuat:

- Starting State;
- Current State;
- Conditions;
- History Reference;
- Metadata.

Character File tidak harus menyalin seluruh History.

History tetap berada pada struktur History yang sesuai dan dapat dirujuk dari Character File.

Jika Character File dan History menunjukkan ketidakkonsistenan, kondisi tersebut harus dianggap sebagai masalah integritas dan divalidasi sebelum State digunakan sebagai dasar gameplay.

## 21. World Persistence

Persistent-world berarti perubahan penting tidak berhenti sebagai narrative response.

Secara konseptual:

```text
SIMULATION RESULT
      ↓
VALIDATED STATE CHANGE
      ↓
APPLY CURRENT STATE
      ↓
CREATE HISTORY
      ↓
PERSIST
      ↓
VERIFY
```

AI GM tidak boleh mengklaim suatu perubahan telah tersimpan hanya karena perubahan tersebut telah dinarasikan.

Jika persistence gagal atau belum terverifikasi, status penyimpanan harus diperlakukan sesuai mekanisme persistence yang akan ditetapkan kemudian.

## 22. Autonomous World Changes

World State dapat berubah tanpa keputusan Player.

Contoh konseptual:

```text
NPC ACTION
EVENT
ENVIRONMENTAL PROCESS
FACTION ACTIVITY
SYSTEM PROCESS
        ↓
STATE CHANGE
        ↓
HISTORY
```

Perubahan autonomous tetap harus memiliki dasar Canon, State, aturan sistem, atau kejadian valid dan mengikuti prinsip provenance serta consistency.

## 23. History Reference & Retrieval

Runtime tidak diwajibkan membaca seluruh History pada setiap Turn.

Prinsip retrieval:

```text
CURRENT STATE
     ↓
IDENTIFY RELEVANT CONTEXT
     ↓
FETCH RELEVANT HISTORY
     ↓
VALIDATE
     ↓
RESOLVE
```

History dapat diambil berdasarkan subject, waktu, event, change, relationship, location, atau kriteria relevan lain ketika sistem retrieval sudah tersedia.

## 24. Integrity Rules

- State adalah snapshot kondisi, bukan narrative.
- Starting State tidak boleh ditimpa oleh Current State.
- Current State harus berasal dari perubahan yang tervalidasi.
- State Change harus memiliki Previous Value yang sesuai dengan State sebelumnya.
- State Change penting harus memiliki Origin/Source yang dapat ditelusuri.
- History tidak boleh dihapus atau ditimpa secara diam-diam.
- Koreksi historis menggunakan Correction Record.
- Event dan State Change tidak boleh dianggap sebagai konsep yang sama.
- Failed/blocked/interrupted action tidak otomatis menghasilkan State Change yang dimaksud Player.
- Unknown/Undefined tidak boleh diisi dengan asumsi.
- Konflik data harus terdeteksi dan tidak diselesaikan secara diam-diam.
- State dan History harus tetap dapat direkonsiliasi.
- Narrative bukan sumber persistence.
- AI GM tidak boleh mengklaim persistence berhasil tanpa verifikasi.

## 25. Boundary of v0.1

State & History Model v0.1 sengaja belum mendefinisikan:

- format database atau serialization final;
- schema JSON/YAML wajib;
- database engine;
- versioning implementation detail;
- retention policy teknis lengkap;
- event sourcing penuh;
- rollback mekanisme teknis;
- conflict resolution algorithm final;
- time/calendar system;
- combat/state formulas;
- magic/supernatural mechanics;
- economy mechanics;
- NPC/faction-specific state schema.

Hal-hal tersebut dapat ditetapkan kemudian melalui modul Canon atau Runtime/Persistence yang relevan.

## 26. Relationship to Other Modules

State & History Model harus kompatibel dengan:

```text
CORE_RULES
↓
CHARACTER_DATA_MODEL
↓
STATE & HISTORY MODEL
↓
RUNTIME MODEL
↓
PERSISTENCE / VALIDATION SYSTEMS
```

Modul ini memperjelas fondasi State dan History tanpa mengubah prinsip Core Rules secara diam-diam.

## 27. Canon Principle

> **Current State menunjukkan apa yang berlaku sekarang. History menjelaskan bagaimana keadaan itu terbentuk. Setiap perubahan penting harus dapat ditelusuri, divalidasi, dan dipersist tanpa mengorbankan integritas masa lalu.**
