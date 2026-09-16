# Eldoria World — Reputation v0.1

> **System:** #07 — Reputation  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Reputation menetapkan **canonical owner** untuk bagaimana suatu actor atau entity dipandang oleh pihak, kelompok, komunitas, atau audience tertentu dalam konteks dunia Eldoria.

Reputation digunakan sebagai contextual world state dan information context yang dapat memengaruhi interaksi, NPC decision-making, faction behavior, politics, economy, atau proses dunia lain ketika relevan.

Modul ini tidak menetapkan satu reputasi global untuk setiap actor, tidak menjadikan reputation sebagai kebenaran moral objektif, dan tidak menetapkan universal score, threshold, multiplier, decay, probability, atau automatic reaction.

---

## 2. Canonical Boundary

```text
REPUTATION
= bagaimana actor / entity dipandang oleh audience tertentu
  dalam konteks tertentu

RELATIONSHIPS
= relationship state / lifecycle / relationship change

NPC BEHAVIOR & AGENCY
= NPC decision-making menggunakan reputation sebagai context

FACTIONS
= faction structure, membership, goals, resources, influence,
  faction relations, serta contextual faction reputation

POLITICS
= authority, governance, jurisdiction, legitimacy, political relations

ECONOMY
= economic processes, transactions, ownership, debt, contracts

PEOPLES / RACES & CIVILIZATION
= group, cultural, social, and institutional context

STATE & HISTORY
= state, provenance, history, persistence
```

Dependency tidak memindahkan canonical authority.

---

## 3. Core Principles

1. Reputation bersifat contextual, bukan universal.
2. Reputation bukan kebenaran objektif tentang actor.
3. Reputation dapat berbeda menurut audience, wilayah, kelompok, actor, waktu, dan konteks.
4. Reputation dapat bersifat asymmetric.
5. Reputation dapat memiliki lebih dari satu aspek atau domain tanpa harus direduksi menjadi satu nilai.
6. Reputation State berbeda dari actor knowledge atau belief tentang reputation.
7. Reputation intent ≠ reputation result ≠ reputation state change.
8. Rumor, klaim, atau opini tidak otomatis menjadi reputation state tanpa proses yang sah.
9. Reputation tidak otomatis menentukan perilaku pihak lain.
10. Reputation tidak otomatis menciptakan membership, authority, legitimacy, ownership, wealth, alliance, hostility, atau relationship.
11. Reputation tidak menghapus agency actor atau audience.
12. Unknown / Undefined tetap Unknown / Undefined.
13. Tidak ada universal reputation score, rating, multiplier, threshold, probability, decay formula, atau quantitative fallback pada v0.1.
14. Persistent reputation changes mengikuti State & History Model dan memerlukan provenance yang sesuai.
15. Reputation tidak boleh dibuat atau diubah hanya untuk memajukan plot atau menghukum Player.

---

## 4. Reputation Scope

Reputation dapat berlaku terhadap entity yang dapat dipandang atau dinilai oleh audience tertentu, misalnya:

- Character;
- NPC;
- faction;
- business atau organization;
- political actor;
- institution;
- settlement atau community jika relevan;
- People/Race atau kelompok sosial dalam konteks tertentu;
- entity lain yang valid menurut Canon.

Tidak semua entity harus memiliki reputation record.

Reputation record dibuat atau dipertahankan ketika reputation perlu diketahui, digunakan, divalidasi, atau dipersistenkan oleh runtime.

---

## 5. Reputation Subject & Audience

Reputation membutuhkan pembedaan antara **subject** dan **audience**.

```text
REPUTATION SUBJECT
        ↓
AUDIENCE / OBSERVER
        ↓
CONTEXT
        ↓
REPUTATION STATE
```

Audience dapat berupa:

- individual actor;
- keluarga atau kelompok sosial;
- faction;
- profession atau community;
- settlement;
- political authority;
- market atau economic network;
- People/Race community;
- region;
- population tertentu;
- audience lain yang valid.

Audience bukan selalu keseluruhan dunia.

---

## 6. Context & Scope

Reputation harus dibaca dalam konteks yang relevan.

Context dapat mencakup:

- audience;
- lokasi atau wilayah;
- waktu;
- domain kegiatan;
- profession atau role;
- jenis tindakan atau event;
- social context;
- faction context;
- political context;
- economic context;
- cultural context;
- supernatural context jika relevan;
- sumber informasi;
- history yang relevan;
- kondisi lain yang ditetapkan Canon.

