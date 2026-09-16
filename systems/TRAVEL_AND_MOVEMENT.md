# Eldoria World — Travel & Movement System v0.1

> **Module:** Travel & Movement  
> **Version:** v0.1  
> **System ID:** SYSTEM-04-TRAVEL-MOVEMENT  
> **Authority:** Official Canon / World System

## 1. Purpose

Travel & Movement v0.1 menetapkan **canonical owner untuk proses perpindahan actor melalui ruang dan wilayah** dalam simulasi Eldoria.

Modul ini menjadi fondasi untuk perjalanan Character, NPC, creature, kelompok, atau actor lain ketika perpindahan tersebut perlu divalidasi, di-resolve, menghasilkan elapsed time, atau menghasilkan perubahan lokasi yang relevan terhadap State.

Modul ini adalah framework resolution dan state integration. Modul ini tidak menetapkan kecepatan perjalanan universal, durasi perjalanan universal, stamina formula, encounter formula, mount speed, atau mekanik numerik lain tanpa Canon eksplisit.

## 2. Canonical Ownership

Travel & Movement adalah canonical owner untuk **travel/movement process dan resolusi perpindahan**.

```text
TRAVEL / MOVEMENT INPUT
        ↓
TRAVEL VALIDATION
        ↓
TRAVEL RESOLUTION
        ↓
MOVEMENT / TRAVEL OUTCOME
        ↓
TIME / HEALTH / ECONOMY / OTHER CONSEQUENCES
        ↓
STATE / HISTORY
```

Boundary utama:

- **Geography** = fakta dan struktur spasial dunia, terrain, connectivity, dan kondisi geografis yang telah ditetapkan.
- **Travel & Movement** = proses perpindahan actor dan resolusi perjalanan.
- **Time & Calendar** = canonical authority untuk representasi dan resolusi temporal.
- **Health & Injury** = canonical authority untuk konsekuensi kesehatan.
- **Economy** = canonical authority untuk biaya, transaksi, kepemilikan, dan konsekuensi ekonomi.
- **Creatures / Ecology** = canonical authority untuk creature, habitat, population, dan ecological facts.
- **Combat** = canonical authority untuk combat/conflict resolution jika perjalanan berkembang menjadi combat.
- **Character Data Model** = canonical owner struktur Character.
- **State & History** = canonical owner state representation, provenance, dan persistence structure.
- **Runtime Turn Model** = canonical owner pipeline Turn.

Dependency tidak memberikan hak kepada Travel & Movement untuk mengambil alih domain system lain.

## 3. Core Principles

- Perjalanan adalah proses dunia, bukan sekadar transisi narrative.
- Perpindahan tidak terjadi hanya karena Player menyatakan tujuan.
- Intent ≠ route ≠ movement process ≠ result ≠ State Change.
- Actor harus memiliki konteks yang cukup untuk melakukan movement resolution.
- Kondisi aktual actor, route, environment, dan tujuan menjadi baseline resolution.
- Perjalanan dapat berhasil, sebagian berhasil, gagal, tertunda, terinterupsi, dialihkan, atau menghasilkan outcome lain yang sah.
- Tidak ada plot armor terhadap bahaya perjalanan.
- Tidak ada arbitrary hazard hanya untuk menghukum Player.
- Dunia tidak men-spawn encounter secara arbitrer hanya karena actor sedang melakukan perjalanan.
- Waktu perjalanan harus berasal dari resolution yang valid dan diteruskan kepada Time & Calendar.
- Perubahan lokasi persisten harus menjadi State Change yang tervalidasi.
- Detail yang belum ditetapkan tetap Unknown / Undefined.
- Travel & Movement tidak boleh menciptakan formula atau angka default sebagai fallback Canon.

## 4. When Travel / Movement Exists

Tidak setiap perubahan posisi harus diperlakukan sebagai travel process penuh.

Movement dapat berupa perpindahan lokal, sedangkan travel biasanya mencakup perpindahan melalui route atau jarak yang membutuhkan proses lebih lanjut.

