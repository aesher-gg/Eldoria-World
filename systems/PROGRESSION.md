# Eldoria World — Progression System v0.1

> **Module:** Progression  
> **Version:** v0.1  
> **Authority:** Official Canon  
> **Role:** World System

---

## 1. Purpose

Progression v0.1 menetapkan **canonical owner untuk perubahan capability suatu Character atau entity yang valid dari waktu ke waktu**.

Progression mencakup acquisition, development, dan perubahan capability yang memiliki dasar yang sah. Progression menghubungkan proses seperti training, practice, experience, learning, teaching, discovery, dan proses domain lain dengan perubahan capability.

Progression adalah **framework perkembangan capability**, bukan sistem level atau sistem poin universal.

---

## 2. Canonical Boundary

```text
CHARACTER DATA MODEL
= struktur Character / NPC

PROGRESSION
= perkembangan / perubahan capability

ACTION MODEL
= struktur dan lifecycle Action

RESOLUTION ARCHITECTURE
= generic Result / resolution contract

COMBAT
= combat mechanics dan combat resolution

SUPERNATURAL / MAGIC
= supernatural mechanics dan magical capability definition

NPC BEHAVIOR & AGENCY
= NPC decision, knowledge, motivation, dan action selection

ITEMS / EQUIPMENT
= item dan equipment semantics

STATE & HISTORY
= State, State Change, provenance, dan History

PERSISTENCE
= penyimpanan validated State / History
```

Prinsip utama:

```text
CAPABILITY DEFINITION
≠
CAPABILITY PROGRESSION
```

Progression tidak mengambil alih domain yang mendefinisikan capability, mekanisme, atau resolution.

---

## 3. Scope

Progression v0.1 memiliki empat core capability domains:

```text
ATTRIBUTE DEVELOPMENT
ABILITY ACQUISITION
ABILITY DEVELOPMENT
CAPABILITY CHANGE
```

Mekanisme yang dapat menjadi input atau proses progression meliputi:

```text
TRAINING
PRACTICE
EXPERIENCE
LEARNING
TEACHING
OBSERVATION
DISCOVERY
OTHER VALID PROCESS
```

Kategori tersebut adalah framework dan bukan daftar mekanisme yang wajib tersedia pada setiap Character atau sistem.

---

## 4. Core Principles

1. Capability hanya dapat berkembang melalui basis yang valid.
2. Progression tidak menjamin development hanya karena suatu proses dilakukan.
3. Experience tidak sama dengan XP.
4. Learning tidak otomatis menghasilkan acquisition atau development.
5. Training tidak otomatis menghasilkan advancement.
6. Practice tidak otomatis menghasilkan advancement.
7. Intent tidak otomatis menjadi progression.
8. Progression Result tidak otomatis menjadi State Change tanpa validasi.
9. Capability definition tetap dimiliki domain yang relevan.
10. Current State tetap menjadi baseline operasional.
11. Starting State tidak ditimpa oleh progression normal.
12. Unknown / Undefined tetap dipertahankan.
13. Progression tidak menggunakan formula universal yang belum ditetapkan Canon.
14. Tidak ada automatic advancement universal.
15. Semua perubahan persistent harus dapat ditelusuri melalui provenance dan History.

---

## 5. Progression Subject

Progression memerlukan subject yang mengalami perubahan capability.

Model konseptual:

```text
PROGRESSION SUBJECT
├── Subject ID
├── Subject Type
└── Character / Entity Reference
```

Character adalah use case utama pada v0.1. Entity lain hanya dapat menggunakan Progression apabila Canon dan konteks yang relevan memang mendukungnya.

Progression tidak secara otomatis memberikan capability progression kepada seluruh entity dunia.

---

## 6. Capability

Progression bekerja terhadap capability yang sudah memiliki definisi atau basis Canon yang sah.

Model konseptual:

```text
CAPABILITY
├── Capability Reference
├── Capability Type
├── Current Capability Context
└── Definition / Source Reference
```

Capability dapat berupa:

```text
ATTRIBUTE
ABILITY
OTHER CANON-DEFINED CAPABILITY
```