Reputation di satu tempat atau audience tidak otomatis berlaku di tempat atau audience lain.

---

## 7. Reputation State

Reputation State adalah kondisi bagaimana subject dipandang oleh audience tertentu pada konteks dan waktu tertentu.

State dapat mencakup secara konseptual:

- subject;
- audience;
- reputation context/domain;
- current characterization atau standing jika telah didukung oleh data;
- basis/evidence reference;
- source reference;
- World Time reference;
- current state reference;
- history reference;
- conditions atau scope tambahan bila relevan.

Tidak ada field universal yang wajib memuat semua reputation.

---

## 8. Multi-Dimensional Reputation

Reputation tidak harus direduksi menjadi satu label atau satu nilai.

Contoh konseptual:

```text
CHARACTER A
├── known as reliable merchant
├── regarded as dangerous fighter
└── distrusted in political circles
```

Dimensi tersebut dapat berbeda menurut audience dan konteks.

```text
REPUTATION DIMENSION
≠
UNIVERSAL CHARACTER JUDGMENT
```

Tidak ada daftar dimensi universal yang wajib digunakan.

---

## 9. Local, Group-Specific & Actor-Specific Reputation

Reputation dapat bersifat:

```text
LOCAL
GROUP-SPECIFIC
ACTOR-SPECIFIC
CONTEXTUAL
ASYMMETRIC
TIME-DEPENDENT
```

Contoh konseptual:

```text
Town A:
Character dikenal sebagai pedagang dapat dipercaya.

Faction B:
Character dianggap tidak dapat dipercaya.

NPC C:
Character dikenal sebagai orang yang pernah menolongnya.
```

Ketiganya dapat coexist tanpa konflik karena audience dan context berbeda.

---

## 10. Reputation vs Relationship

```text
RELATIONSHIP
→ hubungan spesifik antar pihak

REPUTATION
→ bagaimana subject dipandang oleh audience
```

Relationship dengan satu NPC dapat menjadi salah satu basis informasi atau pengalaman yang memengaruhi reputation, tetapi Relationship System tetap menjadi owner relationship state.

Sebaliknya, reputation buruk tidak otomatis menciptakan hostility atau mengubah relationship setiap individu dalam audience.

---

## 11. Reputation vs NPC Behavior

NPC dapat menggunakan reputation sebagai decision context apabila NPC secara sah mengetahui atau mempercayai informasi tersebut.

```text
REPUTATION INFORMATION
        ↓
NPC KNOWLEDGE / BELIEF
        ↓
NPC BEHAVIOR & AGENCY #05
        ↓
NPC DECISION / INTENT
```

Reputation tidak memaksa NPC melakukan satu respons tertentu.

NPC Behavior tetap menjadi owner untuk NPC decision-making.

NPC dapat memiliki informasi reputation yang salah, tidak lengkap, outdated, atau berbeda dari world reputation state.

---

## 12. Reputation vs Knowledge

```text
WORLD REPUTATION STATE
        ≠
ACTOR KNOWLEDGE ABOUT REPUTATION
        ≠
ACTOR BELIEF / INTERPRETATION
```

Actor tidak otomatis mengetahui seluruh reputation state dunia.

Information dapat diperoleh melalui:

- direct observation;
- personal experience;
- conversation;
- witnesses;
- reports;
- documents;
- faction networks;
- travel;
- social interaction;
- valid supernatural means;
- sumber informasi lain yang sah.

Rumor tetap rumor sampai proses dunia yang sah menghasilkan perubahan informasi atau reputation yang relevan.

---

## 13. Reputation Formation

Reputation dapat terbentuk melalui proses yang sah, misalnya:

```text
ACTION / EVENT / ACHIEVEMENT / FAILURE
        ↓
OBSERVATION / INFORMATION FLOW
        ↓
AUDIENCE INTERPRETATION
        ↓
SOCIAL PROCESS / RELEVANT RESOLUTION
        ↓
REPUTATION STATE
```

Basis dapat mencakup:

- tindakan yang terlihat;
- hasil tindakan;
- repeated conduct;
- service atau contribution;
- misconduct;
- public event;
- testimony;
- records;
- association;
- relationship experience;
- faction activity;
- political activity;
- economic conduct;
- supernatural event;
- other valid cause.

Tidak semua tindakan otomatis menghasilkan perubahan reputation.

---

## 14. Reputation Evidence & Provenance

