# Eldoria World — NPC Behavior & Agency v0.1

> **System:** #05 — NPC Behavior & Agency  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Modul ini menetapkan **canonical owner** untuk decision-making, agency, motivation, priorities, perception, knowledge context, action selection, dan autonomous behavior dari NPC atau aktor sentient non-Player di Eldoria.

Tujuannya adalah memungkinkan NPC menjadi aktor dunia yang dapat bertindak secara mandiri berdasarkan State, Canon, informasi yang tersedia, tujuan, motivasi, konteks, kemampuan, dan constraints yang valid, tanpa menjadikan NPC sebagai alat narrative atau sumber random action tanpa dasar.

Modul ini mengatur bagaimana NPC memilih intent atau action. Modul ini **tidak mengambil alih resolution domain** milik system lain.

---

## 2. Canonical Boundary

```text
NPC BEHAVIOR & AGENCY
= decision-making, agency, motivation,
  priorities, perception/context,
  knowledge context, action selection,
  autonomous behavior

CHARACTER DATA MODEL
= structure and persistent character/NPC data

FACTIONS
= faction structure, membership, goals,
  resources, influence, relations

POLITICS
= authority, governance, jurisdiction,
  political relations

ECONOMY
= economic conditions and processes

CREATURES / ECOLOGY
= biological and ecological creature behavior

TRAVEL & MOVEMENT
= movement / travel resolution

COMBAT
= combat / conflict resolution

HEALTH & INJURY
= health and injury state / consequences

TIME & CALENDAR
= temporal authority

RELATIONSHIPS
= relationship state, lifecycle, and relationship change

STATE & HISTORY
= state, provenance, history, persistence structure
```

NPC Behavior dapat menggunakan output atau context dari system lain, tetapi dependency tidak memindahkan canonical authority.

---

## 3. Core Principles

1. NPC adalah autonomous world actor, bukan narrative puppet.
2. NPC agency tidak berarti NPC bebas dari Canon, State, kemampuan, informasi, waktu, lokasi, resource, hukum, lingkungan, atau konsekuensi.
3. NPC action harus memiliki dasar yang valid.
4. NPC tidak omniscient.
5. NPC Knowledge tidak sama dengan World Canon atau Player Knowledge.
6. NPC Goal tidak menjamin Result.
7. NPC Intent tidak sama dengan Result atau State Change.
8. Personality atau motivation tidak boleh diperlakukan sebagai deterministic script.
9. Autonomy tidak berarti random behavior tanpa dasar.
10. NPC Behavior tidak mengambil alih resolution system lain.
11. NPC Behavior tidak boleh mengambil alih keputusan penting Player Character.
12. Unknown / Undefined tetap Unknown / Undefined.
13. Tidak ada numeric fallback, probability, score, multiplier, threshold, atau formula universal dalam v0.1.
14. Persistent changes mengikuti State & History Model dan memerlukan provenance yang sesuai.
15. NPC tidak boleh dibuat bertindak hanya untuk memajukan plot atau menghukum Player.

---

## 4. NPC Scope

System ini berlaku untuk aktor non-Player yang memiliki kapasitas untuk membuat keputusan dan bertindak sebagai agen sosial atau sentient.

Contoh konseptual:

- individu NPC;
- pemimpin;
- pekerja;
- pedagang;
- anggota faction;
- pejabat;
- tokoh lokal;
- aktor sentient lain yang secara Canon diperlakukan sebagai NPC.

Tidak semua entitas dunia otomatis menjadi NPC.

Makhluk yang behavior-nya terutama ditentukan oleh proses biologis/ecological menggunakan `world/CREATURES_ECOLOGY.md` sebagai canonical owner untuk creature behavior. NPC Behavior dapat digunakan jika suatu entitas memang berada dalam scope NPC dan membutuhkan decision-making sentient/social.

---

## 5. NPC Agency

NPC dapat secara konseptual:

- memiliki tujuan;
- memiliki motivasi;
- memiliki kepentingan;
- memiliki prioritas;
- memiliki informasi terbatas;
- memiliki belief atau asumsi;
- membuat rencana;
- memilih tindakan;
- menolak tindakan;
- menerima atau menolak tawaran;
- bernegosiasi;
- menyembunyikan informasi;
- mencari bantuan;
- mengambil risiko;
- menghindari risiko;
- mengubah rencana;
- membatalkan tujuan;
- merespons kejadian;
- bertindak tanpa keputusan Player.

Daftar ini adalah capability framework, bukan kewajiban bahwa setiap NPC memiliki semua capability tersebut.

---

## 6. Autonomy

Autonomous processing berarti NPC dapat mengambil keputusan tanpa menunggu Player.

```text
NPC CURRENT STATE
      +
NPC KNOWLEDGE
      +
GOALS / MOTIVATIONS
      +
CURRENT CONTEXT
      +
CONSTRAINTS
      ↓
NPC DECISION
      ↓
ACTION / INTENT
```

Autonomy tidak memberikan izin untuk menciptakan fakta atau tujuan tanpa dasar.

NPC autonomous process harus dapat ditelusuri ke Canon, State, valid information, prior events, valid system rules, atau proses dunia yang sah.

Tidak ada universal NPC simulation tick atau interval autonomous processing yang ditetapkan oleh modul ini.

---

## 7. Decision Model

Model konseptual utama:

```text
CURRENT STATE
      ↓
PERCEIVE / ACCESS AVAILABLE INFORMATION
      ↓
INTERPRET CONTEXT
      ↓
IDENTIFY RELEVANT CONDITIONS
      ↓
IDENTIFY GOALS / MOTIVATIONS
      ↓
IDENTIFY AVAILABLE OPTIONS
      ↓
CHECK CONSTRAINTS / RISKS
      ↓
SELECT INTENT
      ↓
TAKE ACTION
      ↓
OBSERVE RESULT
      ↓
UPDATE RELEVANT NPC STATE / KNOWLEDGE
      ↓
REASSESS
```

Model ini tidak menetapkan bahwa NPC selalu memilih tindakan yang objectively optimal.

NPC dapat memilih tindakan yang masuk akal berdasarkan informasi, belief, motivation, priorities, constraints, dan context yang dimilikinya.

---

## 8. Perception & Context

Keputusan NPC harus menggunakan context yang relevan.

Context dapat mencakup:

- current location;
- current time jika tersedia;
- physical condition jika relevan;
- available resources;
- immediate environment;
- known actors;
- known threats;
- recent events;
- relevant relationships;
- faction context;
- political context;
- economic context;
- social context;
- supernatural context jika diketahui dan relevan;
- other valid system state.

NPC tidak otomatis mengetahui seluruh State dunia.

---

## 9. Knowledge Boundary

```text
WORLD CANON
    ≠
NPC KNOWLEDGE
    ≠
PLAYER KNOWLEDGE
    ≠
AI GM INTERNAL INFORMATION
```

NPC hanya boleh menggunakan informasi yang secara sah tersedia baginya.

Sumber pengetahuan dapat mencakup:

- direct observation;
- personal experience;
- conversation;
- documents;
- education;
- occupation;
- faction information;
- relationships;
- reports;
- witnesses;
- travel;
- prior events;
- valid supernatural means.

Information state dapat secara konseptual berupa:

```text
KNOWN
BELIEVED
SUSPECTED
RUMORED
UNKNOWN
```

Kategori tersebut tidak menetapkan numeric confidence.

Rumor tidak menjadi fact hanya karena diketahui NPC.

---

## 10. Belief & Interpretation

NPC dapat memiliki belief yang salah atau tidak lengkap.

```text
NPC BELIEF
    ≠
WORLD FACT
```

Contoh konseptual:

```text
WORLD FACT:
A threat is located in the north.

NPC BELIEF:
The threat is probably in the east.

NPC ACTION:
Avoid the eastern route.
```

