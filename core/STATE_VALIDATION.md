# Eldoria World — State Validation v0.1

> **Module:** State Validation  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

State Validation adalah layer integrity yang memeriksa apakah State Change atau rangkaian State Changes dapat diterapkan secara sah dan konsisten terhadap Canon, State, temporal context, dan provenance yang relevan.

Modul ini adalah **validation architecture**, bukan resolution system. Modul ini tidak menentukan apa yang terjadi dalam gameplay; modul ini memeriksa perubahan yang telah dihasilkan oleh resolution atau proses valid lain.

## 2. Canonical Boundary

State Validation adalah canonical owner untuk:

- validasi integritas State Change;
- validasi consistency terhadap State baseline;
- deteksi conflict pada perubahan;
- pemeriksaan provenance yang diwajibkan;
- pemeriksaan compatibility terhadap Canon;
- validasi rangkaian perubahan yang saling bergantung;
- penetapan status validasi.

State Validation **bukan** owner untuk:

- definisi State atau History;
- provenance semantics;
- Character Data Model;
- Time & Calendar resolution;
- Combat resolution;
- Health & Injury resolution;
- Travel & Movement resolution;
- NPC decision-making;
- Relationships resolution;
- Reputation resolution;
- Law resolution;
- persistence/storage.

Boundary utama:

```text
STATE & HISTORY
= apa itu State, History, State Change, Origin, Source

RESOLUTION SYSTEM
= apa yang terjadi

STATE VALIDATION
= apakah perubahan yang dihasilkan dapat diterapkan secara sah dan konsisten

PERSISTENCE
= bagaimana perubahan valid diterapkan/disimpan dan diverifikasi
```

## 3. Dependencies

State Validation bergantung pada kontrak dari:

```text
CORE RULES
RUNTIME / TURN MODEL
STATE & HISTORY MODEL
CHARACTER DATA MODEL
TIME & CALENDAR
RELEVANT WORLD / SYSTEM CANON
```

Dependency tidak memindahkan canonical ownership dari modul tersebut.

## 4. Validation Input

Secara konseptual, Validation Request dapat memuat:

```text
Validation Request
├── Validation ID
├── Current State Reference
├── State Change Set
├── Relevant Canon Context
├── Temporal Context
├── History Context
├── Origin / Source References
└── Metadata
```

Validator tidak boleh mengarang data yang tidak tersedia hanya agar request dapat dinyatakan valid.

## 5. State Change Contract

State Change mengikuti struktur yang ditetapkan `state/STATE_AND_HISTORY_MODEL.md`:

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

State Validation memeriksa kontrak tersebut; State & History tetap menjadi pemilik definisinya.

## 6. Validation Layers

Validasi dilakukan secara berlapis sesuai kebutuhan perubahan:

```text
STATE CHANGE(S)
      ↓
STRUCTURAL VALIDATION
      ↓
REFERENCE / TARGET VALIDATION
      ↓
CURRENT STATE CONSISTENCY
      ↓
PROVENANCE VALIDATION
      ↓
TEMPORAL CONSISTENCY
      ↓
CANON COMPATIBILITY
      ↓
CROSS-CHANGE CONSISTENCY
      ↓
VALIDATION RESULT
```

Tidak semua pemeriksaan harus identik untuk setiap domain; pemeriksaan mengikuti data dan aturan Canon yang relevan.

## 7. Structural Validation

Validator memeriksa apakah perubahan memiliki struktur yang cukup untuk dinilai, termasuk reference target, field/property, nilai sebelum/sesudah bila diwajibkan, provenance, dan temporal context bila diwajibkan.

Data yang diwajibkan tetapi tidak tersedia tidak boleh diganti dengan default, tebakan, nilai rata-rata, atau nilai yang dianggap masuk akal.

## 8. Current State Consistency

Previous Value harus konsisten dengan State baseline yang menjadi dasar perubahan.

Contoh konseptual:

```text
CURRENT STATE
Gold = 100

STATE CHANGE
Previous = 100
New = 70

→ CONSISTENT
```

