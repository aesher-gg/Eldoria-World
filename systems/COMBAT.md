# Eldoria World — Combat System v0.1

> **Module:** Combat  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Combat v0.1 menetapkan **canonical owner untuk resolusi konflik fisik dan konfrontasi** di Eldoria ketika suatu situasi memenuhi kondisi combat atau membutuhkan combat resolution.

Modul ini mengatur struktur, konteks, intent, action, positioning, resolution, outcome, disengagement, surrender, retreat, combat termination, dan integrasi dengan Time & Calendar, Health & Injury, Character, Creatures / Ecology, Supernatural / Magic, State & History, dan Runtime.

Combat v0.1 adalah **framework resolution**, bukan sistem angka final. Modul ini tidak menetapkan HP universal, damage formula, attack/defense formula, armor reduction, initiative formula, critical-hit percentage, dodge percentage, weapon damage table, level, tier, fixed action points, atau combat-round duration universal.

## 2. Canonical Ownership

Combat adalah canonical owner untuk **combat/conflict resolution**.

```text
PLAYER / NPC / CREATURE / WORLD INPUT
                ↓
          COMBAT VALIDATION
                ↓
          COMBAT RESOLUTION
                ↓
      COMBAT OUTCOME / CONSEQUENCE
          ↙               ↘
HEALTH & INJURY       OTHER SYSTEMS
          ↓               ↓
        STATE / HISTORY / TIME
```

Boundary utama:

- Combat menentukan hasil konfrontasi berdasarkan rules dan context yang tersedia.
- Health & Injury menentukan representasi dan lifecycle konsekuensi kesehatan.
- Time & Calendar menentukan temporal representation dan temporal resolution.
- Character Data Model tetap menjadi owner struktur Character.
- Creatures / Ecology tetap menjadi owner creature/ecological facts.
- Supernatural / Magic tetap menjadi owner mekanisme supernatural.
- State & History tetap menjadi owner persistence structure dan provenance.
- Runtime Turn Model tetap menjadi owner pipeline Turn.

Dependency tidak memberikan hak kepada Combat untuk mengambil alih domain system lain.

## 3. Core Principles

- Combat adalah simulasi, bukan jaminan kemenangan Player atau NPC.
- Player menentukan intent karakter, bukan hasil combat.
- Intent ≠ Action Result ≠ Consequence ≠ State Change.
- Validation menentukan apakah combat action dapat diproses; validation tidak menjamin keberhasilan.
- Hasil dapat berupa success, partial success, failure, blocked, delayed, interrupted, disengaged, surrendered, atau outcome lain yang sah.
- Tidak ada plot armor.
- Tidak ada arbitrary punishment.
- Combat tidak boleh menciptakan kemampuan, statistik, atau formula yang belum memiliki Canon.
- Kondisi aktual peserta menjadi baseline resolution.
- Injury tidak otomatis berarti angka damage.
- Tidak semua hostile encounter harus menjadi combat.
- Tidak semua combat harus berakhir dengan kematian.
- Retreat, escape, surrender, negotiation, disengagement, incapacitation, dan perubahan kondisi adalah outcome yang sah bila didukung context.
- Dunia dan pihak non-Player memiliki agency dan tidak bertindak hanya untuk memenuhi narasi Player.

Prinsip inti:

```text
COMBAT INTENT
      ↓
VALIDATION
      ↓
RESOLUTION
      ↓
OUTCOME
      ↓
CONSEQUENCES
      ↓
STATE / HISTORY / TIME
```

## 4. When Combat Exists

Tidak setiap konflik otomatis menjadi combat.

Situasi dapat tetap menjadi interaction, negotiation, chase, threat, dispute, accident, atau proses lain apabila kondisi belum membentuk combat resolution.

Combat context dapat terbentuk ketika terdapat:

- tindakan ofensif atau defensif yang saling berhadapan;
- ancaman fisik yang sedang berlangsung;
- upaya paksa untuk mengalahkan, menahan, atau melukai pihak lain;
- konfrontasi bersenjata atau tanpa senjata;
- creature encounter yang berkembang menjadi konflik fisik;
- supernatural conflict yang membutuhkan physical/combat resolution;
- atau kondisi lain yang menurut Canon dan context memerlukan Combat.