Progression tidak boleh menciptakan definisi capability, stat, ability, spell, technique, atau mechanic baru hanya karena diperlukan untuk menyelesaikan suatu progression process.

Jika definisi capability belum tersedia, statusnya tetap Unknown / Undefined atau proses menjadi Unresolved sesuai konteks.

---

## 7. Progression Source / Process

Progression dapat menerima basis dari proses yang sah.

```text
SOURCE / PROCESS
├── Training
├── Practice
├── Experience
├── Learning
├── Teaching
├── Observation
├── Discovery
├── Domain Process
├── Event
└── Other Valid Source
```

Source / Process harus dapat ditelusuri apabila menghasilkan perubahan persistent.

Tidak semua source menghasilkan progression, dan tidak semua progression harus berasal dari jenis source yang sama.

---

## 8. Progression Context

Evaluasi progression dapat menggunakan context yang relevan, antara lain:

```text
SUBJECT
CURRENT STATE
CURRENT CAPABILITY
PROCESS / ACTION REFERENCE
RESULT REFERENCE
EXPERIENCE / LEARNING CONTEXT
TRAINING CONTEXT
TEACHER / SOURCE
ENVIRONMENT
TIME / TEMPORAL CONTEXT
PREREQUISITES (IF DEFINED)
CONSTRAINTS
OTHER VALID CANON CONTEXT
```

Tidak semua field wajib tersedia pada setiap progression process.

Context yang belum diketahui tetap Unknown / Undefined.

Progression tidak boleh mengarang prerequisite, constraint, atau condition yang belum memiliki basis Canon.

---

## 9. Progression Input

Progression dapat menerima input dari:

```text
CHARACTER / CURRENT STATE
ACTION
RESOLUTION RESULT
COMBAT
SUPERNATURAL / MAGIC
NPC BEHAVIOR
ITEMS / EQUIPMENT
WORLD EVENTS
OTHER VALID WORLD PROCESSES
```

Hubungan konseptual:

```text
VALID PROCESS / EXPERIENCE
        ↓
PROGRESSION INPUT
        ↓
PROGRESSION EVALUATION
```

Input hanya menjadi dasar evaluasi. Input tidak dengan sendirinya menentukan development.

---

## 10. Attribute Development

Progression adalah canonical owner untuk **proses development Attribute**.

Character Data Model tetap menjadi owner struktur Character dan representasi Attribute pada Character.

```text
ATTRIBUTE
↓
VALID DEVELOPMENT PROCESS
↓
PROGRESSION
↓
ATTRIBUTE DEVELOPMENT RESULT
↓
STATE CHANGE
```

Progression v0.1 tidak menetapkan:

- daftar Attribute universal;
- range Attribute universal;
- Attribute point;
- formula perubahan Attribute;
- conversion waktu latihan menjadi Attribute change.

Attribute yang belum didefinisikan tetap Unknown / Undefined.

---

## 11. Ability Acquisition

Progression adalah canonical owner untuk lifecycle acquisition suatu Ability yang sudah memiliki basis Canon.

```text
NO CURRENT ABILITY
↓
VALID SOURCE / PROCESS
↓
PROGRESSION EVALUATION
↓
ABILITY ACQUISITION RESULT
↓
STATE CHANGE
```

Boundary:

```text
ABILITY DEFINITION
→ relevant domain

ABILITY ACQUISITION
→ PROGRESSION
```

Progression tidak menciptakan Ability definition hanya untuk memenuhi acquisition.

---

## 12. Ability Development

Progression juga menjadi owner untuk perkembangan Ability yang sudah dimiliki.

```text
EXISTING ABILITY
↓
VALID DEVELOPMENT PROCESS
↓
PROGRESSION
↓
ABILITY DEVELOPMENT RESULT
↓
STATE CHANGE
```

Development dapat terjadi, tidak terjadi, atau menghasilkan perubahan lain yang sah berdasarkan context dan Canon.

V0.1 tidak menetapkan universal mastery percentage, skill level, skill point, atau development formula.

---

## 13. Capability Change

