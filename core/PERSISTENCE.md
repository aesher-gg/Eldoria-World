# Eldoria World — Persistence v0.1

> **Module:** Persistence  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Persistence mendefinisikan bagaimana State dan History yang telah melewati validasi diterapkan, disimpan, ditangani ketika terjadi kegagalan, dan diverifikasi sebagai persistent result.

Modul ini adalah **save/persistence architecture**, bukan resolution system dan bukan pemilik semantics State atau History.

## 2. Canonical Boundary

Persistence adalah canonical owner untuk:

- penerimaan validated Change Set;
- application of validated changes;
- penyimpanan Current State dan History;
- persistence lifecycle;
- persistence failure handling;
- recovery/correction workflow pada level persistence;
- verification bahwa hasil tersimpan sesuai dengan hasil yang diharapkan.

Persistence **bukan** owner untuk:

- definisi State;
- definisi History;
- State Change semantics;
- Origin/Source semantics;
- gameplay resolution;
- domain-specific rules;
- action selection;
- Canon creation.

Boundary utama:

```text
STATE & HISTORY
= struktur dan semantics data persistent

STATE VALIDATION
= apakah perubahan valid dan konsisten

PERSISTENCE
= bagaimana perubahan valid diterapkan/disimpan

VERIFICATION
= apakah hasil persistence sesuai dengan yang diharapkan
```

Verification adalah **stage/function dalam Persistence Architecture**, bukan canonical owner atau modul ketiga yang berdiri sendiri.

## 3. Dependencies

Persistence bergantung pada:

```text
CORE RULES
RUNTIME / TURN MODEL
STATE & HISTORY MODEL
STATE VALIDATION
CHARACTER DATA MODEL
RELEVANT SYSTEM STATE CONTRACTS
```

Persistence tidak mengubah ownership modul yang menjadi dependency.

## 4. Persistence Input Contract

Persistence hanya menerima perubahan yang telah memenuhi validation requirement yang berlaku.

Secara konseptual:

```text
Persistence Request
├── Persistence ID
├── Validated Change Set
├── Validation Reference
├── Current State Reference
├── History Context / References
├── Temporal Context
├── Origin / Source References
└── Metadata
```

Perubahan yang belum tervalidasi tidak boleh dianggap sebagai valid persistence input.

## 5. Validity Gate

Boundary minimum:

```text
INVALID
   ↓
DO NOT PERSIST AS FINAL STATE
```

```text
CONFLICT / UNRESOLVED
   ↓
DO NOT PERSIST AS FINAL STATE
```

```text
VALIDATED CHANGE SET
   ↓
PERSISTENCE
```

Persistence tidak boleh memperbaiki perubahan invalid secara diam-diam untuk membuatnya dapat disimpan.

## 6. Persistence Lifecycle

Lifecycle konseptual:

```text
VALIDATED CHANGE SET
        ↓
PREPARE
        ↓
APPLY
        ↓
PERSIST
        ↓
VERIFY
        ↓
PERSISTENCE RESULT
```

Detail storage technology, database, file format, transaction engine, atau Git-specific mechanism belum ditetapkan oleh v0.1.

## 7. Change Set and Atomicity

Jika validated Change Set berisi perubahan yang saling bergantung dan harus menjadi satu hasil terintegrasi, persistence harus menjaga agar perubahan tersebut tidak meninggalkan persistent State setengah diterapkan.

Secara konseptual:

```text
VALIDATED CHANGE SET
        ↓
APPLY AS INTEGRATED RESULT
        ↓
PERSIST
        ↓
VERIFY
```

Mekanisme teknis untuk atomic commit atau rollback belum ditetapkan. Requirement Canon-nya adalah mencegah partial final State ketika integritas rangkaian perubahan mensyaratkan penerapan bersama.

## 8. Current State

Persistence menerapkan validated State Changes terhadap Current State yang menjadi baseline.

```text
CURRENT STATE
      ↓
VALIDATED CHANGE SET
      ↓
UPDATED CURRENT STATE
```

Starting State tidak boleh ditimpa oleh gameplay persistence.

Starting State tetap menjadi baseline historis sesuai `state/STATE_AND_HISTORY_MODEL.md`.

## 9. History Persistence

History tetap mengikuti semantics dan ownership `state/STATE_AND_HISTORY_MODEL.md`.

Persistence bertanggung jawab menyimpan History Record yang memang menjadi bagian dari persistent result, tetapi tidak mendefinisikan ulang:

- apa itu History;
- apa itu Origin;
- apa itu Source;
- kapan sebuah record secara semantik merupakan History.

Tidak boleh dibuat parallel History semantics hanya di dalam persistence layer.

## 10. Provenance Preservation

Persistence harus mempertahankan provenance yang berasal dari validated change:

```text
STATE CHANGE
├── Origin
├── Source
├── World Time
└── Other required provenance
        ↓
PERSISTED RECORD
```

Penyimpanan tidak boleh menghilangkan provenance penting sehingga perubahan tidak lagi dapat ditelusuri.

## 11. Verification

Verification memeriksa apakah hasil persistence benar-benar sesuai dengan validated result yang seharusnya tersimpan.

Secara konseptual:

```text
EXPECTED PERSISTED RESULT
          ↓
       PERSIST
          ↓
ACTUAL PERSISTED RESULT
          ↓
      VERIFY
```

Verification harus memperhatikan setidaknya ketika relevan:

- Current State;
- applied State Changes;
- History records;
- provenance;
- consistency antar-data.

Save call atau write operation saja tidak merupakan bukti bahwa persistence berhasil.

## 12. Verification Result

Secara konseptual, verification dapat menghasilkan:

```text
VERIFIED
NOT VERIFIED
MISMATCH
```

Makna final dapat diperluas tanpa melanggar boundary ini.

Jika hasil belum terverifikasi, AI GM tidak boleh mengklaim perubahan sebagai persistent success.

## 13. Persistence Failure

Persistence failure berbeda dari validation failure.

```text
VALIDATION FAILURE
= perubahan tidak lolos integrity gate

PERSISTENCE FAILURE
= perubahan valid tetapi proses penerapan/penyimpanan gagal

VERIFICATION FAILURE
= hasil persistence tidak dapat dikonfirmasi sesuai expected result
```

Ketiga kondisi tersebut harus tetap dapat dibedakan.

## 14. Failure Handling

Jika persistence gagal:

```text
PERSISTENCE FAILURE
       ↓
PRESERVE TRACEABILITY
       ↓
IDENTIFY PERSISTENCE STATUS
       ↓
RECOVERY / RETRY / CORRECTION
       ↓
VALIDATE AS REQUIRED
       ↓
PERSIST
       ↓
VERIFY
```

Persistence tidak boleh menyatakan sukses hanya karena request telah diterima atau proses write telah dimulai.

Mekanisme retry otomatis, jumlah retry, timeout, atau storage-specific recovery policy tidak ditentukan oleh v0.1.

## 15. Verification Failure

Jika verification menemukan mismatch atau tidak dapat memastikan hasil:

```text
PERSIST
  ↓
VERIFY
  ↓
NOT VERIFIED / MISMATCH
```

Status tersebut harus dipertahankan dan tidak boleh diubah menjadi success hanya karena proses persistence sebelumnya telah selesai secara teknis.

## 16. Recovery and Correction

Recovery harus menjaga traceability dan tidak boleh menghapus bukti kegagalan atau record asli secara diam-diam.

Jika koreksi diperlukan:

```text
ORIGINAL / FAILED RECORD
        ↓
CORRECTION / RECOVERY RECORD
        ↓
VALIDATED RESULT
        ↓
PERSIST
        ↓
VERIFY
```

Semantics correction history tetap mengikuti State & History Model.

## 17. Idempotency and Duplicate Application

Persistence architecture harus mencegah satu validated change diterapkan berulang kali sebagai perubahan baru ketika request yang sama diproses ulang.

Secara konseptual:

```text
VALIDATED CHANGE / REQUEST ID
          ↓
IDENTIFY PRIOR APPLICATION
          ↓
ALREADY APPLIED?
   ├── YES → DO NOT DUPLICATE
   └── NO  → APPLY / PERSIST
```

Mekanisme teknis untuk mencapai idempotency belum ditetapkan oleh v0.1. Requirement ini bersifat integrity requirement, bukan implementasi database tertentu.

## 18. Conflict During Persistence

Jika ditemukan conflict terhadap persistent baseline ketika proses persistence berlangsung, Persistence tidak boleh memilih nilai secara diam-diam.

```text
PERSISTENCE CONFLICT
        ↓
STOP / HOLD FINAL APPLICATION AS REQUIRED
        ↓
PRESERVE TRACEABILITY
        ↓
VALIDATE RELEVANT STATE
        ↓
EXPLICIT CORRECTION / RESOLUTION
```

Detail concurrency mechanism belum ditentukan oleh v0.1.

## 19. Concurrent / Autonomous Changes

Player action, NPC action, world event, environmental process, faction activity, atau system process dapat menghasilkan perubahan persistent.

Semua sumber menggunakan persistence boundary yang sama setelah perubahan memenuhi validation requirement.

Tidak ada separate persistence path yang boleh melewati State Validation hanya karena perubahan berasal dari dunia autonomous.

## 20. Unknown / Undefined

Persistence tidak boleh mengisi field Unknown / Undefined dengan nilai konkret hanya agar record dapat disimpan.