Contoh konseptual:

```text
POSITION CHANGE
├── Local Movement
├── Route Travel
├── Crossing / Passage
├── Pursuit / Escape Movement
├── Group Travel
├── Transport-assisted Travel
└── Other Valid Movement Process
```

Kategori tersebut adalah framework, bukan daftar mekanik universal.

Jika suatu perubahan posisi sudah terjadi sebagai bagian dari resolution system lain dan tidak membutuhkan Travel resolution tersendiri, Travel & Movement tidak boleh menduplikasi proses tersebut.

## 5. Travel State

Travel State adalah kondisi operasional suatu proses perjalanan yang sedang berlangsung.

Model konseptual:

```text
TRAVEL STATE
├── Travel ID
├── Status
├── Actor(s)
├── Origin
├── Destination
├── Current Location / Position
├── Route / Path Reference (if known)
├── Travel Method (if defined)
├── Environment / Terrain Context
├── Current Conditions
├── Temporal Context
├── Travel Objective
├── Relevant Constraints
├── Current Progress / Position Reference (if defined)
├── State References
├── History References
└── Validation Status
```

Tidak semua field harus tersedia. Field yang belum diketahui tetap Unknown / Undefined.

Travel State bukan pengganti Current State Character atau World State.

## 6. Actor & Movement Context

Actor yang dapat melakukan movement dapat berupa:

- Character;
- NPC;
- creature;
- group atau unit jika Canon menyediakan model tersebut;
- vehicle atau transport entity jika Canon menyediakan model tersebut;
- actor lain yang sah menurut Canon.

Sebelum resolution, runtime harus memiliki konteks yang relevan, seperti:

- actor identity;
- current location atau position;
- destination atau movement objective;
- kondisi actor;
- route/path information jika tersedia;
- terrain/environment;
- movement method jika relevan;
- restrictions atau obstacles yang diketahui;
- temporal context;
- resources atau biaya jika sistem relevan membutuhkannya.

Travel tidak boleh memberikan kemampuan movement kepada actor hanya karena actor membutuhkannya untuk narrative.

## 7. Movement Intent

Player atau actor dapat memiliki intent seperti:

- bergerak menuju lokasi tertentu;
- mengikuti route;
- mencari route;
- berpindah secara lokal;
- mengejar actor lain;
- melarikan diri;
- mengawal actor;
- menghindari area tertentu;
- mencapai tujuan sebelum kondisi tertentu berubah;
- atau tujuan movement lain yang valid.

Intent tidak menentukan keberhasilan.

```text
MOVEMENT INTENT
≠
AVAILABLE ROUTE
≠
TRAVEL RESULT
≠
LOCATION STATE
```

Destination yang disebut Player juga tidak otomatis berarti destination tersebut dapat dicapai, diketahui karakter, atau tersedia secara geografis.

## 8. Origin & Destination Validation

Sebelum travel resolution, minimal periksa:

- actor valid;
- current location/position diketahui atau cukup untuk resolution;
- destination valid jika action membutuhkannya;
- actor memiliki akses yang relevan terhadap destination atau route;
- route atau path yang digunakan benar-benar ada jika route tertentu disebut;
- movement tidak melanggar kondisi atau constraint Canon;
- informasi yang digunakan sesuai Knowledge Boundary;
- movement method tersedia jika diperlukan;
- kondisi actor memungkinkan proses tersebut sejauh dapat ditentukan.

Jika destination atau route belum ditetapkan oleh Canon, statusnya tetap Unknown / Undefined atau resolution harus berhenti pada batas informasi yang tersedia.

## 9. Geography Dependency

Geography menyediakan konteks spasial yang digunakan Travel & Movement.

Travel dapat menggunakan data seperti:

- geographic hierarchy;
- adjacency;
- distance jika didefinisikan;
- terrain;
- natural barriers;
- water systems;
- route/connectivity;
- settlements/sites;
- environment;
- infrastructure yang telah ditetapkan.