Progression dapat menghasilkan perubahan capability lain jika capability tersebut memiliki basis Canon.

Model konseptual:

```text
CURRENT CAPABILITY
↓
VALID PROCESS / CONDITION
↓
PROGRESSION
↓
CAPABILITY CHANGE
```

Perubahan dapat mencakup acquisition, development, perubahan kondisi capability, atau loss/regression apabila mekanisme yang relevan memang didefinisikan.

Tidak ada asumsi bahwa seluruh capability harus memiliki lifecycle yang sama.

---

## 14. Training

Training adalah **Progression mechanism**, bukan system terpisah pada v0.1.

```text
TRAINING
↓
TRAINING CONTEXT / RESULT
↓
PROGRESSION EVALUATION
↓
DEVELOPMENT / NO CHANGE / OTHER VALID RESULT
```

Training tidak menjamin advancement.

Tidak ada universal:

```text
TRAINING HOURS → PROGRESSION POINTS
```

Detail training dapat berasal dari domain yang sedang dilatih, sedangkan Progression menentukan semantics development yang dihasilkan dari proses yang valid.

---

## 15. Practice

Practice adalah **Progression mechanism**, bukan system terpisah pada v0.1.

```text
PRACTICE
↓
RELEVANT CONTEXT / RESULT
↓
PROGRESSION
```

Practice tidak otomatis menghasilkan development.

Tidak ada universal repetition count, practice points, atau practice formula.

---

## 16. Experience

Experience adalah input progression yang berasal dari sesuatu yang benar-benar dialami atau diperoleh actor melalui proses yang valid.

```text
EXPERIENCE
↓
PROGRESSION RELEVANCE
↓
LEARNING / DEVELOPMENT / OTHER VALID RESULT
```

Hard boundary:

```text
EXPERIENCE ≠ XP
EXPERIENCE ≠ AUTOMATIC ADVANCEMENT
```

Experience dapat relevan terhadap capability tertentu tanpa harus menghasilkan perubahan capability.

---

## 17. Learning

Learning merupakan mekanisme progression ketika proses pembelajaran berkaitan dengan acquisition atau development capability.

```text
OBSERVATION
READING
TEACHING
PRACTICE
EXPERIENCE
DISCOVERY
OTHER VALID SOURCE
        ↓
      LEARNING
        ↓
   PROGRESSION
        ↓
CAPABILITY DEVELOPMENT / ACQUISITION
```

Learning tidak menjamin capability change.

Knowledge state tetap berada pada Character/NPC atau domain knowledge yang relevan. Progression tidak mengambil alih semantics knowledge, belief, atau information access.

---

## 18. Teaching / Instruction

Teaching atau instruction dapat menjadi source untuk learning dan progression.

```text
TEACHER / SOURCE
↓
INSTRUCTION
↓
LEARNING
↓
PROGRESSION
↓
CAPABILITY RESULT
```

Keberadaan teacher tidak otomatis menjamin bahwa subject berhasil belajar.

Tidak ada universal teaching efficiency, learning rate, atau success percentage pada v0.1.

---

## 19. Discovery & Observation

Discovery atau observation dapat menjadi source progression apabila menghasilkan basis pembelajaran atau capability change yang valid.

```text
OBSERVATION / DISCOVERY
↓
VALID INFORMATION / EXPERIENCE
↓
LEARNING / PROGRESSION
```

Progression tidak mengubah informasi yang tidak diketahui menjadi capability hanya karena informasi tersebut tersedia bagi Player.

Knowledge boundary tetap berlaku.

---

## 20. Progression Evaluation

Progression mengevaluasi apakah input yang tersedia memiliki dasar yang cukup untuk menghasilkan perubahan capability.

Model konseptual:

```text
PROGRESSION INPUT
↓
IDENTIFY SUBJECT
↓
IDENTIFY CAPABILITY
↓
CHECK SOURCE / PROCESS
↓
CHECK CURRENT STATE
↓
CHECK RELEVANT CONTEXT
↓
CHECK CANON-DEFINED PREREQUISITES / CONSTRAINTS
↓
EVALUATE
↓
PROGRESSION RESULT
```