AI GM tidak boleh mengubah setiap ketegangan menjadi combat hanya untuk meningkatkan drama.

## 5. Combat State

Combat State adalah kondisi operasional suatu confrontation pada saat resolution.

Model konseptual:

```text
COMBAT STATE
├── Combat ID
├── Status
├── World Time
├── Location / Environment Context
├── Participants
├── Hostile / Allied / Neutral Relations (if known)
├── Current Positions / Spatial Context (if available)
├── Active Conditions / Effects
├── Relevant Equipment
├── Active Objectives / Intentions
├── Recent Actions / Outcomes
├── Escape / Surrender / Disengagement Conditions
├── State References
├── History References
└── Validation Status
```

Tidak semua field harus tersedia. Field yang belum diketahui tetap Unknown / Undefined.

Combat State bukan pengganti Current State karakter atau world State.

## 6. Participants

Peserta combat dapat berupa:

- Character;
- NPC;
- creature;
- group atau unit jika Canon menyediakan model tersebut;
- supernatural actor/entity jika dapat berpartisipasi secara valid;
- atau pihak lain yang sah menurut Canon.

Setiap participant harus dapat diidentifikasi dan memiliki context yang cukup untuk resolution.

Model konseptual:

```text
COMBATANT
├── Participant ID
├── Subject Reference
├── Current State Reference
├── Intent / Objective
├── Position / Context
├── Relevant Abilities
├── Equipment / Objects
├── Active Conditions
├── Known Information
└── Combat Status
```

Combat tidak boleh memberikan kemampuan kepada participant hanya karena kemampuan tersebut berguna dalam encounter.

## 7. Combat Intent & Objectives

Intent menjelaskan apa yang ingin dicapai participant.

Contoh konseptual:

- menyerang;
- bertahan;
- melindungi;
- melumpuhkan;
- menahan;
- melucuti;
- melarikan diri;
- mengejar;
- memaksa mundur;
- mempertahankan posisi;
- mencapai target tertentu;
- mengakhiri confrontation.

Intent tidak menentukan hasil.

```text
INTENT
≠
TACTICAL OPPORTUNITY
≠
RESULT
```

Objective juga dapat berbeda antar participant. Combat tidak mengasumsikan semua pihak menginginkan kematian lawan.

## 8. Action Model

Combat action mengikuti struktur Runtime dan dapat diperluas oleh Combat.

```text
COMBAT ACTION
├── Action ID
├── Actor
├── Intent
├── Target (if any)
├── Action Type / Method
├── Context
├── Position
├── Relevant Equipment
├── Relevant Ability / Mechanism
└── Parameters
```

Contoh kategori action:

- attack;
- defend;
- evade;
- block;
- parry;
- grapple;
- restrain;
- disarm;
- reposition;
- retreat;
- pursue;
- protect;
- interact with environment;
- use relevant equipment;
- use valid supernatural ability;
- surrender;
- atau action lain yang dapat diproses oleh Canon.

Kategori tersebut adalah framework, bukan daftar kemampuan universal.

## 9. Validation

Sebelum combat action di-resolve, minimal periksa:

- participant valid dan masih berada dalam combat context;
- Current State valid;
- lokasi dan spatial context relevan;
- target valid jika action membutuhkan target;
- kemampuan yang digunakan benar-benar tersedia;
- equipment atau object benar-benar tersedia dan dapat digunakan;
- kondisi kesehatan atau kondisi lain yang relevan;
- environmental constraints;
- supernatural constraints bila ada;
- relationship/hostility context bila relevan;
- action tidak melanggar Canon.

Validation tidak menjawab siapa yang menang.

Validation hanya menentukan apakah action dapat diproses secara sah.

Jika input penting tidak tersedia, action tidak boleh diselesaikan dengan fabricated mechanic.

## 10. Position, Distance & Context

Combat resolution dapat dipengaruhi oleh posisi dan konteks ruang.