Belief NPC tidak mengubah Canon dunia kecuali suatu action kemudian menghasilkan State Change yang valid.

---

## 11. Motivation

NPC dapat memiliki satu atau beberapa motivasi.

Kategori konseptual dapat mencakup:

- survival;
- security;
- resources;
- duty;
- loyalty;
- ambition;
- status;
- wealth;
- relationship;
- revenge;
- curiosity;
- belief;
- fear;
- responsibility;
- personal goals;
- motivasi lain yang valid.

Kategori tersebut bukan daftar universal yang wajib dimiliki semua NPC.

Motivation adalah context untuk keputusan, bukan deterministic command.

---

## 12. Goals

NPC dapat memiliki:

### Immediate Goal
Tujuan langsung yang berkaitan dengan situasi saat ini.

### Short-Term Goal
Tujuan yang memerlukan beberapa action.

### Long-Term Goal
Tujuan jangka panjang.

### Conditional Goal
Tujuan yang aktif atau berubah berdasarkan kondisi tertentu.

```text
GOAL
  ↓
PLAN / INTENT
  ↓
ACTION
  ↓
RESULT
```

Goal tidak menjamin keberhasilan.

---

## 13. Priorities & Conflicting Goals

NPC dapat menghadapi konflik antar tujuan atau kepentingan.

```text
GOAL A
   ↘
    CONFLICT
   ↗
GOAL B
    ↓
NPC DECISION
```

Prioritas dapat dipengaruhi oleh:

- current context;
- urgency;
- motivation;
- relationships;
- perceived risk;
- available resources;
- obligations;
- knowledge;
- other valid constraints.

V0.1 tidak menetapkan universal priority score atau numeric weighting.

---

## 14. Constraints

NPC decision dibatasi oleh kondisi nyata.

Relevant constraints dapat mencakup:

```text
CAPABILITY
KNOWLEDGE
LOCATION
TIME
RESOURCES
LAW
SOCIAL CONDITIONS
RELATIONSHIPS
FACTION CONTEXT
POLITICAL CONDITIONS
ECONOMIC CONDITIONS
ENVIRONMENT
RISK
OTHER VALID CONDITIONS
```

Keinginan NPC tidak menghapus constraints.

---

## 15. Action Candidates

NPC Behavior dapat mengidentifikasi beberapa tindakan yang secara konseptual mungkin dilakukan.

Contoh:

```text
GOAL:
Protect family

OPTIONS:
- stay and defend;
- evacuate family;
- seek help;
- negotiate;
- hide;
- flee;
- other valid action.
```

Tidak ada universal action list.

Option hanya dapat dipilih jika NPC secara valid mampu mempertimbangkannya berdasarkan knowledge, capability, context, dan constraints.

---

## 16. Action Selection

NPC Behavior menghasilkan selected intent atau action.

```text
NPC CONTEXT
     ↓
AVAILABLE OPTIONS
     ↓
CONSTRAINT CHECK
     ↓
MOTIVATION / GOAL CONTEXT
     ↓
NPC DECISION
     ↓
SELECTED INTENT
```

NPC Behavior tidak menyatakan bahwa selected intent otomatis berhasil.

---

## 17. Intent, Result, State Change

```text
NPC INTENT
    ≠
ACTION RESULT
    ≠
STATE CHANGE
```

Contoh:

```text
NPC intent:
Buy a sword.

Economy resolution:
Transaction rejected.

State:
No sword acquired.
```

Intent harus melewati resolution system yang relevan.

---

## 18. Cross-System Resolution

NPC Behavior hanya memilih atau memulai action. System lain menyelesaikan domainnya.

### Travel

```text
NPC DECISION
→ travel to destination
        ↓
TRAVEL & MOVEMENT
→ movement resolution
```

### Combat

```text
NPC DECISION
→ fight / flee / surrender / disengage
        ↓
COMBAT
→ combat resolution
```

### Economy

```text
NPC DECISION
→ buy / sell / work / trade
        ↓
ECONOMY
→ economic resolution
```

### Health