Evaluation tidak boleh menggunakan fallback yang tidak didefinisikan Canon.

---

## 21. Progression Result

Progression Result merepresentasikan hasil proses progression sebelum perubahan persistent diterapkan.

Model konseptual:

```text
PROGRESSION RESULT
├── Progression Reference
├── Subject Reference
├── Capability Reference
├── Status / Outcome
├── Development / Acquisition / Change
├── Relevant Consequences
├── Source / Origin
├── Process References
└── Metadata
```

Hasil dapat secara konseptual mencakup:

```text
NO CHANGE
ACQUISITION
DEVELOPMENT
CHANGE
LOSS / REGRESSION (IF DEFINED)
UNRESOLVED
```

Enum final hanya berlaku apabila didukung oleh kebutuhan Canon dan tidak boleh dipakai untuk menyembunyikan missing mechanics.

---

## 22. Progression Lifecycle

Lifecycle utama:

```text
VALID PROCESS / EXPERIENCE
          ↓
     PROGRESSION INPUT
          ↓
   CONTEXT EVALUATION
          ↓
 PROGRESSION RESOLUTION
          ↓
     PROGRESSION RESULT
          │
          ├──────────────→ NO STATE CHANGE
          │
          ↓
 STATE CHANGE PROPOSAL
          ↓
   STATE VALIDATION
          ↓
     VALIDATED CHANGE
          ↓
        HISTORY
          ↓
      PERSISTENCE
          ↓
        VERIFY
```

Progression tidak menerapkan perubahan persistent secara langsung tanpa melalui canonical State Validation dan Persistence boundaries.

---

## 23. Action Integration

Progression dapat dipicu oleh Action yang merepresentasikan training, practice, study, teaching, experimentation, atau proses relevan lainnya.

```text
PLAYER / NPC INTENT
↓
ACTION MODEL
↓
RESOLUTION
↓
RESULT
↓
PROGRESSION PROCESS
↓
PROGRESSION RESULT
↓
STATE CHANGE
```

Action Model tetap menjadi owner struktur dan lifecycle Action.

Progression tidak menggantikan Action Model.

---

## 24. Resolution Integration

Resolution menentukan Result dari proses yang dijalankan.

```text
ACTION
↓
RESOLUTION
↓
RESULT
↓
PROGRESSION INPUT
↓
PROGRESSION RESULT
```

Progression tidak menjadi generic resolution engine dan tidak menggantikan Resolution Architecture.

`UNRESOLVED` tidak boleh digunakan untuk menyamarkan gameplay failure. Unresolved berarti required rule, data, atau mechanic belum tersedia atau tidak dapat diproses secara sah.

---

## 25. Combat Integration

Combat tetap menjadi canonical owner combat mechanics dan combat resolution.

Combat dapat menghasilkan pengalaman atau result yang relevan terhadap Progression.

```text
COMBAT
↓
COMBAT RESULT / EXPERIENCE
↓
PROGRESSION INPUT
↓
COMBAT CAPABILITY DEVELOPMENT
```

Combat tidak otomatis memberikan XP, level, skill point, atau advancement.

Progression tidak mengubah combat resolution atau membuat combat formula baru.

---

## 26. Supernatural / Magic Integration

Supernatural / Magic tetap menjadi canonical owner untuk mekanisme supernatural, access, capability definition, limits, costs, risks, dan effects.

```text
MAGIC
↓
MAGICAL PRACTICE / LEARNING / EXPERIENCE
↓
PROGRESSION
↓
MAGICAL CAPABILITY DEVELOPMENT
```

Progression tidak menciptakan spell, mana, magical tier, magical power, atau supernatural mechanic.

Magic v0.1 memang menyediakan ruang untuk learning/development tetapi belum menetapkan progression universal; Progression menjadi owner proses development tanpa mengambil alih mekanisme Magic. fileciteturn534file0

---

## 27. NPC Behavior Integration

NPC Behavior & Agency tetap menjadi owner decision-making, motivation, knowledge, belief, dan action selection NPC.