Informasi yang relevan dapat mencakup:

- posisi relatif;
- jarak;
- cover atau obstruction;
- terrain;
- elevation;
- visibility;
- footing;
- available space;
- environmental hazards;
- escape routes;
- nearby objects;
- crowding atau pihak lain;
- kondisi waktu/lingkungan jika relevan.

Tidak ada universal distance band, movement speed, range formula, atau positioning grid pada v0.1.

Jika detail spasial tidak diketahui, tetap Unknown / Undefined sampai terdapat basis yang sah.

## 11. Initiative & Ordering

Combat dapat membutuhkan ordering ketika beberapa action berkompetisi secara temporal atau kausal.

Ordering harus berasal dari context dan mekanisme yang Canon sahkan.

V0.1 **tidak menetapkan**:

- initiative score universal;
- initiative formula;
- fixed combat round;
- fixed turn order;
- action point system;
- reaction-point system;
- universal attack speed.

Jika urutan tidak dapat ditentukan secara sah, AI GM tidak boleh memilih urutan hanya demi memudahkan narasi.

Time & Calendar tetap menjadi authority untuk temporal ordering ketika temporal data diperlukan.

## 12. Resolution Model

Combat resolution menentukan hasil action berdasarkan:

```text
CURRENT STATE
+
COMBAT CONTEXT
+
PARTICIPANT CAPABILITIES
+
ACTION
+
POSITION / ENVIRONMENT
+
RELEVANT CANON
+
VALID SYSTEM MECHANICS
↓
COMBAT RESULT
```

Resolution dapat menghasilkan:

- hit / successful contact;
- miss / unsuccessful contact;
- partial outcome;
- blocked;
- evaded;
- interrupted;
- countered;
- restrained;
- disarmed;
- forced reposition;
- retreat/escape;
- surrender;
- incapacitation;
- death;
- atau outcome lain yang valid.

Istilah seperti hit atau miss tidak otomatis menentukan injury. Health consequence harus diproses melalui Health & Injury.

## 13. Attack & Defense

Combat dapat merepresentasikan hubungan antara offensive dan defensive action.

Secara konseptual:

```text
OFFENSIVE ACTION
        ↕
DEFENSIVE / REACTIVE ACTION
        ↓
RESOLUTION
```

Resolution mempertimbangkan data yang benar-benar tersedia.

V0.1 tidak menetapkan:

- Attack = Attribute × X;
- Defense = Attribute × X;
- damage = Attack − Defense;
- dodge percentage;
- critical-hit percentage;
- universal accuracy;
- universal armor reduction.

Attribute atau ability hanya digunakan apabila Character/system Canon telah mendefinisikannya dan aturan penggunaannya tersedia.

## 14. Maneuver & Tactical Interaction

Maneuver adalah tindakan yang mengubah posisi, control, access, leverage, atau kondisi confrontation tanpa harus menjadi direct damage.

Contoh konseptual:

- mengambil posisi lebih aman;
- menjatuhkan atau mendorong;
- mengunci anggota tubuh;
- merebut senjata;
- memutus line of sight;
- memaksa lawan keluar dari posisi;
- menggunakan terrain;
- melindungi pihak lain.

Keberhasilan maneuver ditentukan oleh resolution, bukan oleh pernyataan Player.

Tidak ada universal maneuver success formula pada v0.1.

## 15. Equipment & Object Interaction

Equipment dapat memengaruhi combat apabila item tersebut memang tersedia dan memiliki properties yang relevan.

Character Data Model tetap menjadi owner struktur equipment/possession karakter.

Combat tidak menciptakan item stat secara otomatis.

Jika equipment system kelak dibuat, Combat menggunakan definisi item tersebut sebagai dependency.

Contoh interaksi konseptual:

```text
EQUIPMENT DATA
↓
COMBAT CONTEXT
↓
COMBAT RESOLUTION
```

Tidak ada universal weapon damage, armor value, durability formula, atau item tier pada v0.1.

## 16. Environment Interaction