```text
GEOGRAPHY
= spatial facts / structure

TRAVEL & MOVEMENT
= movement process / resolution
```

Travel tidak boleh mengarang jalan, jembatan, pelabuhan, shortcut, jarak, atau hubungan spasial yang belum memiliki basis Canon.

Geographic proximity juga tidak otomatis berarti route tersedia.

## 10. Route & Path

Route adalah jalur atau rangkaian konektivitas yang digunakan actor untuk bergerak.

Model konseptual:

```text
ORIGIN
↓
ROUTE / PATH
├── Segment A
├── Segment B
├── Segment C
└── DESTINATION
```

Route dapat berasal dari:

- Canon Geography;
- in-world infrastructure;
- informasi Character;
- route yang ditemukan melalui resolution;
- atau sumber valid lain.

Route yang hanya berupa rumor atau dugaan tidak boleh diperlakukan sebagai route Canon yang pasti.

Jika beberapa route tersedia, Travel resolution dapat membandingkan route berdasarkan faktor yang memang diketahui dan memiliki aturan yang sah.

V0.1 tidak menetapkan universal pathfinding formula.

## 11. Terrain, Environment & Obstacles

Kondisi ruang dapat memengaruhi travel apabila kondisi tersebut benar-benar ada dan resolution system dapat memprosesnya.

Faktor konseptual dapat mencakup:

- terrain;
- elevation;
- vegetation;
- water crossing;
- natural barriers;
- road quality;
- infrastructure;
- weather/environment;
- visibility;
- hazards;
- obstruction;
- route condition;
- security conditions.

Travel tidak boleh menciptakan obstacle hanya untuk memperpanjang perjalanan.

Geography menyediakan fakta spasial; environment dan world systems lain menyediakan kondisi yang relevan sesuai authority masing-masing.

## 12. Travel Method & Transport

Perjalanan dapat menggunakan:

- berjalan kaki;
- hewan tunggangan;
- kendaraan;
- kapal;
- sarana transportasi lain;
- atau metode supernatural jika Canon menyediakan mekanismenya.

Travel Method hanya dapat digunakan apabila actor benar-benar memiliki akses terhadap sarana tersebut dan Canon yang relevan mendukungnya.

Travel & Movement tidak menetapkan universal:

- walking speed;
- mount speed;
- vehicle speed;
- ship speed;
- carrying capacity;
- acceleration;
- fuel consumption;
- teleportation rules;
- fast-travel rules.

Detail tersebut menjadi Canon tersendiri apabila kelak diperlukan.

## 13. Travel Duration & Time Integration

Time & Calendar adalah canonical temporal authority.

Travel & Movement menentukan atau menggunakan elapsed duration hanya jika proses perjalanan memiliki basis resolution yang sah.

```text
TRAVEL PROCESS
↓
VALIDATED TRAVEL OUTCOME
↓
VALIDATED ELAPSED DURATION
↓
TIME & CALENDAR
↓
NEW TEMPORAL CONTEXT
```

Travel tidak boleh mengarang durasi hanya agar perjalanan selesai dalam satu Turn.

Jika durasi tidak dapat ditentukan secara sah, travel process dapat tetap berada pada status pending/ongoing/undefined sesuai context tanpa memalsukan World Time.

Tidak ada durasi universal untuk perjalanan pada v0.1.

## 14. Turn Integration

Satu Player Message tetap satu Runtime Turn.

Satu Turn dapat mengandung action movement/travel, tetapi Turn tidak otomatis sama dengan satu segmen perjalanan atau satu unit jarak tertentu.

```text
ONE TURN
≠
ONE TRAVEL SEGMENT
≠
FIXED TRAVEL DISTANCE
```

Jika satu Turn berisi beberapa movement action yang saling bergantung, masing-masing diproses berurutan dan menggunakan Working State serta temporal context hasil action sebelumnya.

## 15. Progression During Travel

Perjalanan dapat bersifat:

- completed;
- ongoing;
- paused;
- delayed;
- interrupted;
- diverted;
- failed;
- atau status lain yang sah.

Progress tidak harus direpresentasikan sebagai persentase atau angka.

Jika progress kuantitatif diperlukan di masa depan, model tersebut harus ditetapkan secara eksplisit sebagai Canon.

Perjalanan yang sedang berlangsung dapat memiliki Current Location yang berbeda dari Destination.

```text
ORIGIN
↓
CURRENT POSITION
↓
ONGOING TRAVEL
↓
DESTINATION
```

## 16. Group Travel

Beberapa actor dapat melakukan perjalanan bersama jika mereka memiliki hubungan dan kondisi yang memungkinkan.

Group travel dapat menghadapi:

- perbedaan movement capability;
- kondisi kesehatan;
- tujuan yang berbeda;
- resources berbeda;
- route constraints;
- keputusan anggota;
- pemisahan atau perubahan komposisi group.

Travel tidak boleh menganggap seluruh group bergerak sebagai satu entitas tanpa basis.

Jika satu anggota tertinggal, berhenti, cedera, atau berpisah, perubahan tersebut harus di-resolve secara valid dan dapat menghasilkan State Change terpisah.

## 17. Pursuit & Escape

Travel & Movement dapat menangani perpindahan yang memiliki hubungan kejar-mengejar atau pelarian selama situasi belum menjadi combat resolution.

```text
PURSUER
↓
MOVEMENT / TRAVEL RESOLUTION
↕
EVADER
↓
RELATIVE POSITION / OUTCOME
```

Jika konfrontasi berkembang menjadi Combat, Combat menjadi canonical owner untuk combat resolution.

Travel tidak menetapkan universal chase speed, escape threshold, atau pursuit formula.

## 18. Encounter During Travel

Perjalanan dapat menghasilkan encounter dengan NPC, creature, environmental condition, event, atau actor lain apabila terdapat dasar dunia yang valid.

Encounter tidak boleh dibuat hanya karena:

```text
PLAYER IS TRAVELING
→ RANDOM ENCOUNTER MUST HAPPEN
```

Creatures / Ecology menyediakan dasar ecological encounter ketika relevan.

NPC/Faction/Event systems kelak menyediakan dasar encounter sosial atau dunia lainnya apabila sistem tersebut telah didefinisikan.

Jika encounter menghasilkan combat, resolution berpindah ke Combat.

Jika encounter menghasilkan health consequence, Health & Injury menjadi owner health-state consequence.

Encounter narrative sendiri tidak otomatis mengubah ecological population atau persistent world State.

## 19. Travel Hazards

Hazard dapat memengaruhi travel apabila:

- hazard benar-benar ada;
- actor dapat terpapar;
- context mendukung;
- resolution yang relevan tersedia.

Hazard dapat berasal dari:

- terrain;
- environment;
- weather;
- creature;
- infrastructure condition;
- political/security condition;
- health condition;
- supernatural effect;
- atau source valid lain.

Travel & Movement tidak memiliki daftar hazard universal dan tidak menciptakan hazard arbitrer.

## 20. Health & Injury Integration

Travel dapat menghasilkan health consequences melalui proses yang valid, misalnya exposure, accident, exertion, environmental hazard, atau kondisi lain jika mekanismenya telah ditetapkan.

```text
TRAVEL RESOLUTION
↓
VALIDATED HEALTH CONSEQUENCE
↓
HEALTH & INJURY
↓
HEALTH STATE
```

Health & Injury tetap menjadi owner atas:

- injury;
- wound;
- condition;
- symptom;
- functional impact;
- recovery;
- treatment;
- incapacitation;
- death/irreversible health outcomes.

Travel tidak menciptakan HP, damage, healing, exhaustion threshold, atau health formula universal.

## 21. Economy & Resource Integration

Perjalanan dapat memiliki konsekuensi ekonomi atau membutuhkan resources apabila Canon ekonomi atau konteks perjalanan mendukungnya.