```text
NPC BEHAVIOR
↓
DECISION
↓
TRAINING / PRACTICE / LEARNING ACTION
↓
RESOLUTION
↓
PROGRESSION
```

Boundary:

```text
NPC BEHAVIOR
= Apa yang NPC pilih / lakukan?

PROGRESSION
= Bagaimana capability NPC berkembang?
```

NPC learning sebagai knowledge/information update tetap berada pada NPC Behavior ketika konteksnya adalah perubahan knowledge atau belief. Progression menangani development capability yang dihasilkan dari proses learning tersebut.

---

## 28. Items / Equipment Integration

Items / Equipment dapat menjadi context atau tool untuk training, practice, learning, atau proses development lainnya.

```text
ITEM / EQUIPMENT
↓
TRAINING / PRACTICE CONTEXT
↓
PROGRESSION
```

Items / Equipment tetap menjadi owner item identity, Item State, Equipment Context, possession, usage, dan lifecycle.

Progression tidak menciptakan item mechanics atau item capability.

---

## 29. Character Integration

Character Data Model tetap menjadi canonical owner struktur Character.

Progression berinteraksi terutama dengan:

```text
CHARACTER
├── Attributes
├── Abilities
├── Current State
└── History References
```

Alur:

```text
CHARACTER CURRENT STATE
↓
PROGRESSION
↓
CAPABILITY CHANGE
↓
STATE CHANGE
```

Progression tidak menggantikan Character Data Model dan tidak mengubah Starting State sebagai baseline historical.

---

## 30. State Integration

Progression menghasilkan **State Change Proposal**, bukan final State secara langsung.

```text
PROGRESSION RESULT
↓
STATE CHANGE PROPOSAL
↓
STATE VALIDATION
↓
APPLY VALID CHANGE
```

State & History tetap menjadi canonical owner semantics State dan State Change.

Minimal provenance untuk perubahan yang relevan harus dapat menghubungkan:

```text
Subject
Capability
Previous Value
New Value
Origin
Source
World Time
```

sesuai kebutuhan State & History Model.

Starting State tidak ditimpa oleh progression normal.

---

## 31. History & Provenance

Progression yang menghasilkan perubahan persistent harus dapat ditelusuri.

```text
SOURCE / PROCESS
↓
RESULT
↓
PROGRESSION RESULT
↓
STATE CHANGE
↓
HISTORY
```

History tetap menjadi canonical owner record historis.

Progression tidak menghapus atau menimpa History untuk membenarkan hasil progression baru.

---

## 32. Persistence Integration

Progression mengikuti persistence boundary yang berlaku secara umum.

```text
PROGRESSION RESULT
↓
STATE CHANGE
↓
STATE VALIDATION
↓
VALIDATED CHANGE SET
↓
PERSISTENCE
↓
VERIFY
```

Progression tidak boleh menyatakan bahwa capability telah tersimpan secara resmi tanpa persistence verification.

---

## 33. Time Integration

Time & Calendar tetap menjadi canonical temporal authority.

Progression dapat menggunakan temporal context ketika durasi, urutan, atau waktu proses memang relevan dan memiliki basis yang sah.

V0.1 tidak menetapkan:

- universal training duration;
- universal practice duration;
- universal learning duration;
- universal progression interval;
- universal simulation tick;
- universal advancement schedule.

Jika waktu yang diperlukan belum diketahui, gunakan Unknown / Undefined atau mekanisme temporal yang relevan.

---

## 34. Autonomous Progression

Progression dapat terjadi melalui autonomous world process jika proses tersebut memiliki basis yang valid.

Contoh konseptual:

```text
NPC / WORLD PROCESS
↓
VALID TRAINING / EXPERIENCE / LEARNING
↓
PROGRESSION
↓
STATE CHANGE
```

Autonomous progression tidak berarti random advancement.

Perubahan harus dapat ditelusuri ke actor, event, process, state, Canon, atau basis valid lainnya.

---

## 35. Knowledge Boundary

Progression mengikuti knowledge boundaries Eldoria:

```text
CANON FACT
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
≠
NPC KNOWLEDGE
```

