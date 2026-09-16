# Eldoria World — Relationships v0.1

> **System:** #06 — Relationships  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Relationships menetapkan **canonical owner** untuk state hubungan antara actor atau entity yang relevan dalam simulasi Eldoria, termasuk pembentukan, perubahan, pemeliharaan, deterioration, termination, dan konsekuensi relationship yang memang didukung oleh Canon dan resolution yang relevan.

Modul ini membuat hubungan menjadi data dunia yang dapat direpresentasikan, divalidasi, dirujuk oleh system lain, dan dipersistenkan bila relationship tersebut memiliki dampak continuity.

Modul ini tidak menetapkan daftar hubungan universal, relationship score, personality formula, atau hasil sosial yang otomatis.

---

## 2. Canonical Boundary

```text
RELATIONSHIPS
= relationship state + relationship lifecycle + relationship change

NPC BEHAVIOR & AGENCY
= bagaimana NPC mengambil keputusan dengan relationship sebagai context

FACTIONS
= struktur, membership, tujuan, sumber daya, dan hubungan faction

POLITICS
= authority, governance, jurisdiction, diplomacy, dan hubungan politik

ECONOMY
= transaksi, ownership, debt, kontrak, dan proses ekonomi

CHARACTER DATA MODEL
= struktur data karakter dan reference terhadap relationship

STATE & HISTORY
= state snapshot, provenance, history, correction, persistence
```

Dependency tidak memindahkan canonical authority.

---

## 3. Core Principles

1. Relationship adalah bagian dari world state ketika memiliki dampak persisten atau relevan terhadap simulasi.
2. Relationship bukan sekadar label narrative.
3. Relationship tidak otomatis memiliki numeric score.
4. Tidak ada universal relationship scale yang wajib berlaku untuk semua actor.
5. Relationship dapat berbeda menurut konteks, pihak, waktu, dan pengetahuan yang tersedia.
6. Relationship state tidak sama dengan intention, belief, opinion, atau action.
7. Relationship intent ≠ relationship result ≠ relationship state change.
8. Relationship tidak dapat berubah hanya karena Player atau NPC menyatakan keinginan.
9. Perubahan relationship harus memiliki sebab, resolution, atau proses dunia yang sah.
10. Unknown / Undefined tidak boleh diisi dengan asumsi.
11. Relationship tidak menghapus agency actor.
12. Relationship tidak menjamin perilaku tertentu.
13. Hubungan satu actor dengan suatu group tidak otomatis menentukan hubungan actor dengan seluruh anggota group.
14. Persistent relationship changes mengikuti State & History Model.
15. Narrative tidak otomatis menjadi relationship state.

---

## 4. Relationship Scope

Relationship dapat terjadi antara entity yang secara Canon dapat memiliki hubungan relevan, misalnya:

- Character ↔ NPC;
- NPC ↔ NPC;
- Character ↔ Faction;
- NPC ↔ Faction;
- Faction ↔ Faction;
- Character ↔ community atau institution;
- actor ↔ political entity;
- actor ↔ business atau organization;
- entity ↔ entity lain yang valid.

Tidak semua hubungan harus direpresentasikan sebagai relationship record. Record dibuat ketika hubungan perlu diketahui, digunakan, divalidasi, atau dipertahankan oleh runtime.

---

## 5. Relationship vs Other Concepts

```text
RELATIONSHIP
≠ OPINION
≠ BELIEF
≠ INTENT
≠ GOAL
≠ REPUTATION
≠ AUTHORITY
≠ OWNERSHIP
≠ MEMBERSHIP
≠ TRANSACTION
≠ ALLIANCE
```

Konsep tersebut dapat saling memengaruhi, tetapi tetap memiliki canonical owner masing-masing.

Contoh:

```text
NPC A mempercayai NPC B
        ↓
relationship context dapat relevan
        ↓
NPC A memilih membantu NPC B
```

Kepercayaan tidak otomatis berarti bantuan berhasil, dan bantuan berhasil tidak otomatis mengubah semua aspek relationship.

---