Contoh konseptual:

- transport fee;
- toll;
- lodging;
- supplies;
- hired transport;
- route access cost;
- loss or consumption of resources;
- economic consequence of delay.

```text
TRAVEL PROCESS
↓
ECONOMIC INPUT / CONSEQUENCE
↓
ECONOMY RESOLUTION
↓
STATE / HISTORY
```

Economy tetap menjadi owner untuk transaction, price, value, ownership, income, cost, dan economic State.

Travel tidak menciptakan harga atau biaya universal.

## 22. Creatures & Ecology Integration

Perjalanan dapat berinteraksi dengan creature dan ecosystem ketika actor memasuki habitat atau area yang memiliki ecological context yang relevan.

Creatures / Ecology tetap menjadi owner untuk:

- creature identity;
- habitat;
- population;
- behavior;
- territory/range;
- ecological relationships;
- ecological events.

Travel hanya menggunakan data tersebut untuk movement/encounter context.

Travel tidak membuat creature spawn arbitrer atau mengubah population hanya karena Player melewati wilayah tertentu.

## 23. Combat Integration

Jika travel menghasilkan atau memasuki combat context, Combat menjadi canonical owner untuk combat resolution.

```text
TRAVEL
↓
CONFLICT / COMBAT CONTEXT
↓
COMBAT RESOLUTION
↓
CONSEQUENCES
↓
HEALTH / STATE / HISTORY / TIME
```

Travel tidak mengambil alih attack, defense, maneuver, initiative, combat outcome, surrender, atau death resolution yang menjadi bagian dari Combat.

Jika combat berakhir dengan retreat atau pursuit, Travel & Movement dapat kembali menjadi system yang relevan untuk perpindahan setelah combat resolution.

## 24. Supernatural / Magic Integration

Supernatural atau magic dapat memengaruhi movement apabila mekanismenya telah ditetapkan.

Contoh kategori konseptual:

- magical transportation;
- altered movement;
- movement restriction;
- environmental magical effect;
- supernatural route access.

Supernatural / Magic tetap menjadi owner untuk source, access, effect, limits, cost, dan risk dari mekanisme supernatural.

Travel hanya menyelesaikan movement consequence yang memang menjadi domainnya.

Tidak ada teleportation atau fast-travel rule universal dalam v0.1.

## 25. Political, Legal & Security Context

Travel dapat dipengaruhi oleh kondisi politik atau legal ketika route melewati jurisdiction, border, checkpoint, controlled infrastructure, conflict zone, atau kondisi keamanan yang telah ditetapkan.

Politics tetap menjadi owner untuk:

- authority;
- jurisdiction;
- sovereignty/control;
- law;
- border/political relations;
- political consequences.

Travel tidak menciptakan border, permit requirement, toll, law, atau restriction tanpa Canon yang relevan.

## 26. Knowledge Boundary

Travel resolution harus membedakan:

```text
GEOGRAPHY / TRAVEL CANON
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
≠
RUMOR / UNCERTAIN INFORMATION
```

Character tidak otomatis mengetahui route terbaik, jarak, obstacle, destination condition, creature habitat, security condition, atau shortcut hanya karena informasi tersebut diketahui Player atau AI GM.

Perjalanan dapat gagal karena Character memilih berdasarkan informasi yang salah atau tidak lengkap apabila resolution mendukungnya.

## 27. Autonomous Movement

NPC, creature, faction, transport, atau actor dunia lain dapat bergerak tanpa keputusan Player apabila proses autonomous tersebut memiliki basis yang sah.

```text
AUTONOMOUS MOVEMENT
↓
VALIDATE
↓
RESOLVE
↓
TIME / CONSEQUENCES
↓
STATE CHANGE
↓
HISTORY
```

Travel & Movement tidak memerintahkan seluruh dunia untuk bergerak secara otomatis tanpa process owner atau basis yang relevan.

## 28. State Integration

Perubahan movement yang menjadi persistent State mengikuti State & History Model.