Player Knowledge tidak otomatis menjadi Character Knowledge atau NPC Knowledge.

Suatu kemampuan tidak boleh diperoleh melalui “learning” jika sumber learning tersebut tidak dapat diakses atau diketahui oleh subject secara sah.

---

## 36. Unknown / Undefined

Progression harus mempertahankan:

```text
UNKNOWN
UNDEFINED
```

Tidak boleh mengisi informasi yang belum didefinisikan dengan:

```text
ZERO
DEFAULT
AVERAGE
ASSUMED VALUE
ASSUMED XP
ASSUMED MASTERY
ASSUMED PREREQUISITE
```

Jika mechanic yang dibutuhkan belum tersedia, gunakan `UNKNOWN / UNDEFINED` atau `UNRESOLVED` sesuai konteks.

---

## 37. Failure, No Change & Unresolved

Progression harus membedakan:

```text
VALID PROCESS WITH NO DEVELOPMENT
≠
FAILURE OF THE PROCESS
≠
UNRESOLVED PROGRESSION
```

Tidak berkembang dapat menjadi hasil progression yang sah ketika proses tidak menghasilkan capability change.

`UNRESOLVED` berarti required Canon, data, atau mechanic belum tersedia atau tidak dapat diproses secara sah.

Progression tidak boleh mengubah missing mechanic menjadi arbitrary success atau arbitrary failure.

---

## 38. Integrity Rules

- Progression hanya memproses capability yang memiliki basis Canon yang sah.
- Capability definition tetap berada pada domain owner yang relevan.
- Progression mengatur development/acquisition/change, bukan domain mechanics.
- Training adalah mechanism, bukan system terpisah pada v0.1.
- Practice adalah mechanism, bukan system terpisah pada v0.1.
- Experience adalah input, bukan XP.
- Learning adalah mechanism untuk capability development, bukan pengganti knowledge system.
- Action tetap menjadi owner Action structure/lifecycle.
- Resolution tetap menjadi owner generic resolution contract dan domain resolution tetap memiliki authority masing-masing.
- Combat tetap owner combat resolution.
- Supernatural / Magic tetap owner supernatural mechanics.
- NPC Behavior tetap owner NPC decision-making dan knowledge context.
- Items / Equipment tetap owner item/equipment semantics.
- State & History tetap owner State/History semantics.
- Persistence tetap owner save/persistence.
- Progression Result bukan otomatis State Change.
- State Change harus melalui State Validation.
- Persistent changes harus memiliki provenance yang relevan.
- Starting State tidak ditimpa oleh progression normal.
- Unknown / Undefined tidak boleh diisi asumsi.
- Tidak ada automatic advancement universal.
- Tidak ada universal progression formula.
- Tidak ada universal XP, level, tier, rank, skill point, atau attribute point system.
- Tidak ada universal training, practice, learning, atau experience conversion formula.
- Autonomous progression membutuhkan valid basis.
- Progression tidak boleh digunakan untuk memperbaiki inconsistency atau missing Canon secara diam-diam.

---

## 39. Explicit Non-Goals v0.1

Progression v0.1 **tidak menetapkan**:

```text
❌ XP
❌ XP threshold
❌ Level
❌ Level-up
❌ Skill Points
❌ Attribute Points
❌ Skill Tree
❌ Class
❌ Tier
❌ Rank
❌ Mastery Percentage
❌ Universal Progression Percentage
❌ Universal Advancement Formula
❌ Universal Training Formula
❌ Universal Practice Formula
❌ Universal Learning Formula
❌ Universal Experience Conversion
❌ Automatic Advancement
❌ Universal Capability Stat Block
```

Mekanisme tersebut hanya dapat diperkenalkan melalui Canon lanjutan apabila kebutuhan nyata telah diaudit dan desainnya memiliki boundary yang jelas.

---

## 40. Canonical Ownership Matrix