Reputation yang persisten harus memiliki basis yang dapat ditelusuri jika basis tersebut diperlukan oleh State & History Model.

Evidence dapat berupa:

- event;
- action result;
- observation;
- testimony;
- document;
- public record;
- social transmission;
- prior reputation state;
- other valid source.

```text
SOURCE / EVIDENCE
        ↓
INTERPRETATION / SOCIAL PROCESS
        ↓
REPUTATION CHANGE
```

Evidence tidak selalu berarti kebenaran objektif. Audience dapat membentuk reputation berdasarkan informasi yang salah atau tidak lengkap apabila proses dunia mendukungnya.

---

## 15. Reputation Change

Reputation dapat berubah karena:

- tindakan atau hasil tindakan;
- achievement atau failure;
- public event;
- testimony atau information flow;
- repeated conduct;
- association;
- faction activity;
- political activity;
- economic conduct;
- relationship-related experience;
- correction of prior information;
- other valid world process.

Perubahan mengikuti:

```text
CAUSE / INFORMATION / EVENT
        ↓
VALIDATION / RELEVANT RESOLUTION
        ↓
AUDIENCE REACTION / SOCIAL PROCESS
        ↓
REPUTATION CONSEQUENCE
        ↓
VALIDATED STATE CHANGE
```

Tidak ada universal reputation delta atau perubahan otomatis.

---

## 16. No Automatic Reputation Outcome

Player dapat menyatakan:

```text
"Saya ingin semua orang menghormati saya."
```

Itu adalah intent, bukan reputation state.

Character dapat memenangkan duel secara nyata, tetapi reputation consequence tetap bergantung pada siapa yang mengetahui, bagaimana informasi menyebar, bagaimana audience menafsirkan kejadian, dan proses sosial yang valid.

```text
INTENT
≠
RESULT
≠
REPUTATION CHANGE
≠
REPUTATION STATE
```

---

## 17. Reputation Propagation

Reputation tidak otomatis menyebar ke semua audience.

```text
KNOWN BY A
≠
KNOWN BY B
≠
KNOWN BY C
```

Penyebaran reputation membutuhkan basis informasi atau proses sosial yang valid.

Reputation dari satu individual tidak otomatis menjadi reputation seluruh faction.

Reputation faction tidak otomatis menjadi reputation setiap member.

Reputation di satu settlement tidak otomatis menjadi reputation di seluruh region.

---

## 18. Reputation & Factions

Factions dapat memiliki reputation yang berbeda menurut audience.

`world/FACTIONS.md` tetap menjadi owner untuk faction structure, membership, goals, resources, influence, dan faction relations.

```text
FACTION REPUTATION
        ↓
REPUTATION #07
```

Reputation dapat digunakan sebagai context dalam recruitment, recognition, negotiation, atau faction decision apabila proses tersebut mendukungnya.

Reputation tidak otomatis menentukan membership, loyalty, authority, influence, atau legitimacy.

---

## 19. Reputation & Politics

Reputation dapat menjadi context politik atau sumber political influence jika kondisi politik mendukungnya.

Namun:

```text
REPUTATION
≠
AUTHORITY
≠
LEGITIMACY
≠
JURISDICTION
≠
SOVEREIGNTY
≠
CONTROL
```

Politics tetap menjadi owner untuk authority, governance, jurisdiction, legitimacy, dan formal political relations.

Reputation tidak otomatis menghasilkan jabatan atau kewenangan politik.

---

## 20. Reputation & Economy

Reputation dapat memengaruhi atau menjadi context dalam economic interaction, misalnya ketika actor mempertimbangkan reliability atau standing suatu merchant.

Namun:

```text
REPUTATION
≠
OWNERSHIP
≠
WEALTH
≠
INCOME
≠
LIQUIDITY
≠
TRANSACTION
```

Economy tetap menjadi owner untuk transaksi, harga, ownership, debt, contract, dan proses ekonomi.

Tidak ada economic result yang muncul hanya karena reputation dianggap tinggi atau rendah tanpa resolution yang sah.

---

## 21. Reputation & Peoples / Civilization

Culture, community, People/Race, profession, settlement, dan civilization dapat menjadi audience atau context reputation.

Group perception tidak otomatis menentukan setiap individual perception.

```text
GROUP REPUTATION CONTEXT
≠
EVERY INDIVIDUAL BELIEF
```

Reputation tidak boleh digunakan untuk menetapkan sifat moral atau perilaku inheren suatu People/Race.

---

## 22. Reputation & Supernatural