Lingkungan dapat memengaruhi combat melalui kondisi yang benar-benar ada.

Contoh konseptual:

- terrain sulit;
- ruang sempit;
- permukaan licin;
- ketinggian;
- api atau hazard;
- air;
- visibility;
- obstruction;
- struktur yang dapat digunakan atau rusak.

Geography dan world/environment Canon menyediakan konteks tempat. Combat menentukan bagaimana konteks tersebut relevan terhadap resolution jika mekanismenya dapat diproses.

Combat tidak boleh menciptakan environmental hazard tanpa dasar.

## 17. Supernatural / Magic Interaction

Supernatural atau magic dapat menjadi bagian dari combat apabila participant memiliki kemampuan atau mekanisme yang sah.

```text
MAGIC / SUPERNATURAL RESOLUTION
            ↓
   COMBAT-RELEVANT OUTCOME
            ↓
     COMBAT CONSEQUENCE
```

Supernatural / Magic tetap menjadi canonical owner atas mekanisme magic, access, limits, costs, dan effects.

Combat tidak menciptakan spell, mana, magical damage, resistance, atau countermeasure universal.

Jika magic resolution menghasilkan health consequence, consequence tersebut diteruskan ke Health & Injury.

## 18. Creature Interaction

Creature combat menggunakan data creature yang relevan dari Creatures / Ecology.

Pertimbangkan jika tersedia:

- classification;
- biology;
- behavior;
- habitat;
- current condition;
- territory;
- relevant abilities;
- ecological context.

Combat tidak boleh mengasumsikan semua creature agresif, cerdas, humanoid, tameable, atau memiliki kemampuan tertentu.

Creature/Ecology tetap menjadi owner fakta creature dan ecological context.

## 19. Health Consequences

Combat dapat menghasilkan konsekuensi kesehatan, tetapi **Health & Injury adalah canonical owner health-state representation**.

```text
COMBAT RESULT
↓
VALIDATED HEALTH CONSEQUENCE
↓
HEALTH & INJURY RESOLUTION
↓
HEALTH / INJURY STATE
```

Combat tidak boleh:

- membuat HP universal;
- mengubah hit menjadi damage number tanpa Canon;
- menetapkan healing rate;
- menetapkan severity scale universal;
- menetapkan death threshold universal.

Combat harus menyampaikan consequence yang memang dihasilkan resolution ke Health & Injury untuk representasi health yang sah.

## 20. Incapacitation

Participant dapat kehilangan kemampuan melakukan action tertentu ketika resolution menghasilkan kondisi yang sah.

Incapacitation harus dibedakan dari:

- temporary disadvantage;
- inability to perform one action;
- unconsciousness;
- surrender;
- retreat;
- death;
- atau condition lain yang memiliki definisi berbeda.

Definisi kesehatan dan functional impact tetap berada pada Health & Injury.

V0.1 tidak menetapkan universal threshold untuk incapacitation.

## 21. Death & Irreversible Outcomes

Combat dapat menghasilkan death atau irreversible outcome apabila resolution dan kondisi mendukungnya.

Death harus melalui:

```text
COMBAT RESOLUTION
↓
VALIDATED OUTCOME
↓
HEALTH & INJURY
↓
STATE CHANGE
↓
HISTORY
↓
PERSISTENCE / VERIFY
```

Combat tidak boleh membunuh participant hanya karena combat berlangsung atau karena narrative membutuhkan ending dramatis.

Health & Injury menentukan representasi health outcome; Combat menentukan bahwa combat resolution menghasilkan consequence tersebut.

Tidak ada resurrection rule universal dalam Combat v0.1.

## 22. Retreat, Escape & Pursuit

Retreat atau escape adalah combat outcome yang sah jika participant memiliki kesempatan, intent, dan kondisi yang memungkinkan.

Resolution dapat dipengaruhi oleh:

- posisi;
- akses keluar;
- kondisi fisik;
- kemampuan participant;
- tindakan lawan;
- lingkungan;
- pengetahuan;
- dan mekanisme Canon lain yang relevan.

Tidak ada universal escape percentage atau movement formula.