```text
NPC ACTION / WORLD EVENT
        ↓
HEALTH & INJURY
→ health consequence resolution
```

### Relationships / Social Interaction

```text
NPC DECISION
→ negotiate / persuade / refuse / cooperate / interact
        ↓
RELATIONSHIPS
→ relationship consequence / state resolution when applicable
```

Jika domain khusus belum memiliki canonical resolution system, NPC Behavior tidak boleh mengarang formula atau outcome universal untuk menggantikannya. Resolution tetap mengikuti Canon dan context yang tersedia.

NPC Behavior tidak menduplikasi formula atau resolution rule milik system lain.

---

## 19. Reaction Loop

Setelah action menghasilkan result, NPC dapat memperbarui decision context.

```text
DECISION
 ↓
ACTION
 ↓
RESULT
 ↓
CONSEQUENCE
 ↓
NEW STATE / NEW INFORMATION
 ↓
REASSESS
```

Failure, blockage, delay, interruption, rejection, partial outcome, atau unexpected consequence adalah hasil yang valid apabila didukung resolution system terkait.

NPC tidak boleh dipaksa berhasil hanya karena goal masih aktif.

---

## 20. Plans

NPC dapat membentuk plan yang terdiri dari beberapa intended steps.

```text
GOAL
 ↓
PLAN
 ├── STEP A
 ├── STEP B
 └── STEP C
```

Plan bukan jaminan bahwa semua step terjadi.

Jika kondisi berubah atau step gagal:

```text
PLAN
 ↓
REASSESS
 ↓
CONTINUE
OR MODIFY
OR ABANDON
OR SUBSTITUTE
```

Perubahan plan harus memiliki basis dalam NPC state, knowledge, context, atau valid result.

---

## 21. Learning & Information Update

NPC dapat memperbarui knowledge atau belief setelah memperoleh informasi baru.

```text
EVENT / OBSERVATION
        ↓
INFORMATION RECEIVED
        ↓
INTERPRETATION
        ↓
KNOWLEDGE / BELIEF UPDATE
        ↓
FUTURE DECISION
```

Tidak semua event otomatis menghasilkan learning.

NPC hanya memperoleh informasi yang secara valid dapat diamati, disampaikan, ditemukan, atau diperoleh melalui sumber yang sah.

---

## 22. Deception & Information Disclosure

NPC dapat memiliki perbedaan antara internal knowledge dan outward communication.

```text
NPC INTERNAL KNOWLEDGE
        ≠
NPC SPOKEN CLAIM
```

NPC dapat menyembunyikan, mengubah, atau menahan informasi apabila tindakan tersebut memiliki dasar yang valid dari goals, motivations, knowledge, relationships, risks, atau context.

NPC Behavior tidak menetapkan universal deception formula.

---

## 23. Personality

Personality dapat menjadi faktor keputusan NPC.

Contoh konseptual:

- cautious;
- bold;
- sociable;
- private;
- patient;
- impulsive;
- dutiful;
- suspicious;
- curious.

Personality bukan deterministic script.

```text
PERSONALITY
    ≠
ALWAYS SAME ACTION
```

Kondisi dan tujuan dapat menyebabkan NPC dengan personality yang sama mengambil tindakan berbeda.

---

## 24. Relationships

NPC Behavior dapat membaca relationship state sebagai decision context.

```text
RELATIONSHIP STATE
        ↓
NPC DECISION CONTEXT
```

**Canonical ownership Relationship State berada pada `systems/RELATIONSHIPS.md`.**

NPC Behavior tidak boleh menciptakan universal relationship score atau mengubah relationship state tanpa dasar dan authority yang sesuai.

---

## 25. Faction Context

Faction membership dan faction goals dapat menjadi context keputusan NPC.

```text
FACTION CONTEXT
      ↓
NPC INDIVIDUAL DECISION
```

Faction goal tidak otomatis menjadi individual NPC goal.