Contoh:

```text
TRAVEL RESULT
↓
LOCATION / POSITION CHANGE
↓
VALIDATE STATE CHANGE
↓
APPLY
↓
HISTORY
↓
PERSIST
↓
VERIFY
```

Current Location dapat berubah apabila actor benar-benar berpindah berdasarkan resolution.

Destination tidak boleh ditulis sebagai Current Location sebelum actor benar-benar mencapainya.

Travel State yang ongoing dapat menjadi referensi untuk menjelaskan perpindahan yang belum selesai.

## 29. History & Provenance

Perubahan penting terkait perjalanan harus dapat ditelusuri.

Model konseptual:

```text
TRAVEL / MOVEMENT RESULT
├── Travel ID
├── Actor
├── Origin
├── Destination
├── Result
├── Relevant Conditions
├── Elapsed Time Reference
├── State Changes
├── Cause / Origin
├── Source
└── History Reference
```

History dapat mencatat keberangkatan, kedatangan, perubahan route, interruption, diversion, atau outcome penting lainnya apabila memiliki nilai continuity atau audit.

Narrative perjalanan bukan pengganti Travel State atau History.

## 30. Data Model

### Travel Entity

```text
TRAVEL ENTITY
├── Travel ID
├── Actor(s)
├── Origin
├── Destination
├── Current Location / Position
├── Route / Path Reference
├── Travel Method
├── Environment / Terrain Context
├── Travel Objective
├── Status
├── Temporal Context
├── Relevant Conditions
├── Consequences
├── Current State Reference
├── History Reference
└── Metadata
```

### Movement Action

```text
MOVEMENT ACTION
├── Action ID
├── Actor
├── Intent
├── Origin / Current Position
├── Destination / Target Position
├── Route Input (if any)
├── Movement Method (if any)
├── Context
└── Parameters
```

### Travel Resolution

```text
TRAVEL RESOLUTION
├── Travel / Action ID
├── Validation Result
├── Route Result
├── Movement Result
├── Elapsed Duration (if defined)
├── New Position / Location (if changed)
├── Encounter / Hazard Result (if any)
├── Consequences
├── State Changes
└── History Reference
```

Field yang belum didefinisikan tetap Unknown / Undefined.

## 31. Runtime / Resolution Pipeline

Travel action mengikuti Runtime Turn Model:

```text
PLAYER / NPC / CREATURE / WORLD INPUT
↓
PARSE
↓
IDENTIFY MOVEMENT / TRAVEL INTENT
↓
LOAD CURRENT STATE + RELEVANT CANON
↓
VALIDATE ORIGIN / DESTINATION / CONTEXT
↓
RESOLVE ROUTE / MOVEMENT
↓
DETERMINE VALID ELAPSED TIME
↓
RESOLVE RELEVANT CONSEQUENCES
↓
GENERATE STATE CHANGES
↓
VALIDATE STATE CHANGES
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

Urutan detail dapat berubah jika dependency tertentu membutuhkan resolution lebih dahulu, tetapi canonical ownership tetap harus dipertahankan.

## 32. Sequential Travel Actions

Jika satu Turn berisi beberapa movement action:

```text
CURRENT STATE T0
↓
MOVEMENT A
↓
RESULT A
↓
WORKING STATE
↓
MOVEMENT B
↓
RESULT B
↓
FINAL STATE VALIDATION
↓
PERSIST
```

Movement B harus menggunakan lokasi, kondisi, route context, dan temporal context hasil Movement A.

Jika Movement A gagal, tertunda, atau terinterupsi, Movement B tidak otomatis dijalankan seolah-olah Movement A berhasil.

## 33. Failure, Delay & Interruption

Travel dapat menghasilkan:

- success;
- partial success;
- failure;
- blocked;
- delayed;
- interrupted;
- diverted;
- forced stop;
- return;
- ongoing travel;
- atau outcome lain yang sah.

Failure tidak otomatis berarti tidak ada State Change. Misalnya, proses dapat tetap mengonsumsi waktu atau menghasilkan kondisi lain apabila resolution menetapkannya.

Sebaliknya, Travel tidak boleh menambahkan konsekuensi hanya karena narrative membutuhkan drama.

## 34. No Universal Numeric Mechanics

Travel & Movement v0.1 **secara eksplisit tidak menetapkan**:

```text
❌ universal movement speed
❌ km/hour universal
❌ travel speed = attribute × multiplier
❌ universal distance formula
❌ universal terrain multiplier
❌ universal stamina drain formula
❌ universal exhaustion threshold
❌ hunger / thirst formula
❌ random encounter percentage
❌ encounter table
❌ universal hazard probability
❌ universal mount speed
❌ universal vehicle speed
❌ universal ship speed
❌ universal carrying capacity
❌ universal travel cost
❌ universal route efficiency formula
❌ teleportation rules
❌ fast-travel rules
❌ universal chase formula
❌ universal escape threshold
❌ fixed travel duration per Turn
❌ fixed distance per Turn
```

Jika salah satu mekanik tersebut diperlukan, mekanik harus didefinisikan dan diintegrasikan secara eksplisit sebagai Canon yang relevan.

## 35. Canon Boundary

Travel & Movement v0.1 **tidak** menetapkan secara universal:

- daftar route;
- daftar jalan atau jalur;
- jarak antar lokasi;
- kecepatan actor;
- kecepatan transportasi;
- terrain multiplier;
- stamina/exhaustion system;
- hunger/thirst system;
- encounter table atau encounter rate;
- hazard probability;
- travel cost;
- mount/vehicle rules;
- teleportation/fast-travel rules;
- universal chase mechanics;
- universal route-finding formula;
- universal navigation skill;
- universal travel duration.

Detail tersebut hanya menjadi Canon setelah ditetapkan secara resmi oleh modul yang tepat.

## 36. Dependencies

Travel & Movement v0.1 bergantung pada:

```text
INDEX.md
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
```

Dependency aktual dapat dibatasi sesuai action yang sedang diproses. AI GM tidak diwajibkan memuat seluruh dependency pada setiap Turn apabila tidak relevan.

## 37. Ownership Audit

| Domain | Canonical Owner | Travel & Movement Role |
|---|---|---|
| Spatial facts / terrain / connectivity | Geography | Read / use |
| Travel / movement process | Travel & Movement | **Owner** |
| Temporal representation / time advancement | Time & Calendar | Read / submit temporal result |
| Health / injury state | Health & Injury | Produce health consequence input |
| Economic transaction / cost / value | Economy | Produce economic context/input |
| Creature / habitat / ecology | Creatures / Ecology | Read ecological context |
| Combat / conflict resolution | Combat | Hand off conflict resolution |
| Character structure | Character Data Model | Read / update through valid State Change |
| State / provenance / persistence structure | State & History | Follow / write through model |
| Runtime Turn pipeline | Runtime Turn Model | Follow |
| Supernatural mechanics | Supernatural / Magic | Read / hand off supernatural resolution |
| Political authority / law / jurisdiction | Politics | Read context |
| Faction identity / membership / internal relations | Factions | Read context |

Tidak ada domain di atas yang diambil alih oleh Travel & Movement.

## 38. Knowledge & Information Integrity

Travel resolution harus menjaga perbedaan antara:

```text
WHAT EXISTS IN CANON
vs.
WHAT THE CHARACTER KNOWS
vs.
WHAT THE PLAYER KNOWS
vs.
WHAT IS UNCERTAIN
```

AI GM tidak boleh menggunakan hidden route, hidden hazard, hidden creature location, atau hidden destination condition sebagai Character Knowledge tanpa basis yang sah.

Informasi yang salah dapat menghasilkan keputusan travel yang salah jika resolution mendukungnya.

## 39. Persistence Integrity

Perubahan lokasi atau Travel State yang dinyatakan sebagai persistent harus mengikuti:

```text
VALIDATED TRAVEL RESULT
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