Pursuit adalah proses terpisah yang dapat berlanjut setelah disengagement jika context masih mendukung combat/chase resolution.

## 23. Surrender & Capture

Participant dapat menyerah atau mencoba menyerah.

```text
SURRENDER INTENT
↓
OTHER PARTY RESPONSE / RESOLUTION
↓
COMBAT STATUS CHANGE
```

Surrender intent tidak memaksa pihak lain menerima.

Capture juga bukan automatic consequence. Kondisi dan resolution harus mendukungnya.

Status hukum, tahanan, perlakuan terhadap tawanan, atau konsekuensi politik berada pada system Canon terkait apabila relevan.

## 24. Disengagement & Combat End

Combat dapat berakhir ketika kondisi termination terpenuhi.

Contoh konseptual:

- objective tercapai;
- semua pihak keluar dari engagement;
- pihak menyerah dan diterima;
- participant tidak lagi mampu melanjutkan;
- lawan melarikan diri dan engagement berakhir;
- ancaman hilang;
- pihak mencapai kondisi lain yang secara valid mengakhiri combat.

Combat end harus merupakan hasil state/resolution, bukan asumsi naratif.

Combat dapat berubah menjadi interaction lain setelah berakhir.

## 25. Sequential Combat Actions

Jika satu Player Message mengandung beberapa combat actions, action yang saling bergantung diproses berurutan sesuai Runtime Turn Model.

```text
COMBAT STATE T0
↓
ACTION A
↓
RESULT A
↓
WORKING COMBAT STATE
↓
ACTION B
↓
RESULT B
↓
FINAL VALIDATION
```

Action B harus menggunakan hasil A yang benar-benar berlaku.

Jika A menyebabkan incapacitation, surrender, death, disengagement, atau perubahan lain yang menghentikan B, B tidak otomatis dijalankan.

## 26. Time Integration

Combat menggunakan `systems/TIME_AND_CALENDAR.md` sebagai canonical temporal authority.

Combat v0.1 tidak menetapkan durasi universal untuk:

- combat round;
- attack;
- defense;
- movement;
- reaction;
- recovery between actions.

Jika suatu combat process menghasilkan elapsed time, duration harus berasal dari resolution atau system yang memiliki authority untuk menentukannya.

```text
COMBAT PROCESS
↓
VALIDATED TEMPORAL RESULT
↓
TIME & CALENDAR
↓
NEW TEMPORAL STATE
```

Combat tidak boleh mengarang waktu hanya untuk memberi timestamp.

## 27. State & History Integration

Combat yang menghasilkan perubahan persisten harus mengikuti State & History Model.

Combat record konseptual:

```text
COMBAT RECORD
├── Combat ID
├── World Time
├── Participants
├── Context
├── Actions / Action References
├── Resolution(s)
├── Consequences
├── State Changes
├── Outcome / End Status
├── Origin / Source
└── History Reference
```

State Change tetap menggunakan struktur canonical State & History.

History harus dapat menjelaskan perubahan penting yang dihasilkan combat.

Narrative combat bukan pengganti combat record atau persistence.

## 28. Runtime Integration

Combat adalah system-specific resolution yang dipanggil oleh Runtime.

```text
BOOT / LOAD CONTEXT
↓
READ CURRENT STATE
↓
PARSE PLAYER MESSAGE
↓
IDENTIFY COMBAT ACTION / INTENT
↓
VALIDATE
↓
COMBAT RESOLUTION
↓
CONSEQUENCES
├── HEALTH / INJURY
├── POSITION / COMBAT STATUS
├── EQUIPMENT / POSSESSION
├── TIME
└── OTHER VALID SYSTEM EFFECTS
↓
STATE CHANGE VALIDATION
↓
APPLY
↓
HISTORY
↓
PERSIST
↓
VERIFY
↓
RESPONSE
```

Jika combat memerlukan system yang belum dibuat, AI GM tidak boleh mengisi kekosongan tersebut dengan formula buatan sendiri.

## 29. Autonomous Combat