NPC dapat mendukung, menafsirkan, menolak, atau memprioritaskan kepentingan pribadi terhadap faction context apabila hasil tersebut memiliki dasar yang valid.

Faction structure, membership, resources, influence, dan faction relations tetap berada di bawah `world/FACTIONS.md`.

---

## 26. Political Context

Political conditions dapat memengaruhi NPC decision.

Contoh konseptual:

```text
LAW / AUTHORITY / JURISDICTION
        ↓
NPC DECISION CONTEXT
```

NPC Behavior tidak menciptakan law, jurisdiction, authority, governance, atau political structure.

Domain tersebut tetap dimiliki oleh `world/POLITICS.md`.

---

## 27. Economic Context

NPC dapat mempertimbangkan economic conditions yang valid.

Contoh:

- resources;
- income;
- employment;
- debt;
- prices;
- availability;
- assets;
- economic opportunity.

Namun Economy tetap menjadi canonical owner economic process dan transaction resolution.

```text
NPC DECISION
→ economic action
→ ECONOMY RESOLUTION
```

---

## 28. Creature Boundary

Creature behavior yang berasal dari biology, ecology, habitat, population, food web, territoriality, lifecycle, atau ecological processes tetap berada pada `world/CREATURES_ECOLOGY.md`.

NPC Behavior tidak boleh mengambil alih ecological behavior hanya karena creature tersebut dapat bertindak.

Jika suatu entity secara Canon merupakan NPC/sentient social actor, NPC Behavior dapat mengatur decision-making-nya sesuai scope system ini.

---

## 29. Player Character Boundary

NPC Behavior tidak boleh mengambil alih keputusan penting Player Character.

AI GM tidak boleh menggunakan NPC Behavior sebagai alasan untuk menentukan secara sepihak:

- Player Character intent;
- Player Character belief;
- Player Character decision;
- Player Character voluntary action;
- Player Character goal.

NPC dapat merespons Player Character, tetapi respons tersebut adalah keputusan NPC, bukan kontrol terhadap Player Character.

---

## 30. Autonomous NPC Processing

NPC dapat melakukan proses autonomous ketika Player tidak berinteraksi langsung dengannya.

```text
PLAYER ABSENT
     ↓
NPC CURRENT STATE
     ↓
VALID CONTEXT
     ↓
NPC DECISION
     ↓
ACTION
     ↓
RELEVANT SYSTEM RESOLUTION
     ↓
CONSEQUENCES
     ↓
STATE / HISTORY
```

Tidak ada kewajiban bahwa setiap NPC harus disimulasikan pada setiap Turn.

Frequency, scheduling, batching, simulation tick, atau background processing rules belum ditetapkan oleh v0.1.

---

## 31. Time Integration

NPC Behavior dapat menggunakan World Time ketika decision membutuhkan temporal context.

```text
TIME & CALENDAR
        ↓
NPC DECISION CONTEXT
```

NPC Behavior tidak menciptakan calendar atau universal time duration.

Durasi action ditentukan oleh system yang memiliki domain action tersebut atau context Canon yang valid.

---

## 32. State Integration

NPC Behavior dapat membaca **NPC behavior state, knowledge, goals, plans, dan decision context** yang relevan dengan decision process.

Conceptual flow:

```text
CURRENT NPC BEHAVIOR CONTEXT
        ↓
NPC DECISION
        ↓
ACTION / INTENT
        ↓
RELEVANT SYSTEM RESOLUTION
        ↓
VALIDATED RESULT
        ↓
VALIDATED STATE CHANGE
```

State change harus mengikuti `state/STATE_AND_HISTORY_MODEL.md` dan canonical owner domain masing-masing.

NPC Behavior tidak menjadi owner atas Character State, Faction State, Political State, Economic State, Creature State, Travel State, Combat State, Health State, Relationship State, atau World State hanya karena NPC action dapat memengaruhinya.

Starting State tidak ditimpa secara retroaktif oleh runtime behavior.

---

## 33. History & Provenance

Perubahan persistent yang berasal dari NPC process harus dapat ditelusuri.