## 6. Relationship State

Relationship State adalah kondisi hubungan yang berlaku antara pihak tertentu pada konteks dan waktu tertentu.

State dapat mencakup secara konseptual:

- jenis atau bentuk hubungan jika telah ditetapkan;
- kondisi hubungan saat ini;
- konteks hubungan;
- pihak yang terlibat;
- relevant obligations atau expectations jika Canon mendukungnya;
- restrictions atau conditions jika relevan;
- current state reference;
- history reference.

Tidak ada field universal yang harus memuat semua relationship.

---

## 7. Relationship Context

Relationship harus dibaca dalam konteks.

Context dapat mencakup:

- identity pihak;
- waktu;
- lokasi atau lingkungan;
- riwayat interaksi yang relevan;
- knowledge yang tersedia;
- faction context;
- political context;
- economic context;
- social context;
- supernatural context jika relevan;
- obligations atau commitments yang telah sah;
- kondisi lain yang ditetapkan Canon.

Satu relationship dapat memiliki konteks yang berbeda tanpa harus mengubah fakta lain secara otomatis.

---

## 8. Relationship Formation

Relationship dapat terbentuk melalui proses yang sah, misalnya:

```text
INTERACTION
EVENT
COOPERATION
CONTRACT / OBLIGATION
CONFLICT
SHARED EXPERIENCE
SOCIAL PROCESS
FACTION PROCESS
POLITICAL PROCESS
OTHER VALID CAUSE
        ↓
VALIDATION / RESOLUTION
        ↓
RELATIONSHIP STATE
```

Pertemuan atau percakapan tidak otomatis menciptakan relationship persisten.

Relationship baru hanya berlaku jika proses yang relevan menghasilkan dasar yang cukup untuk state tersebut.

---

## 9. Relationship Change

Relationship dapat berubah karena:

- interaksi;
- tindakan atau hasil tindakan;
- fulfilled atau broken obligation;
- bantuan atau pengkhianatan;
- konflik;
- kerja sama;
- perubahan kondisi;
- informasi baru;
- perubahan faction/political/economic context;
- event dunia;
- proses lain yang sah.

Perubahan harus berasal dari resolution atau proses yang memiliki authority sesuai.

```text
CAUSE / ACTION / EVENT
        ↓
RELEVANT RESOLUTION
        ↓
RELATIONSHIP CONSEQUENCE
        ↓
VALIDATED STATE CHANGE
```

---

## 10. No Automatic Relationship Outcome

Player dapat menyatakan:

```text
"Saya ingin berteman dengan NPC A."
```

Itu adalah intent, bukan state.

NPC dapat menyatakan:

```text
"Saya memaafkanmu."
```

Pernyataan tersebut menjadi relevant evidence dalam resolution, tetapi perubahan relationship tetap bergantung pada konteks dan hasil yang sah.

```text
INTENT
≠
STATEMENT
≠
RESULT
≠
STATE CHANGE
```

---

## 11. Relationship and NPC Behavior

Relationship merupakan input/context untuk System #05.

```text
RELATIONSHIP STATE
        ↓
NPC BEHAVIOR #05
        ↓
DECISION / INTENT
```

Sebaliknya, keputusan NPC dapat menghasilkan interaction yang kemudian diproses oleh Relationship System.

```text
NPC DECISION
        ↓
ACTION / INTERACTION
        ↓
RELATIONSHIP RESOLUTION
        ↓
RELATIONSHIP STATE
```

Relationship System tidak menentukan apa yang harus dipilih NPC.

NPC Behavior tidak memiliki authority untuk menyimpan universal relationship state.

---

## 12. Social Interaction Resolution

Relationship System dapat menjadi canonical resolution owner untuk **relationship consequences**, tetapi tidak otomatis menjadi universal owner untuk seluruh social interaction.

```text
SOCIAL ACTION
        ↓
CHECK RELEVANT CANON
        ↓
RESOLVE SOCIAL / DOMAIN ACTION
        ↓
RELATIONSHIP CONSEQUENCE
        ↓
RELATIONSHIPS #06
```