Combat dapat terjadi tanpa Player input ketika NPC, creature, faction, event, atau world process memiliki dasar yang sah untuk berkonflik.

Namun autonomous combat harus memiliki:

- participant yang valid;
- context yang valid;
- cause atau trigger yang dapat ditelusuri;
- resolution yang sah;
- consequences;
- State/History integration bila persisten.

AI GM tidak boleh menciptakan combat autonomous hanya untuk memaksa Player masuk ke plot tertentu.

## 30. Knowledge Boundary

Combat resolution harus membedakan:

```text
COMBAT CANON / SIMULATION DATA
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
```

Character tidak otomatis mengetahui:

- hidden ability lawan;
- exact condition lawan;
- unseen position;
- hidden tactical intention;
- true creature weakness;
- atau data simulation lain yang belum dapat diketahui secara sah.

Player Knowledge tidak boleh digunakan sebagai Character Knowledge tanpa mekanisme informasi yang valid.

## 31. Combat Information & Uncertainty

Combat resolution dapat memiliki informasi yang tidak lengkap.

Unknown dapat mencakup:

- kemampuan lawan yang belum terlihat;
- exact position yang tidak teramati;
- kondisi tersembunyi;
- intent pihak lain;
- outcome yang belum di-resolve.

Unknown tidak boleh diubah menjadi certainty hanya untuk membuat combat lebih mudah disimulasikan.

## 32. Combat Data Model

```text
COMBAT ENTITY
├── Combat ID
├── Status
├── World Time Reference
├── Location / Environment Reference
├── Participants
├── Combat Objectives
├── Current Positions / Context
├── Active Conditions
├── Relevant Equipment References
├── Action / Resolution Records
├── Consequences
├── Outcome
├── State Change References
├── History Reference
└── Metadata
```

### Combat Action Record

```text
COMBAT ACTION
├── Action ID
├── Combat ID
├── Actor
├── Intent
├── Target
├── Method / Type
├── Context
├── Relevant Inputs
├── Validation Result
├── Resolution Result
├── Consequences
├── State Change References
├── World Time
└── Source / Origin
```

### Combatant State

```text
COMBATANT STATE
├── Participant Reference
├── Current Condition
├── Position / Context
├── Active Conditions
├── Relevant Equipment
├── Available Abilities
├── Objective / Intent
├── Combat Status
└── Validation Status
```

Field yang belum ditetapkan tetap Unknown / Undefined.

## 33. Dependencies & Canon Ownership Audit