Jika data yang diwajibkan belum tersedia, status tersebut harus tetap direpresentasikan sesuai kontrak sistem terkait atau persistence harus menahan hasil bila data tersebut membuat persistence tidak sah.

Persistence tidak menciptakan fakta Canon baru.

## 21. Starting State vs Current State

Persistence harus menjaga:

```text
STARTING STATE
= baseline historis

CURRENT STATE
= persistent operational state
```

Gameplay update hanya mengubah Current State melalui validated changes.

Starting State hanya berubah melalui explicit Canon/character data correction yang sah, bukan melalui gameplay save biasa.

## 22. Runtime Integration

Runtime mengintegrasikan Persistence setelah State Validation:

```text
RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGE(S)
↓
STATE VALIDATION
↓
VALID
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE
```

Jika persistence atau verification belum berhasil, response harus merepresentasikan status tersebut secara jujur dan tidak menyatakan bahwa save telah berhasil secara resmi.

## 23. History and State Consistency

Setelah persistence berhasil dan diverifikasi, Current State dan History yang terkait harus tetap dapat direkonsiliasi.

Persistence tidak boleh menghasilkan:

```text
CURRENT STATE = A
HISTORY = tidak mendukung A
```

ketika History tersebut diwajibkan untuk menjelaskan perubahan.

## 24. No Narrative Persistence

Narrative response bukan persistence record dan bukan bukti bahwa save berhasil.

```text
NARRATIVE
≠
PERSISTENCE
```

Narrative hanya merepresentasikan hasil simulasi dan status persistence yang diketahui.

## 25. No Silent Overwrite

Persistence tidak boleh melakukan overwrite diam-diam untuk menghilangkan:

- State conflict;
- History record;
- provenance;
- correction evidence;
- failure information.

Correction harus dapat ditelusuri sesuai State & History Model.

## 26. Output Contract

Secara konseptual:

```text
Persistence Result
├── Persistence ID
├── Status
├── Applied Change Set
├── Current State Reference
├── History Reference
├── Verification Reference
├── Failure / Recovery Information
└── Metadata
```

Output harus membedakan setidaknya antara persistence yang berhasil diverifikasi dan persistence yang belum dapat diverifikasi.

## 27. Persistence Status

Status persistence bersifat lifecycle-oriented dan tidak boleh disamakan dengan gameplay result.

Contoh konseptual:

```text
NOT_STARTED
IN_PROGRESS
PERSISTED
VERIFIED
FAILED
RECOVERY_REQUIRED
NOT_VERIFIED
```

Daftar ini adalah model konseptual v0.1; implementasi dapat menggunakan representasi lain selama semantics dan integrity requirement tetap terjaga.

## 28. Knowledge Boundary

Persistence tidak memperluas knowledge karakter atau Player.

Menyimpan sebuah record tidak berarti semua actor mengetahui isi record tersebut.

```text
PERSISTED FACT
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
```

Knowledge boundaries tetap mengikuti Core Rules dan sistem relevan.

## 29. Integrity Rules

- Persistence hanya menerima perubahan yang memenuhi validation requirement.
- Persistence tidak menentukan gameplay result.
- State & History tetap menjadi canonical owner semantics State, History, State Change, Origin, dan Source.
- Starting State tidak ditimpa oleh gameplay persistence.
- Current State diperbarui melalui validated State Changes.
- History harus dipertahankan sesuai State & History Model.
- Provenance tidak boleh hilang selama persistence.
- Interdependent Change Sets harus diperlakukan sebagai integrated result ketika atomicity diperlukan.
- Invalid, conflict, atau unresolved changes tidak boleh dipersist sebagai final valid State.
- Persistence failure ≠ validation failure ≠ verification failure.
- Save/write operation bukan bukti verification.
- Verification harus membandingkan hasil aktual dengan expected persisted result sesuai kebutuhan.
- Persistence conflict tidak boleh diselesaikan diam-diam.
- Duplicate application harus dicegah secara konseptual.
- Recovery/correction harus menjaga traceability.
- Unknown / Undefined tidak boleh diisi dengan fallback.
- Autonomous world changes menggunakan persistence boundary yang sama.
- Narrative bukan bukti persistence.
- AI GM tidak boleh mengklaim persistence berhasil tanpa verification.

## 30. Future Extensions

Implementasi berikut dapat ditetapkan kemudian tanpa mengubah boundary v0.1:

```text
STORAGE FORMAT
TRANSACTION MECHANISM
ROLLBACK / RECOVERY MECHANISM
CONCURRENCY CONTROL
RETRY POLICY
VERSIONING / REVISION IMPLEMENTATION
REPOSITORY-SPECIFIC SAVE MECHANISM
AUTOMATED INTEGRITY CHECKS
```

Ekstensi tersebut harus tetap tunduk pada Core Rules, Runtime, State & History, dan State Validation.