Jika social action memerlukan system khusus yang belum tersedia, Relationship System tidak boleh menciptakan formula universal untuk menggantikannya.

---

## 13. Relationship Types

Relationship type dapat didefinisikan oleh Canon atau data dunia ketika dibutuhkan.

Kategori konseptual dapat mencakup:

- family / kinship;
- friendship;
- trust;
- rivalry;
- hostility;
- cooperation;
- mentorship;
- patronage;
- dependency;
- professional relationship;
- contractual relationship;
- political relationship;
- faction relationship;
- other context-specific relationships.

Kategori ini bukan daftar universal dan tidak menentukan outcome secara otomatis.

Satu pair dapat memiliki beberapa relationship dimensions bila Canon mendukungnya.

---

## 14. Multi-Dimensional Relationships

Hubungan tidak harus direduksi menjadi satu label.

Contoh konseptual:

```text
A ↔ B
├── family relationship
├── business relationship
└── political rivalry
```

Satu dimensi dapat berubah tanpa otomatis menghapus dimensi lain.

Jika beberapa perubahan saling bergantung, perubahan tersebut harus divalidasi sebagai satu hasil terintegrasi sesuai Runtime dan State & History.

---

## 15. Symmetry and Asymmetry

Relationship tidak selalu simetris.

```text
A → B: trusts
B → A: distrusts
```

Hubungan dapat memiliki:

- mutual state;
- directional state;
- asymmetric perception;
- different obligations;
- different knowledge;

jika model dan Canon yang relevan mendukungnya.

Jangan mengasumsikan bahwa hubungan A terhadap B otomatis sama dengan hubungan B terhadap A.

---

## 16. Relationship and Knowledge

Relationship State dan Knowledge bukan hal yang sama.

```text
WORLD RELATIONSHIP STATE
        ≠
ACTOR KNOWLEDGE ABOUT THAT RELATIONSHIP
```

Actor dapat salah memahami hubungan, tidak mengetahui perubahan, atau hanya mengetahui sebagian informasi.

NPC Behavior harus menggunakan knowledge yang tersedia bagi NPC, bukan relationship state dunia yang tidak diketahui NPC.

Player juga tidak otomatis mengetahui seluruh relationship state dunia.

---

## 17. Relationship and Reputation

Reputation bukan relationship.

```text
RELATIONSHIP
→ hubungan spesifik antar pihak

REPUTATION
→ bagaimana suatu actor/entity dipandang oleh pihak atau populasi tertentu
```

Satu NPC dapat memiliki relationship baik dengan Character tetapi reputasi Character buruk di komunitasnya.

Tidak ada Reputation System yang didefinisikan oleh modul ini.

---

## 18. Relationship and Factions

Faction dapat menjadi salah satu pihak dalam relationship.

Namun:

```text
FACTION ↔ CHARACTER
        ≠
EVERY MEMBER ↔ CHARACTER
```

Relationship dengan faction tidak otomatis menentukan relationship Character dengan setiap anggota faction.

Sebaliknya, relationship Character dengan satu anggota tidak otomatis menentukan posisi Character terhadap faction secara keseluruhan.

Membership tetap mengikuti Factions.

---

## 19. Relationship and Politics

Relationship dapat memiliki konteks politik.

Namun:

```text
POLITICAL RELATION
≠
PERSONAL RELATION
```

Hubungan diplomatik antar political entities tidak otomatis menjadi friendship atau hostility antar seluruh individu di dalamnya.

Authority, jurisdiction, sovereignty, dan formal political relations tetap mengikuti Politics.

---

## 20. Relationship and Economy

Hubungan dapat dipengaruhi oleh aktivitas ekonomi, kontrak, utang, perdagangan, pekerjaan, atau ownership.

Namun Economic System tetap menjadi owner untuk proses ekonomi.

```text
ECONOMIC PROCESS
        ↓
RESULT / CONSEQUENCE
        ↓
RELATIONSHIP CONSEQUENCE
```