| Concept | Canonical Owner |
|---|---|
| Character structure | Character Data Model |
| Attribute representation | Character Data Model / relevant Canon |
| Attribute development | Progression |
| Ability definition | Relevant domain |
| Ability acquisition | Progression |
| Ability development | Progression |
| Capability change | Progression |
| Training as progression mechanism | Progression |
| Practice as progression mechanism | Progression |
| Experience as progression input | Progression |
| Learning for capability development | Progression |
| NPC knowledge / belief update | NPC Behavior & Agency |
| NPC decision / action selection | NPC Behavior & Agency |
| Action structure / lifecycle | Action Model |
| Generic Result contract | Resolution Architecture |
| Combat mechanics / outcome | Combat |
| Supernatural / magical mechanics | Supernatural / Magic |
| Item / equipment semantics | Items / Equipment |
| Current State semantics | State & History |
| History semantics | State & History |
| State Change validation | State Validation |
| Persistence | Persistence |
| Temporal authority | Time & Calendar |

---

## 41. Dependency Graph

```text
                         CHARACTER
                            │
                            ↓
                     CURRENT STATE
                            │
                            ↓
                          ACTION
                            │
                            ↓
                       RESOLUTION
                            │
                            ↓
                          RESULT
                            │
              ┌─────────────┼─────────────┐
              ↓             ↓             ↓
           COMBAT         MAGIC         WORLD
              │             │             │
              └─────────────┼─────────────┘
                            ↓
                 TRAINING / PRACTICE /
                 EXPERIENCE / LEARNING
                            │
                            ↓
                       PROGRESSION
                            │
                 ┌──────────┼──────────┐
                 ↓          ↓          ↓
             ATTRIBUTE    ABILITY   CAPABILITY
             DEVELOPMENT ACQUISITION DEVELOPMENT
                 └──────────┼──────────┘
                            ↓
                  PROGRESSION RESULT
                            ↓
                    STATE CHANGE
                            ↓
                   STATE VALIDATION
                            ↓
                         HISTORY
                            ↓
                      PERSISTENCE
                            ↓
                         VERIFY
```

Items / Equipment dan NPC Behavior dapat menjadi context/source dalam proses tersebut tanpa mengambil alih Progression ownership.

---

## 42. Runtime Integration

Progression mengikuti runtime architecture Eldoria:

```text
INPUT / WORLD PROCESS
↓
ACTION / EVENT / AUTONOMOUS PROCESS
↓
VALIDATION
↓
RESOLUTION / RELEVANT DOMAIN
↓
RESULT
↓
PROGRESSION EVALUATION
↓
PROGRESSION RESULT
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE / NEXT PROCESS
```

Tidak setiap Action atau Result harus masuk ke Progression. Hanya proses yang relevan terhadap capability development yang diproses lebih lanjut.

---

## 43. Future Extensions

Progression v0.1 dapat menjadi fondasi bagi extension yang benar-benar diperlukan kemudian, misalnya:

```text
ATTRIBUTE DEVELOPMENT RULES
ABILITY DEVELOPMENT RULES
TRAINING FRAMEWORKS
LEARNING SYSTEMS
EXPERIENCE TRACKING
SPECIALIZED PROGRESSION DOMAINS
CAPABILITY LOSS / REGRESSION
OTHER CANON-DEFINED DEVELOPMENT MECHANISMS
```

Extension tersebut tidak menjadi bagian v0.1 secara otomatis.

Setiap extension harus melalui audit dependency dan overlap sebelum menjadi Canon.

---

## 44. Canon Boundary

Progression v0.1 mendefinisikan **ownership, semantics, lifecycle, inputs, outputs, dependencies, dan integrity boundary** untuk capability development.

Progression v0.1 sengaja tidak menentukan mekanik advancement numerik atau struktur RPG universal.

Prinsip akhirnya:

```text
VALID PROCESS
↓
PROGRESSION
↓
CAPABILITY CHANGE
↓
STATE
↓
HISTORY
```

Dengan boundary:

```text
PROGRESSION
≠ COMBAT
≠ MAGIC
≠ NPC DECISION
≠ ITEMS
≠ ACTION
≠ GENERIC RESOLUTION
≠ STATE
≠ HISTORY
≠ PERSISTENCE
```