Supernatural dapat memengaruhi reputation bila mekanisme supernatural yang relevan telah ditetapkan.

Contoh konseptual dapat mencakup:

- magical evidence;
- supernatural event witnessed by an audience;
- magical disguise or identity uncertainty;
- supernatural information transfer;
- other Canon-supported processes.

Magic tidak otomatis membuat reputation benar, salah, terkenal, atau hilang.

Semua supernatural interaction mengikuti `world/SUPERNATURAL_MAGIC.md`.

---

## 23. Reputation & Association

Reputation dapat dipengaruhi oleh association jika audience atau world process memang menganggap association tersebut relevan.

Namun:

```text
ASSOCIATION
≠
AUTOMATIC GUILT
≠
AUTOMATIC PRAISE
```

Reputation suatu actor tidak otomatis diwariskan kepada pihak yang berhubungan dengannya.

---

## 24. Reputation & Time

Reputation dapat berubah seiring waktu apabila ada valid process yang mendukung perubahan tersebut.

```text
TIME PASSAGE
≠
AUTOMATIC REPUTATION DECAY
```

Tidak ada universal reputation decay atau expiration formula pada v0.1.

Perubahan karena waktu hanya dapat terjadi jika Canon atau proses dunia yang relevan benar-benar mendukungnya.

---

## 25. Autonomous Reputation Change

Reputation dapat berubah tanpa keputusan Player apabila perubahan tersebut berasal dari valid world process.

Contoh konseptual:

```text
PUBLIC EVENT
NPC / FACTION ACTION
INFORMATION SPREAD
POLITICAL EVENT
ECONOMIC EVENT
REPEATED CONDUCT
DISCOVERY
CORRECTION
OTHER VALID PROCESS
        ↓
REPUTATION CONSEQUENCE
        ↓
VALIDATED STATE CHANGE
```

AI GM tidak boleh mengubah reputation secara arbitrer hanya untuk menghasilkan quest, reward, punishment, atau plot progression.

---

## 26. Reputation Lifecycle

Reputation dapat mengikuti lifecycle konseptual:

```text
NONE / UNDEFINED
        ↓
FORMATION
        ↓
CURRENT / ACTIVE
        ↓
CHANGED / STRENGTHENED / WEAKENED
        ↓
OUTDATED / DORMANT (if applicable)
        ↓
ENDED / REPLACED (if applicable)
```

Lifecycle tidak menetapkan automatic decay.

Tidak semua reputation harus melewati semua tahap.

History tidak dihapus hanya karena reputation berubah atau tidak lagi aktif.

---

## 27. Runtime Integration

Reputation mengikuti Runtime Turn Model:

```text
LOAD CURRENT REPUTATION STATE
        ↓
LOAD RELEVANT AUDIENCE / ACTOR CONTEXT
        ↓
PLAYER / NPC / WORLD ACTION OR EVENT
        ↓
PARSE INTENT / INFORMATION
        ↓
VALIDATE
        ↓
RELEVANT DOMAIN RESOLUTION
        ↓
REPUTATION CONSEQUENCE
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

Untuk action berurutan, reputation state dan information yang telah berubah menjadi context untuk action berikutnya sesuai knowledge boundary.

Jika action tidak memiliki relevant reputation consequence, reputation tidak boleh dipaksa berubah.

---

## 28. State & History Integration

Reputation yang persisten dapat memiliki Current State dan History Reference.

Perubahan mengikuti:

```text
CAUSE / ACTION / EVENT / INFORMATION PROCESS
        ↓
VALIDATE
        ↓
RESOLVE
        ↓
REPUTATION STATE CHANGE
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

Provenance harus dapat menjelaskan subject, audience atau scope, field/property yang berubah, previous value bila tersedia, new value, origin, source, dan World Time ketika diwajibkan oleh State & History Model.

Correction dilakukan melalui state/history correction yang dapat ditelusuri; tidak ada silent overwrite terhadap historical truth.

---

## 29. Data Model

Struktur konseptual:

```text
REPUTATION
├── Reputation ID
├── Subject ID
├── Audience ID / Audience Scope
├── Context / Domain
├── Current Reputation State
├── Basis / Evidence Reference
├── Source Reference
├── World Time Reference
├── Current State Reference
├── History Reference
└── Metadata
```

Audience dapat berupa individual actor, group, faction, community, settlement, region, institution, political entity, economic network, atau scope lain yang valid.

Tidak ada universal numeric reputation field.

---