Relationship tidak menciptakan uang, ownership, debt, atau transaction result.

---

## 21. Relationship and Peoples / Civilization

People/Race, culture, community, dan civilization dapat menyediakan konteks hubungan.

Group membership tidak menentukan relationship individual secara otomatis.

```text
GROUP CONTEXT
≠
INDIVIDUAL RELATIONSHIP
```

Relationship harus tetap ditentukan berdasarkan actor, context, knowledge, history, dan valid resolution.

---

## 22. Relationship and Supernatural

Supernatural dapat memengaruhi relationship bila mekanisme supernatural yang relevan telah ditetapkan.

Magic tidak otomatis memaksa friendship, loyalty, love, obedience, trust, atau hostility.

Setiap supernatural effect harus mengikuti `world/SUPERNATURAL_MAGIC.md`.

---

## 23. Relationship Lifecycle

Relationship dapat mengalami lifecycle seperti:

```text
NONE / UNDEFINED
        ↓
FORMATION
        ↓
ACTIVE
        ↓
CHANGED / DEGRADED / STRENGTHENED
        ↓
SUSPENDED / DORMANT (if applicable)
        ↓
ENDED
```

Tahapan tersebut adalah model konseptual. Tidak semua relationship harus melewati seluruh tahap.

Termination tidak berarti History dihapus.

---

## 24. Relationship Obligations & Expectations

Suatu relationship dapat menghasilkan obligation atau expectation jika memiliki dasar yang sah.

Contoh konseptual:

```text
RELATIONSHIP / AGREEMENT
        ↓
OBLIGATION
        ↓
FULFILLMENT / BREACH
        ↓
CONSEQUENCE
        ↓
POSSIBLE RELATIONSHIP CHANGE
```

Relationship tidak otomatis menciptakan kewajiban hukum atau ekonomi. Formal obligation mengikuti Canon dan domain yang relevan.

---

## 25. Relationship Conflict

Relationship dimensions dapat saling bertentangan.

Contoh:

```text
FAMILY LOYALTY
      ↕
POLITICAL DUTY
```

Konflik tersebut menjadi context untuk actor decision atau domain resolution. Relationship System tidak menentukan keputusan moral atau pilihan actor secara universal.

---

## 26. Autonomous Relationship Change

Relationship dapat berubah tanpa keputusan Player jika perubahan tersebut berasal dari valid world process.

Contoh:

```text
NPC ACTION
FACTION CHANGE
POLITICAL EVENT
ECONOMIC EVENT
SHARED EVENT
TIME-DEPENDENT PROCESS (if Canon supports it)
        ↓
RELATIONSHIP CONSEQUENCE
        ↓
VALIDATED STATE CHANGE
```

Tidak ada autonomous relationship change tanpa basis.

---

## 27. Runtime Integration

Relationship mengikuti Runtime Turn Model:

```text
LOAD CURRENT STATE
        ↓
PLAYER / NPC ACTION
        ↓
PARSE INTENT
        ↓
VALIDATE
        ↓
RELEVANT DOMAIN RESOLUTION
        ↓
RELATIONSHIP CONSEQUENCE
        ↓
GENERATE STATE CHANGE
        ↓
VALIDATE STATE CHANGE
        ↓
APPLY CURRENT STATE
        ↓
CREATE HISTORY
        ↓
PERSIST
        ↓
VERIFY
```

Untuk beberapa action berurutan, relationship state hasil action sebelumnya menjadi context untuk action berikutnya.

---

## 28. State & History Integration

Relationship yang persistent dapat memiliki Current State dan History Reference.

Perubahan mengikuti:

```text
CAUSE / ACTION / EVENT
        ↓
VALIDATE
        ↓
RESOLVE
        ↓
RELATIONSHIP STATE CHANGE
        ↓
STATE VALIDATION
        ↓
APPLY
        ↓
HISTORY
        ↓
PERSIST
        ↓
VERIFY
```

Minimum provenance harus dapat menjelaskan pihak yang berubah, field/property relationship yang berubah, previous value, new value, origin, source, dan World Time ketika diwajibkan oleh State & History Model.