AI GM tidak boleh menyatakan actor telah tersimpan di destination hanya karena narrative menyatakan actor tiba.

Jika persistence belum diverifikasi, status persistence harus tetap diketahui sebagai belum terverifikasi sesuai Runtime dan State/History rules.

## 40. Progressive Development

Travel & Movement dapat dikembangkan bertahap:

```text
TRAVEL FRAMEWORK
↓
LOCATION / ROUTE DATA
↓
MOVEMENT METHODS
↓
DURATION MODEL
↓
NAVIGATION / PATHFINDING
↓
TRANSPORT
↓
HAZARD / ENCOUNTER SYSTEMS
↓
SPECIFIC REGIONAL TRAVEL RULES
↓
CURRENT STATE / HISTORY
```

Setiap extension harus melalui dependency dan overlap audit sebelum menjadi Canon.

## 41. Integrity Rules

1. Travel & Movement adalah owner proses movement/travel, bukan owner Geography.
2. Geography tetap menjadi source untuk fakta spasial yang telah ditetapkan.
3. Time & Calendar tetap menjadi temporal authority.
4. Health & Injury tetap menjadi owner health-state dan injury-state.
5. Economy tetap menjadi owner transaksi, nilai, biaya, dan economic State.
6. Creatures / Ecology tetap menjadi owner creature dan ecological facts.
7. Combat tetap menjadi owner combat/conflict resolution.
8. Destination tidak otomatis menjadi Current Location hanya karena Player menyatakannya.
9. Route yang tidak diketahui tidak boleh diisi dengan asumsi.
10. Travel duration tidak boleh dibuat arbitrer.
11. Encounter tidak boleh di-spawn arbitrer hanya karena actor sedang traveling.
12. Hazard harus memiliki basis dunia atau system yang valid.
13. Travel method harus benar-benar tersedia bagi actor.
14. Current Location hanya berubah melalui resolution dan State Change yang valid.
15. Sequential movement menggunakan hasil action sebelumnya sebagai baseline.
16. Ongoing, delayed, interrupted, diverted, blocked, dan failed travel adalah outcome yang sah.
17. Unknown / Undefined tidak boleh diubah menjadi fakta hanya untuk menyelesaikan perjalanan.
18. Tidak ada formula, multiplier, threshold, probability, speed, cost, atau angka default universal pada v0.1.
19. Narrative bukan sumber Travel State atau persistence.
20. Persistent movement changes harus memiliki provenance dan dapat ditelusuri melalui History.
21. Autonomous movement harus memiliki dasar yang valid.
22. Travel tidak boleh mengubah authority system lain melalui dependency.
23. Jika travel berkembang menjadi combat, Combat mengambil alih combat resolution.
24. Jika travel menghasilkan health consequence, Health & Injury mengambil alih health-state resolution.
25. Jika travel menghasilkan economic consequence, Economy mengambil alih economic resolution.
26. Jika temporal result diperlukan, Time & Calendar menangani temporal authority.
27. AI GM tidak boleh mengklaim persistence berhasil tanpa verifikasi.

## 42. Summary Boundary

```text
GEOGRAPHY
= WHERE THE WORLD IS

TRAVEL & MOVEMENT
= HOW ACTORS MOVE THROUGH THAT WORLD

TIME & CALENDAR
= WHEN THE MOVEMENT OCCURS

HEALTH & INJURY
= WHAT HEALTH CONSEQUENCES OCCUR

ECONOMY
= WHAT ECONOMIC CONSEQUENCES OCCUR

CREATURES / ECOLOGY
= WHAT ECOLOGICAL CONTEXT EXISTS

COMBAT
= WHAT HAPPENS IF MOVEMENT BECOMES COMBAT

STATE & HISTORY
= WHAT PERSISTENTLY CHANGED AND HOW IT IS TRACED
```

Travel & Movement v0.1 menjadi canonical owner untuk proses perpindahan tanpa menggantikan owner Canon lain.