## 30. Knowledge Boundary

```text
WORLD REPUTATION STATE
        ≠
NPC KNOWLEDGE
        ≠
PLAYER KNOWLEDGE
        ≠
AUDIENCE BELIEF
        ≠
AI GM INTERNAL INFORMATION
```

AI GM harus membedakan:

- reputation yang benar-benar menjadi world state;
- informasi yang diketahui audience;
- belief atau interpretation audience;
- rumor;
- informasi yang belum diketahui.

Player tidak otomatis mengetahui reputation yang tidak tersedia bagi Character.

NPC tidak boleh menggunakan reputation yang tidak dapat diketahui secara sah.

---

## 31. Integrity Rules

- Reputation selalu memiliki subject dan audience/scope yang dapat diidentifikasi.
- Reputation tidak boleh diperlakukan sebagai universal world-wide value tanpa Canon yang menetapkannya.
- Reputation bukan objective moral truth.
- Rumor tidak otomatis menjadi fact atau reputation state.
- Reputation tidak otomatis menyebar antar audience.
- Reputation tidak otomatis diwariskan dari faction ke member atau sebaliknya.
- Reputation tidak otomatis menghasilkan relationship change.
- Reputation tidak otomatis menghasilkan membership, authority, legitimacy, ownership, wealth, atau transaction.
- NPC Behavior menggunakan reputation sebagai context, bukan deterministic command.
- Politics, Economy, Factions, Relationships, dan domain lain tetap memiliki canonical authority masing-masing.
- Unknown / Undefined tetap Unknown / Undefined.
- Tidak boleh ada numeric fallback, probability, score, multiplier, threshold, decay formula, atau universal reaction rule pada v0.1.
- Persistent reputation change harus memiliki valid basis dan provenance.
- Narrative tidak otomatis menjadi reputation state.
- Persistence harus diverifikasi sebelum diklaim.

---

## 32. Canonical Ownership Audit

| Domain | Canonical Owner | Reputation Role |
|---|---|---|
| Reputation state / lifecycle / reputation change | Reputation #07 | Owner |
| Relationship state / lifecycle / relationship change | Relationships #06 | Boundary / context |
| NPC decision / agency | NPC Behavior & Agency #05 | Context / consumer |
| Faction structure / membership / faction relations | Factions | Context / consumer |
| Political authority / governance / legitimacy | Politics | Context / domain authority |
| Economic transactions / ownership / debt / contracts | Economy | Context / domain authority |
| Peoples / culture / demography | Peoples / Races | Context |
| Civilization / institutions / social structure | Civilization | Context |
| Supernatural rules / effects | Supernatural / Magic | Context / domain authority |
| Time | Time & Calendar #01 | Temporal authority |
| Health / injury | Health & Injury #02 | Consequence authority |
| Combat | Combat #03 | Resolution authority |
| Travel / movement | Travel & Movement #04 | Resolution authority |
| State / provenance / persistence | State & History | State & persistence authority |

Principle:

```text
ONE CANONICAL OWNER
        ↓
CLEAR DEPENDENCIES
        ↓
NO SILENT DUPLICATION
```

---

## 33. Development Boundary

Reputation v0.1 menetapkan framework dan canonical ownership, bukan complete social simulation.

Belum didefinisikan secara universal:

- reputation score;
- reputation rating scale;
- fame level;
- notoriety level;
- reputation decay;
- reputation propagation speed;
- audience population formula;
- probability bahwa rumor dipercaya;
- automatic NPC reaction table;
- universal moral classification;
- universal threshold untuk respect, fear, trust, hostility, atau acceptance;
- reputation multiplier terhadap harga, combat, recruitment, atau social action;
- global reputation ranking.

Jika kebutuhan tersebut muncul, harus dibuat melalui Canon atau system yang sesuai, diaudit terhadap ownership yang sudah ada, dan tidak boleh diisi dengan fallback numerik.

---

## 34. Canon Boundary

Modul ini menjadi Canon untuk **Reputation System #07** mulai saat diintegrasikan ke `INDEX.md` dan commit-nya terverifikasi.

Sebelum suatu reputation spesifik ditetapkan dalam data dunia atau State, AI GM tidak boleh menganggap reputation tersebut sebagai fakta Canon.

Reputation yang belum didefinisikan tetap:

```text
UNKNOWN / UNDEFINED
```

Reputation System tidak memberikan izin untuk menciptakan nama, audience, social standing, event, atau historical fact tanpa basis yang sah.