```text
NPC PROCESS
 ↓
CAUSE / ACTION / RESULT
 ↓
ORIGIN
 ↓
SOURCE
 ↓
STATE CHANGE
 ↓
HISTORY
```

History mencatat kejadian dan perubahan; History bukan sumber rule baru.

NPC Behavior tidak boleh menggunakan history secara retroaktif untuk membenarkan action yang sebelumnya tidak memiliki basis.

---

## 34. Runtime Integration

NPC Behavior terintegrasi dengan Runtime / Turn Model secara konseptual:

```text
LOAD CURRENT STATE
        ↓
READ NPC CONTEXT
        ↓
READ VALID NPC KNOWLEDGE
        ↓
IDENTIFY ACTIVE GOALS / MOTIVATIONS
        ↓
IDENTIFY AVAILABLE OPTIONS
        ↓
VALIDATE CONSTRAINTS
        ↓
NPC DECISION
        ↓
NPC ACTION / INTENT
        ↓
RELEVANT SYSTEM RESOLUTION
        ↓
RESULT
        ↓
CONSEQUENCES
        ↓
VALIDATED STATE / KNOWLEDGE UPDATE
        ↓
WORLD STATE CHANGE THROUGH CANONICAL OWNER
        ↓
HISTORY
        ↓
PERSIST
        ↓
VERIFY
```

NPC-specific processing tidak boleh melewati validation karena hasilnya dianggap penting bagi narrative.

---

## 35. Validation

Sebelum NPC action diproses, runtime harus memeriksa context yang relevan, termasuk secara konseptual:

```text
Is the NPC capable?
↓
Does the NPC have sufficient relevant information?
↓
Is the intended action possible in the current context?
↓
Are required resources available?
↓
Are relevant law / social / political constraints applicable?
↓
Does another system own the resolution?
```

Jika action tidak valid, hasil dapat berupa blocked, modified, delayed, interrupted, atau bentuk valid lain sesuai system yang relevan.

---

## 36. Failure & Uncertainty

NPC dapat gagal atau salah mengambil keputusan.

Valid outcomes dapat mencakup:

- failure;
- rejection;
- delay;
- interruption;
- incomplete information;
- mistaken belief;
- unavailable option;
- unexpected consequence;
- changed circumstances.

V0.1 tidak menetapkan probability universal untuk outcome tersebut.

---

## 37. Quantitative Mechanics Boundary

NPC Behavior v0.1 **tidak menetapkan**:

```text
❌ personality score
❌ motivation score
❌ goal priority score
❌ confidence percentage
❌ decision probability
❌ loyalty score
❌ fear score
❌ aggression percentage
❌ intelligence modifier
❌ utility formula
❌ weighted decision formula
❌ random action table
❌ universal NPC tick
❌ universal decision interval
❌ universal behavior frequency
```

Angka, formula, probability, multiplier, threshold, atau quantitative fallback hanya boleh ditambahkan melalui Canon eksplisit di masa depan.

---

## 38. NPC Behavior Data Model

Model konseptual:

```text
NPC BEHAVIOR STATE
├── NPC ID
├── Current Goals
├── Active Motivations
├── Priority / Preference Context
├── Known Information
├── Beliefs / Assumptions
├── Current Intent
├── Active Plan
├── Constraints
├── Relevant Relationships
├── Faction Context
├── Political Context
├── Economic Context
├── Environmental Context
├── Recent Relevant Events
├── Behavioral State
├── Current State Reference
├── History Reference
└── Metadata
```

Field di atas adalah conceptual data model. Tidak semua field wajib menjadi literal runtime field pada v0.1.

---

## 39. Behavioral State

NPC dapat memiliki behavioral state yang sesuai context, misalnya secara konseptual:

```text
IDLE
TRAVELING
WORKING
SEARCHING
NEGOTIATING
FLEEING
PURSUING
WAITING
RESTING
PLANNING
RESPONDING
OTHER VALID STATE
```

Daftar ini bukan universal state machine final.