---

## 29. Data Model

Struktur konseptual:

```text
RELATIONSHIP
├── Relationship ID
├── Actor A / Subject A
├── Actor B / Subject B
├── Relationship Context
├── Relationship Type(s) (if defined)
├── Current State
├── Conditions / Obligations (if applicable)
├── World Time Reference
├── Current State Reference
├── History Reference
└── Metadata
```

### Relationship State Change

```text
RELATIONSHIP STATE CHANGE
├── Change ID
├── Relationship ID
├── Field / Property
├── Previous Value
├── New Value
├── Origin
├── Source
├── World Time
└── Validation Status
```

Data model ini konseptual dan tidak memaksa numeric score.

---

## 30. Knowledge Boundary

```text
RELATIONSHIP CANON / STATE
        ≠
NPC KNOWLEDGE
        ≠
CHARACTER KNOWLEDGE
        ≠
PLAYER KNOWLEDGE
```

AI GM tidak boleh memberikan actor informasi relationship yang tidak secara sah diketahui actor tersebut.

Rumor, assumption, suspicion, dan belief tidak otomatis mengubah Relationship State.

---

## 31. No Universal Formula

V0.1 tidak menetapkan:

- relationship score;
- affection score;
- trust score;
- loyalty score;
- hostility percentage;
- friendship percentage;
- attraction formula;
- decay formula;
- universal relationship thresholds;
- universal social success probability;
- universal relationship change multiplier;
- universal relationship value.

Jika mekanik kuantitatif dibutuhkan di masa depan, mekanik tersebut harus dibuat sebagai Canon eksplisit dan diaudit terhadap system lain.

---

## 32. Integrity Rules

1. Relationship state harus memiliki pihak yang dapat diidentifikasi.
2. Relationship tidak boleh dibuat hanya karena narrative menyebutkannya.
3. Intent tidak otomatis menjadi relationship state.
4. Relationship change harus memiliki dasar yang valid.
5. Relationship System tidak mengambil alih authority NPC Behavior, Factions, Politics, Economy, atau domain lain.
6. Relationship tidak boleh menciptakan universal score sebagai fallback.
7. Relationship A → B tidak otomatis sama dengan B → A.
8. Relationship dengan faction tidak otomatis berlaku untuk seluruh anggota faction.
9. Political relationship tidak otomatis menjadi personal relationship.
10. Economic transaction tidak otomatis menjadi relationship state.
11. Knowledge tentang relationship harus dibedakan dari relationship state itu sendiri.
12. Unknown / Undefined tetap Unknown / Undefined.
13. Persistent relationship change harus mengikuti State & History Model.
14. History relationship tidak boleh dihapus atau ditimpa secara diam-diam.
15. AI GM tidak boleh mengklaim relationship telah dipersistenkan tanpa verifikasi.
16. Relationship tidak boleh digunakan untuk mengambil alih keputusan penting Player Character.

---

## 33. Progressive Development

```text
RELATIONSHIP FRAMEWORK
        ↓
RELATIONSHIP DATA / STATE
        ↓
SOCIAL / INTERACTION RESOLUTION
        ↓
REPUTATION / INFORMATION / QUEST DEPENDENCIES
        ↓
RICHER SOCIAL SIMULATION
```

Future systems dapat menggunakan Relationship sebagai dependency tanpa mengubah ownership relationship.

---

## 34. Canon Boundary

Relationships v0.1 **tidak** menetapkan secara universal:

- daftar relationship lengkap Eldoria;
- relationship score;
- personality formula;
- universal social formula;
- attraction/love formula;
- friendship formula;
- trust/loyalty formula;
- universal relationship decay;
- universal social success probability;
- daftar NPC atau character relationship spesifik;
- reputasi global;
- hukum atau kewajiban universal yang muncul dari relationship;
- political diplomacy rules;
- economic transaction rules;
- NPC decision formula.

Detail tersebut hanya menjadi Canon setelah didefinisikan secara resmi oleh system/data yang memiliki authority.