Jika Current State adalah `100` tetapi Previous Value adalah `80`, perubahan tersebut memiliki conflict dan tidak boleh disesuaikan secara diam-diam.

## 9. Provenance Validation

Jika State Change memerlukan provenance, Validator memeriksa ketersediaan dan keterlacakan:

```text
STATE CHANGE
   ↓
ORIGIN
   ↓
SOURCE
   ↓
RELEVANT ACTION / EVENT / PROCESS / CANON BASIS
```

Origin dan Source tidak boleh dibuat setelah fakta hanya untuk membenarkan perubahan yang sudah diputuskan.

## 10. Temporal Validation

World Time dan temporal context harus berasal dari sumber waktu yang sah menurut `systems/TIME_AND_CALENDAR.md` dan Runtime.

State Validation tidak menetapkan kalender, musim, durasi Turn, atau formula waktu universal.

Jika temporal information yang diwajibkan tidak tersedia, Validator tidak boleh mengarangnya.

## 11. Canon Compatibility

State Change harus kompatibel dengan Canon yang relevan.

Validator tidak boleh menciptakan aturan baru untuk membuat perubahan menjadi valid.

Jika Canon belum mendefinisikan aturan yang diperlukan, kondisi tersebut tetap **Unknown / Undefined** dan perubahan tidak boleh memperoleh validitas hanya melalui asumsi.

## 12. Change Set and Atomicity

Jika beberapa State Changes saling bergantung sebagai satu hasil terintegrasi, perubahan tersebut harus divalidasi sebagai satu Change Set.

```text
CHANGE A
CHANGE B
CHANGE C
   ↓
VALIDATE AS SET
   ↓
ALL REQUIRED CHANGES VALID?
   ├── YES → PASS TO PERSISTENCE
   └── NO  → DO NOT TREAT SET AS FINAL
```

Validator tidak boleh menyatakan Change Set valid hanya karena sebagian perubahan valid jika dependency antar-perubahan membuat keseluruhan tidak konsisten.

## 13. Multi-Entity Changes

Perubahan yang melibatkan beberapa subject atau entity harus dapat dinilai sebagai satu rangkaian ketika perubahan tersebut saling bergantung.

Contoh konseptual:

```text
ACTOR A
├── resource decreases

ACTOR B
├── resource increases

TRANSACTION / EVENT
└── common origin
```

Validasi harus menjaga konsistensi antar-perubahan dan provenance bersama bila relevan.

## 14. Conflict Handling

Conflict adalah integrity condition, bukan alasan untuk memilih nilai secara diam-diam.

Minimum process:

```text
DETECT CONFLICT
↓
PRESERVE TRACEABILITY
↓
IDENTIFY RELEVANT SOURCES
↓
REQUIRE EXPLICIT CORRECTION / RESOLUTION
```

Validator tidak berwenang memilih `latest`, `highest`, `lowest`, atau sumber lain sebagai pemenang tanpa aturan Canon yang secara sah menetapkannya.

## 15. Unknown / Undefined

Unknown / Undefined harus dipertahankan ketika Canon, State, History, atau sistem relevan belum menyediakan jawaban yang sah.

Validator tidak boleh mengubah Unknown menjadi:

- zero;
- default value;
- average;
- assumed value;
- plausible value;
- generated fact.

Unknown adalah status informasi, bukan izin untuk menciptakan data.

## 16. Starting State vs Current State

Validator harus mempertahankan perbedaan:

```text
STARTING STATE
= baseline historis karakter

CURRENT STATE
= kondisi operasional sekarang
```

Gameplay State Change tidak boleh menimpa Starting State.

Jika Current State bertentangan dengan Starting State, hal tersebut bukan alasan untuk mengubah Starting State secara diam-diam.

## 17. Validation Result

Secara konseptual, hasil validasi dapat memiliki status:

```text
VALID
INVALID
CONFLICT
UNRESOLVED
```

Makna umum:

- **VALID** — perubahan memenuhi kontrak yang diperlukan dan dapat diteruskan ke Persistence.
- **INVALID** — perubahan melanggar requirement atau aturan yang diketahui.
- **CONFLICT** — terdapat ketidaksesuaian antar sumber atau State yang belum diselesaikan secara sah.
- **UNRESOLVED** — informasi atau mekanisme yang diperlukan belum tersedia untuk menentukan validitas.

Status tersebut tidak menentukan hasil gameplay.

## 18. Resolution Boundary

State Validation tidak boleh mengubah:

```text
FAILURE → SUCCESS
SUCCESS → FAILURE
BLOCKED → SUCCESS
```

hanya karena validator menemukan masalah data.

Jika resolution menghasilkan result tertentu, validator hanya memeriksa apakah State Change yang merepresentasikan result tersebut valid untuk diterapkan.

## 19. Failed / Blocked / Interrupted Actions

Action yang gagal, diblokir, tertunda, atau terinterupsi tidak otomatis menghasilkan State Change yang dimaksud Player.

Jika resolution menghasilkan consequence lain yang sah, consequence tersebut dapat menghasilkan State Change sendiri dan tetap harus divalidasi.

## 20. Autonomous Changes

NPC, faction, event, environment, atau system process dapat menghasilkan State Change tanpa Player action.

Sumber autonomous tersebut tetap harus memiliki dasar yang sah dan melewati State Validation sebelum persistent application.

```text
AUTONOMOUS PROCESS
↓
STATE CHANGE
↓
STATE VALIDATION
↓
PERSISTENCE
```

## 21. History Compatibility

State Change yang lolos validasi harus dapat direkonsiliasi dengan History yang akan dibuat sesuai `state/STATE_AND_HISTORY_MODEL.md`.

Validator tidak mengambil alih pembuatan atau definisi History. Validator hanya memastikan perubahan tidak secara jelas bertentangan dengan History context yang relevan.

## 22. Output Contract

Secara konseptual, Validation Result dapat memuat:

```text
Validation Result
├── Validation ID
├── Status
├── Validated Change Set / Findings
├── Conflict References
├── Provenance Status
├── Consistency Findings
├── Canon Compatibility Findings
├── Temporal Findings
└── Metadata
```

Output valid tidak berarti perubahan sudah tersimpan. Perubahan baru dapat diteruskan ke Persistence setelah validasi yang diperlukan selesai.

## 23. Runtime Integration

Runtime menggunakan State Validation setelah resolution dan State Change generation:

```text
RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGE(S)
↓
STATE VALIDATION
↓
VALID?
├── NO → DO NOT APPLY AS FINAL STATE
└── YES
     ↓
  PERSISTENCE
     ↓
  VERIFY
```

Working State dapat digunakan selama Turn, tetapi persistence final tetap membutuhkan validasi sesuai kontrak ini.

## 24. No Bypass

Tidak ada system, NPC process, world event, atau narrative response yang boleh melewati State Validation hanya karena perubahan dianggap penting bagi cerita.

Narrative tidak menjadi bukti validitas.

## 25. Integrity Rules

- State Validation adalah integrity gate, bukan resolution engine.
- State & History tetap menjadi canonical owner State, History, State Change, Origin, dan Source semantics.
- Previous Value harus sesuai dengan State baseline.
- State Changes yang saling bergantung harus dapat divalidasi sebagai satu Change Set.
- Conflict tidak boleh diselesaikan secara diam-diam.
- Provenance yang diwajibkan harus tersedia dan dapat ditelusuri.
- Temporal data tidak boleh diarang.
- Canon yang undefined tidak boleh diisi dengan fallback.
- Unknown / Undefined tidak boleh menjadi fakta konkret melalui asumsi.
- Starting State tidak boleh ditimpa oleh gameplay Current State.
- Validator tidak boleh mengubah hasil resolution.
- State Change invalid, conflict, atau unresolved tidak boleh diperlakukan sebagai final valid change.
- Semua perubahan persistent, termasuk autonomous changes, harus mengikuti validation contract.
- Validasi berhasil tidak sama dengan persistence berhasil.