Combat bergantung pada:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
characters/CHARACTER_DATA_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
systems/TIME_AND_CALENDAR.md
systems/HEALTH_AND_INJURY.md
world/CREATURES_ECOLOGY.md
world/SUPERNATURAL_MAGIC.md
world/GEOGRAPHY.md
world/FACTIONS.md
world/POLITICS.md
world/ECONOMY.md
```

Kebutuhan dependency tidak berarti semua modul harus dimuat penuh pada setiap combat. Runtime mengambil Canon/Data yang relevan terhadap encounter.

### Ownership Matrix

| Domain | Canonical Owner | Combat Boundary |
|---|---|---|
| Runtime Turn | `core/RUNTIME_TURN_MODEL.md` | Mengikuti pipeline |
| Character structure | `characters/CHARACTER_DATA_MODEL.md` | Mengonsumsi data karakter |
| Temporal representation | `systems/TIME_AND_CALENDAR.md` | Menggunakan time authority |
| Health / injury state | `systems/HEALTH_AND_INJURY.md` | Mengirim health consequences |
| Creature facts/ecology | `world/CREATURES_ECOLOGY.md` | Menggunakan creature context |
| Supernatural / magic rules | `world/SUPERNATURAL_MAGIC.md` | Menggunakan valid magic mechanisms |
| Geography/environment | `world/GEOGRAPHY.md` | Menggunakan spatial context |
| Faction facts | `world/FACTIONS.md` | Menggunakan faction context bila relevan |
| Political/legal consequences | `world/POLITICS.md` | Menyerahkan domain consequences terkait |
| Economic consequences | `world/ECONOMY.md` | Menyerahkan domain consequences terkait |
| State structure | `state/STATE_AND_HISTORY_MODEL.md` | Menghasilkan validated State Changes |
| Combat resolution | **`systems/COMBAT.md`** | **Canonical owner** |

Tidak ada overlap yang memberi Combat authority atas domain di luar combat resolution.

## 34. Explicitly Undefined in v0.1

Combat v0.1 sengaja **tidak menetapkan**:

- universal attributes;
- universal combat stats;
- HP;
- stamina formula;
- attack formula;
- defense formula;
- damage formula;
- armor mitigation formula;
- weapon damage table;
- armor stat table;
- initiative formula;
- dodge/parry percentage;
- critical-hit percentage;
- hit probability formula;
- universal range bands;
- movement speed;
- action point system;
- fixed combat rounds;
- fixed combat-round duration;
- level/tier/rank;
- universal status-effect numbers;
- universal death threshold;
- universal surrender threshold;
- universal escape probability;
- universal morale formula;
- universal group/unit combat formula;
- universal loot rules.

Semua mekanik tersebut hanya boleh ditambahkan melalui Canon eksplisit dan dengan canonical ownership yang jelas.

## 35. Integrity Rules

- Combat tidak boleh menganggap intent sebagai result.
- Combat action harus divalidasi sebelum resolution.
- Validation tidak menjamin keberhasilan.
- Current State adalah baseline combat.
- Sequential action menggunakan Working State yang benar-benar dihasilkan resolution sebelumnya.
- Action yang sudah tidak valid karena hasil sebelumnya tidak boleh tetap dipaksakan.
- Combat tidak boleh menciptakan stat atau formula yang belum didefinisikan.
- Health consequences harus mengikuti Health & Injury.
- Temporal resolution harus mengikuti Time & Calendar.
- Creature facts harus mengikuti Creatures / Ecology.
- Magic facts/mechanics harus mengikuti Supernatural / Magic.
- Equipment facts harus berasal dari Canon item/equipment yang relevan ketika tersedia.
- Environment facts harus memiliki basis Geography/world State yang valid.
- State Changes harus mengikuti State & History Model.
- History penting harus dapat ditelusuri ke combat action/resolution.
- Autonomous combat harus memiliki dasar yang valid.
- Character Knowledge tidak boleh disamakan dengan Player Knowledge.
- Unknown / Undefined tidak boleh diisi dengan asumsi.
- Combat end harus berasal dari valid outcome/state, bukan narrative convenience.
- Death tidak boleh dipaksakan tanpa valid resolution dan health consequence.
- Narrative bukan sumber State atau persistence.
- AI GM tidak boleh mengklaim persistence berhasil tanpa verification.

## 36. Progressive Development

Combat dapat dikembangkan bertahap tanpa merusak boundary v0.1:

```text
COMBAT FRAMEWORK
↓
SPECIFIC RESOLUTION MECHANICS
↓
ATTRIBUTES / ABILITIES INTEGRATION
↓
WEAPONS / ARMOR / EQUIPMENT SYSTEM
↓
TACTICAL / POSITIONING RULES
↓
GROUP / UNIT COMBAT (if needed)
↓
SPECIFIC COMBAT CONTEXTS
↓
BALANCING / VALIDATION / TESTING
```

Setiap ekstensi harus memiliki ownership, dependencies, formula, data model, State/History integration, dan validation yang eksplisit.

## 37. Canon Boundary

Combat v0.1 adalah framework canonical resolution untuk konflik. Modul ini tidak boleh digunakan untuk menyelundupkan lore, race, creature, weapon, armor, magic, faction, kingdom, atau angka statistik yang belum ditetapkan oleh Canon terkait.

Jika suatu detail combat membutuhkan system yang belum tersedia:

```text
REQUIRED SYSTEM MISSING
        ↓
UNKNOWN / UNDEFINED
        ↓
NO FABRICATED MECHANIC
```

Perubahan atau pengecualian terhadap boundary ini harus menjadi perubahan Canon eksplisit melalui Repository.