Behavioral State adalah context/status perilaku; ia tidak mengambil alih state process milik system domain lain. Misalnya, `TRAVELING` tidak menggantikan Travel State dan `FLEEING` tidak otomatis menentukan hasil Combat atau Travel.

---

## 40. System Interaction Model

```text
                 NPC BEHAVIOR
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
     FACTIONS       POLITICS       ECONOMY
        │              │              │
        └──────────────┼──────────────┘
                       ↓
                  NPC DECISION
                       │
            ┌──────────┼──────────┐
            ↓          ↓          ↓
         TRAVEL      COMBAT   RELATIONSHIPS
            │          │          │
            └──────────┼──────────┘
                       ↓
                 CONSEQUENCES
                       ↓
              CANONICAL STATE OWNER
                       ↓
                 STATE / HISTORY
                       ↓
                   PERSIST
```

Dependency tidak mengubah canonical ownership.

---

## 41. Canonical Ownership Audit

| Domain | Canonical Owner | NPC Behavior Role |
|---|---|---|
| NPC decision / agency | NPC Behavior & Agency | Owner |
| Character structure | Character Data Model | Consumer / context |
| Faction structure | Factions | Consumer / context |
| Political authority | Politics | Consumer / context |
| Economic process | Economy | Consumer / action source |
| Creature ecology | Creatures / Ecology | Boundary / context |
| Travel resolution | Travel & Movement | Action resolution |
| Combat resolution | Combat | Action resolution |
| Health / injury | Health & Injury | Consequence resolution |
| Time | Time & Calendar | Temporal authority |
| Relationship state / lifecycle / change | Relationships | Consumer / decision context |
| Persistence | State & History | State/provenance owner |

Tidak ada domain pada tabel ini yang dipindahkan authority-nya kepada NPC Behavior.

---

## 42. Knowledge Integrity Rules

1. NPC tidak omniscient.
2. NPC tidak otomatis mengetahui hidden state.
3. NPC tidak otomatis mengetahui Player Knowledge.
4. NPC belief dapat salah.
5. Rumor tidak otomatis menjadi fact.
6. NPC tidak memperoleh informasi tanpa valid source.
7. AI GM knowledge tidak boleh diperlakukan sebagai NPC knowledge.
8. Knowledge update harus memiliki basis yang dapat ditelusuri jika menjadi persistent state.

---

## 43. Agency Integrity Rules

1. NPC harus memiliki dasar untuk tindakan penting.
2. NPC tidak boleh bertindak hanya untuk memajukan plot.
3. NPC tidak boleh dibuat gagal hanya untuk menghukum Player.
4. NPC goal tidak menjamin outcome.
5. NPC personality tidak deterministic.
6. NPC faction membership tidak menentukan semua keputusan individu.
7. NPC political role tidak menggantikan Politics.
8. NPC economic intent tidak menggantikan Economy.
9. NPC movement intent tidak menggantikan Travel.
10. NPC combat intent tidak menggantikan Combat.
11. NPC behavior tidak menggantikan Creature Ecology.
12. NPC autonomy tidak berarti unlimited capability.
13. NPC action harus tunduk pada constraints.
14. NPC decision tidak boleh mengontrol Player Character.
15. NPC social intent tidak otomatis menghasilkan relationship, reputation, political, economic, atau other persistent State Change tanpa resolution dan authority yang sesuai.

---

## 44. State Integrity Rules

1. Persistent NPC State Change harus divalidasi.
2. State Change harus memiliki Origin dan Source yang sesuai.
3. History harus mencatat perubahan penting yang persistent.
4. Tidak boleh ada silent overwrite untuk perubahan persistent.
5. Starting State tidak boleh ditimpa retroaktif.
6. NPC Behavior tidak boleh mengubah State domain system lain tanpa melalui owner/resolution yang sesuai.
7. Unknown / Undefined tidak boleh diisi dengan asumsi.
8. Narrative bukan sumber State hanya karena disebutkan dalam response.
9. Persistence tidak boleh diklaim tanpa verification.

---

## 45. No Hidden Fallback

Jika NPC Behavior membutuhkan informasi atau mechanic yang belum ditetapkan:

```text
DEFINED
→ USE CANON

UNDEFINED
→ REMAIN UNKNOWN / UNDEFINED
```

AI GM tidak boleh mengubah kekosongan Canon menjadi angka default, formula improvisasi, atau aturan tersembunyi.

---

## 46. Future Extension Boundary

Future systems dapat memperluas domain yang sekarang hanya menjadi dependency atau context, misalnya:

- Reputation;
- Knowledge / Information;
- Events;
- Quests / Objectives;
- Social Customs;
- Religion / Belief;
- Law / Legal Procedures;
- Progression;
- Property / Settlement Management;
- Diplomacy;
- War;
- atau domain lain yang memenuhi criteria system creation.

Ketika system baru dibuat, NPC Behavior harus menggunakan canonical owner system tersebut tanpa menduplikasi authority-nya.

---

## 47. Dependencies

NPC Behavior & Agency v0.1 secara arsitektural bergantung pada context dari system berikut sesuai kebutuhan action:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
characters/CHARACTER_DATA_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
world/WORLD_FOUNDATION.md
world/GEOGRAPHY.md
world/CIVILIZATION.md
world/PEOPLES_RACES.md
world/POLITICS.md
world/SUPERNATURAL_MAGIC.md
world/ECONOMY.md
world/CREATURES_ECOLOGY.md
world/FACTIONS.md
systems/TIME_AND_CALENDAR.md
systems/HEALTH_AND_INJURY.md
systems/COMBAT.md
systems/TRAVEL_AND_MOVEMENT.md
systems/RELATIONSHIPS.md
```

Dependency aktual dapat dibatasi pada module yang relevan terhadap decision atau action tertentu. Dependency tidak berarti seluruh isi semua module harus selalu dimuat atau diubah.

---

## 48. Progressive Development

NPC Behavior v0.1 adalah fondasi architecture dan decision model, bukan NPC simulation engine numerik final.

Pengembangan lanjutan mengikuti:

```text
IDENTIFY NPC BEHAVIOR NEED
↓
CHECK CANONICAL OWNER
↓
CHECK NPC CONTEXT / DEPENDENCY
↓
VALIDATE KNOWLEDGE BOUNDARY
↓
DEFINE DECISION RULE IF NEEDED
↓
DEFINE QUANTITATIVE MECHANIC ONLY IF EXPLICITLY CANONIZED
↓
INTEGRATE RUNTIME
↓
INTEGRATE STATE / HISTORY
↓
AUDIT OVERLAP
↓
VERIFY REPOSITORY
```

---

## 49. Canon Boundary Summary

NPC Behavior & Agency v0.1 menetapkan bahwa NPC adalah aktor dunia yang dapat mengambil keputusan secara autonomous berdasarkan State, information, goals, motivations, priorities, context, capability, dan constraints yang valid.

Modul ini **tidak** menetapkan:

- universal personality system;
- universal NPC stat block;
- intelligence score;
- morality score;
- relationship score;
- reputation score;
- decision probability;
- utility formula;
- universal action frequency;
- universal simulation tick;
- universal NPC schedule;
- universal social score;
- universal economic behavior formula;
- universal political behavior formula;
- universal combat AI formula;
- universal creature behavior formula;
- atau quantitative NPC mechanic lain yang belum menjadi Canon.

Prinsip akhir:

```text
NPC AGENCY
+
VALID KNOWLEDGE
+
GOALS / MOTIVATIONS
+
CURRENT CONTEXT
+
REAL CONSTRAINTS
+
CANONICAL SYSTEM RESOLUTION
=
AUTONOMOUS NPC BEHAVIOR
```

NPC dapat memilih apa yang ingin dilakukan, tetapi dunia tetap menentukan apa yang benar-benar terjadi melalui Canon, State, system resolution, dan consequences yang valid.
