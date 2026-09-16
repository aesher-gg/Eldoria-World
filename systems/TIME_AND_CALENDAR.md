# Eldoria World — Time & Calendar System v0.1

> **Module:** Time & Calendar  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Time & Calendar v0.1 menetapkan **canonical temporal authority** Eldoria: bagaimana waktu dunia direpresentasikan, bagaimana posisi waktu diketahui, bagaimana waktu dapat berlalu, bagaimana kalender digunakan ketika telah didefinisikan, dan bagaimana waktu terintegrasi dengan Runtime, State, History, serta world systems lain.

Modul ini dibuat sebagai fondasi temporal untuk persistent-world simulation. Modul ini **tidak** secara otomatis menetapkan nama kalender, jumlah hari dalam tahun, jumlah bulan, panjang musim, atau durasi unit waktu tertentu kecuali dinyatakan secara eksplisit sebagai Canon.

## 2. Canonical Temporal Authority

Untuk semua system yang membutuhkan informasi waktu, `systems/TIME_AND_CALENDAR.md` adalah canonical owner bagi **representasi dan resolusi temporal**.

Prinsip:

```text
TIME & CALENDAR
        ↓
CANONICAL TEMPORAL CONTEXT
        ↓
RUNTIME / STATE / HISTORY / WORLD SYSTEMS
```

System lain boleh menggunakan waktu, tetapi tidak boleh membuat definisi kalender atau temporal authority sendiri secara diam-diam.

Dependency tidak memberi hak kepada system lain untuk mengubah aturan Time & Calendar.

## 3. Core Principles

- Dunia Eldoria memiliki waktu yang berjalan secara independen dari Player.
- Waktu adalah bagian dari State dunia ketika temporal context diperlukan.
- Waktu yang belum diketahui tetap `Unknown / Undefined`.
- Character Knowledge tentang waktu tidak sama dengan Canonical World Time.
- Intent Player tidak otomatis menentukan berapa lama suatu action berlangsung.
- Hasil action dapat menyebabkan waktu berlalu apabila resolution system yang relevan menetapkan elapsed time.
- Tidak ada time skip arbitrer untuk kebutuhan narasi.
- Tidak ada waktu yang dibuat hanya untuk melengkapi response atau History.
- Calendar adalah representasi temporal; Calendar bukan satu-satunya konsep waktu.
- Perubahan waktu yang persisten harus dapat ditelusuri melalui State/History ketika relevan.
- System lain menggunakan temporal authority ini sebagai dependency, bukan menduplikasi definisinya.

## 4. Temporal Concepts

### World Time

World Time adalah posisi temporal yang berlaku bagi dunia atau konteks simulasi tertentu pada suatu titik waktu.

### Calendar

Calendar adalah sistem representasi yang mengorganisasi World Time ke dalam unit dan label yang dapat digunakan oleh masyarakat atau sistem.

### Duration

Duration adalah lamanya suatu proses atau interval antara dua titik waktu.

### Timestamp

Timestamp adalah representasi posisi waktu yang dilekatkan pada event, State Change, History Record, atau data lain yang membutuhkan konteks temporal.

### Temporal Context

Temporal Context adalah kumpulan informasi waktu yang relevan terhadap suatu subject, location, event, atau process.

```text
WORLD TIME ≠ CALENDAR ≠ DURATION ≠ TIMESTAMP
```

## 5. Temporal Representation

System harus mampu merepresentasikan waktu secara bertingkat tanpa memaksa semua field selalu diketahui.

Model konseptual:

```text
TEMPORAL CONTEXT
├── World Time Reference
├── Calendar Reference (if defined)
├── Era / Year (if defined)
├── Month / Period (if defined)
├── Date / Day Position (if defined)
├── Day / Night Context (if defined)
├── Clock / Time-of-Day (if defined)
├── Season (if defined)
├── Duration Context (if applicable)
└── Knowledge / Confidence Context (if applicable)
```

Field yang belum memiliki Canon tetap `Unknown / Undefined`; tidak boleh diisi dengan default.

## 6. Temporal State

World State dapat memiliki temporal state yang menjadi acuan runtime.

Model konseptual:

```text
WORLD TEMPORAL STATE
├── Temporal State ID
├── World Time Reference
├── Calendar Reference (if defined)
├── Current Temporal Position
├── Active Temporal Conditions (if applicable)
├── Source / Origin
├── Revision
└── Validation Status
```

Jika simulasi memiliki konteks waktu berbeda untuk subject tertentu, perbedaan tersebut harus memiliki dasar system atau State yang sah. System tidak boleh membuat dua World Time yang bertentangan tanpa model temporal yang eksplisit.

## 7. Calendar Structure

Eldoria dapat memiliki satu atau beberapa calendar yang digunakan oleh masyarakat atau institusi yang berbeda apabila Canon menetapkannya.

Calendar dapat memiliki struktur seperti:

```text
CALENDAR
├── Calendar ID
├── Name
├── Era Structure (if defined)
├── Year Structure (if defined)
├── Period / Month Structure (if defined)
├── Date Structure (if defined)
├── Day Structure (if defined)
├── Seasonal Relationship (if defined)
├── Cultural / Institutional Use
├── Conversion Rules (if defined)
└── Metadata
```

V0.1 tidak menetapkan kalender tertentu sebagai satu-satunya kalender universal Eldoria.

## 8. Multiple Calendars

Jika beberapa calendar digunakan di Eldoria, setiap calendar harus memiliki identitas dan aturan konversi yang jelas apabila diperlukan.

```text
WORLD TIME
├── CALENDAR A
├── CALENDAR B
└── OTHER VALID CALENDAR
```

Calendar yang berbeda dapat memberi label berbeda untuk titik temporal yang sama.

Perbedaan label calendar tidak berarti terdapat dua World Time yang berbeda.

Jika hubungan antar-calendar belum didefinisikan, konversi harus dianggap `Unknown / Undefined`.

## 9. Era, Year, Period & Date

Unit temporal seperti era, year, month, week, period, date, atau day dapat digunakan jika calendar yang relevan mendefinisikannya.

System tidak boleh mengasumsikan:

- jumlah hari per year;
- jumlah period/month per year;
- panjang period/month;
- jumlah hari per week;
- nama month/period;
- nama day;
- panjang era;
- titik awal era;
- atau struktur kalender lain

tanpa Canon yang eksplisit.

## 10. Seasons

Season adalah konteks temporal yang dapat digunakan ketika telah didefinisikan oleh Canon atau system yang relevan.

Season dapat berhubungan dengan Geography, environment, agriculture, ecology, culture, travel, dan kehidupan sehari-hari.

Namun Time & Calendar v0.1 tidak menetapkan jumlah season, nama season, panjang season, atau hubungan universal season dengan bulan/date.

```text
SEASON
≠
WEATHER
≠
CLIMATE
```

Weather dan climate tetap berada pada domain yang relevan.

## 11. Day / Night & Time of Day

System dapat merepresentasikan posisi dalam siklus harian jika diperlukan.

Kategori seperti dawn, morning, noon, afternoon, dusk, evening, night, atau istilah lain hanya menjadi aturan temporal apabila didefinisikan secara resmi.

Time of day dapat dipengaruhi oleh lokasi atau model dunia jika Canon kemudian menetapkannya.

System tidak boleh mengarang waktu matahari terbit/terbenam atau durasi siang/malam tanpa data atau aturan yang sah.

## 12. Duration

Duration harus memiliki sumber yang dapat ditelusuri.

Duration dapat berasal dari:

- system-specific resolution;
- explicit world process;
- event;
- action yang berhasil atau gagal jika system terkait menetapkannya;
- environmental process;
- autonomous process;
- atau sumber valid lain.

Prinsip:

```text
ACTION / PROCESS
↓
VALIDATE
↓
RESOLVE
↓
ELAPSED DURATION
↓
WORLD TIME ADVANCE
```

Time & Calendar tidak boleh mengarang duration untuk system yang belum mendefinisikannya.

## 13. Time Advancement

World Time dapat maju ketika terjadi proses yang memang mengonsumsi waktu.

Model konseptual:

```text
CURRENT WORLD TIME
        ↓
VALIDATED TEMPORAL INPUT
        ↓
ELAPSED DURATION
        ↓
TEMPORAL RESOLUTION
        ↓
NEW WORLD TIME
```

Time advancement harus bersifat deterministik terhadap input temporal yang sudah valid sejauh rules system memungkinkan.

Jika duration tidak diketahui atau tidak dapat divalidasi, system tidak boleh memilih durasi arbitrer sebagai fallback.

## 14. Turn & Time

Satu Player Message tetap merupakan satu Runtime Turn sesuai `core/RUNTIME_TURN_MODEL.md`.

Namun satu Turn tidak otomatis memiliki durasi temporal universal.

```text
ONE TURN
≠
FIXED TIME DURATION
```

Sebuah Turn dapat:

- tidak menghabiskan waktu yang berarti;
- menghasilkan elapsed time;
- mengandung beberapa action berurutan dengan durasi berbeda;
- berakhir tanpa perubahan waktu apabila resolution yang sah menetapkannya demikian.

Durasi action harus berasal dari system atau proses yang memiliki authority untuk menentukannya.

## 15. Sequential Actions

Jika satu Turn memiliki beberapa action, elapsed time harus diproses secara berurutan bila masing-masing action menghasilkan perubahan temporal.

```text
TIME T0
↓
ACTION A
↓
VALIDATED DURATION A
↓
TIME T1
↓
ACTION B
↓
VALIDATED DURATION B
↓
TIME T2
```

Action berikutnya harus menggunakan temporal context hasil action sebelumnya.

System tidak boleh menghitung seluruh action seolah-olah semuanya terjadi pada waktu yang sama jika resolution menetapkan adanya elapsed time.

## 16. Concurrent Processes

Beberapa process dunia dapat berlangsung pada interval yang beririsan.

Jika concurrency relevan:

```text
TIME INTERVAL
├── PROCESS A
├── PROCESS B
└── PROCESS C
```

Resolution harus mempertahankan konsistensi temporal dan menentukan urutan hanya ketika urutan memang diperlukan oleh causal dependency atau aturan system.

Time System tidak boleh mengubah proses concurrent menjadi sequential secara arbitrer hanya karena keterbatasan narasi.

## 17. Temporal Ordering

Event dan State Change harus dapat ditempatkan dalam urutan temporal ketika timestamp tersedia.

Hubungan minimum:

```text
EARLIER
↓
CONTEMPORANEOUS / OVERLAPPING (if valid)
↓
LATER
```

Jika dua record tidak memiliki presisi waktu yang cukup untuk menentukan urutan, system harus mempertahankan ketidakpastian tersebut daripada mengarang urutan.

## 18. Temporal Integrity

Temporal integrity berarti timestamp, duration, dan World Time tidak saling bertentangan.

Setidaknya periksa:

- sumber World Time valid;
- duration memiliki basis valid;
- waktu baru tidak bertentangan dengan waktu sebelumnya;
- urutan event masuk akal terhadap timestamp;
- State Change memakai waktu yang sesuai dengan resolution;
- History dapat direkonsiliasi dengan temporal state;
- calendar representation konsisten dengan World Time ketika conversion tersedia.

Jika validasi gagal, temporal change tidak boleh diterapkan sebagai fakta final.

## 19. State & History Integration

World Time menjadi bagian penting dari State Snapshot, State Change, dan History ketika konteks temporal diperlukan.

```text
VALIDATED PROCESS
↓
TEMPORAL RESULT
↓
STATE CHANGE
├── Previous World Time
└── New World Time
        ↓
HISTORY RECORD
        ↓
PERSIST
        ↓
VERIFY
```

Time advancement yang persisten tidak boleh hanya disebut dalam narrative tanpa State/History yang sesuai ketika persistence diperlukan.

## 20. Runtime Integration

Time & Calendar terintegrasi dengan Runtime sebagai berikut:

```text
LOAD CURRENT STATE
↓
READ CURRENT WORLD TIME
↓
PARSE PLAYER / NPC / WORLD INPUT
↓
VALIDATE
↓
SYSTEM-SPECIFIC RESOLUTION
↓
DETERMINE VALID ELAPSED TIME
↓
ADVANCE WORLD TIME
↓
CALCULATE CONSEQUENCES
↓
GENERATE STATE CHANGES
↓
VALIDATE
↓
HISTORY
↓
PERSIST
↓
VERIFY
↓
RESPONSE
```

Urutan detail dapat berbeda ketika suatu system memerlukan temporal resolution sebelum consequence calculation, tetapi perubahan waktu tetap harus memiliki source dan validasi.

## 21. World Autonomy

Waktu dunia berjalan tanpa menunggu Player.

Autonomous systems dapat menghasilkan temporal advancement melalui proses yang sah, misalnya event dunia, ecological process, political process, economic process, atau proses lain yang memiliki duration yang didefinisikan.

```text
AUTONOMOUS PROCESS
↓
VALIDATED DURATION
↓
TIME ADVANCEMENT
↓
WORLD CONSEQUENCES
```

Time System sendiri tidak membuat event acak hanya untuk membuat waktu terasa hidup.

## 22. Knowledge Boundary

```text
CANONICAL WORLD TIME
≠
CHARACTER PERCEPTION / KNOWLEDGE
≠
PLAYER KNOWLEDGE
```

Character dapat salah memperkirakan waktu, tidak mengetahui tanggal, menggunakan calendar berbeda, atau memiliki informasi temporal yang terbatas jika hal tersebut sesuai dengan Canon dan State.

Player tidak otomatis mengetahui hidden temporal state hanya karena system memiliki data tersebut.

## 23. Temporal Uncertainty

System dapat merepresentasikan waktu dengan presisi berbeda.

Contoh konseptual:

```text
EXACT
↓
APPROXIMATE
↓
PERIOD-LEVEL
↓
DATE-UNKNOWN
↓
TIME-UNKNOWN
```

Tingkat presisi harus dibedakan dari nilai yang benar-benar diketahui.

Jika hanya diketahui bahwa sebuah event terjadi "sekitar suatu periode", system tidak boleh mengubahnya menjadi timestamp exact tanpa source.

## 24. Calendar Conversion

Jika lebih dari satu calendar digunakan, conversion hanya boleh dilakukan apabila hubungan antar-calendar telah didefinisikan.

Model:

```text
WORLD TIME
↓
CALENDAR A REPRESENTATION
↕
VALIDATED CONVERSION RULE
↕
CALENDAR B REPRESENTATION
```

Tanpa conversion rule, perbedaan label harus tetap `Unknown / Undefined`.

## 25. Temporal Events

Event dapat memiliki:

- start time;
- end time;
- duration;
- recurrence;
- deadline;
- temporal condition;
- atau temporal relationship lain

jika system event yang relevan mendefinisikannya.

Time & Calendar menyediakan representasi temporalnya; Event System kelak memiliki authority atas lifecycle event.

Time System tidak menciptakan event hanya karena sebuah tanggal telah tiba.

## 26. Character Integration

Character dapat memiliki temporal information seperti:

- current temporal context;
- known date/time;
- calendar familiarity;
- deadlines atau appointments dari system lain;
- historical timestamps;
- temporal conditions.

Namun Character Data Model tetap menjadi canonical owner struktur karakter. Time System hanya menyediakan data temporal dan rules yang dibutuhkan.

## 27. System Dependencies

Time & Calendar bergantung pada:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
characters/CHARACTER_DATA_MODEL.md
world/WORLD_FOUNDATION.md
world/GEOGRAPHY.md
world/CIVILIZATION.md
world/PEOPLES_RACES.md
world/POLITICS.md
world/SUPERNATURAL_MAGIC.md
world/ECONOMY.md
world/CREATURES_ECOLOGY.md
world/FACTIONS.md
```

Dependency utama adalah Runtime dan State/History. World Canon lain menjadi dependency kontekstual karena menggunakan atau dipengaruhi oleh waktu.

System khusus lain harus merujuk Time & Calendar ketika membutuhkan temporal authority.

## 28. Data Model

### Calendar Entity

```text
CALENDAR ENTITY
├── Calendar ID
├── Name
├── Era Structure (if defined)
├── Year Structure (if defined)
├── Period / Month Structure (if defined)
├── Date Structure (if defined)
├── Day Structure (if defined)
├── Seasonal Relationship (if defined)
├── Conversion Rules (if defined)
├── Users / Cultural Context
├── Current State Reference (if applicable)
├── History Reference (if applicable)
└── Metadata
```

### Temporal State

```text
TEMPORAL STATE
├── Temporal State ID
├── World Time Reference
├── Calendar Reference (if defined)
├── Current Temporal Position
├── Precision / Uncertainty
├── Source / Origin
├── Revision
└── Validation Status
```

### Time Advancement Record

```text
TIME ADVANCEMENT
├── Advancement ID
├── Previous World Time
├── Elapsed Duration
├── New World Time
├── Cause / Process
├── Origin
├── Source
├── Consequences
├── State Changes
└── History Reference
```

### Temporal Event Reference

```text
TEMPORAL EVENT REFERENCE
├── Event ID
├── Start Time (if defined)
├── End Time (if defined)
├── Duration (if defined)
├── Recurrence (if defined)
├── Deadline (if defined)
├── Temporal Conditions
└── Source / History Reference
```

## 29. Canon Boundary

Time & Calendar v0.1 **tidak** menetapkan secara universal:

- nama kalender;
- jumlah kalender Eldoria;
- nama era;
- tahun awal/final dunia;
- jumlah tahun dalam era;
- jumlah bulan/period dalam tahun;
- nama bulan/period;
- jumlah hari dalam bulan/period;
- jumlah hari dalam tahun;
- jumlah hari dalam minggu;
- nama hari;
- panjang hari;
- panjang jam/menit/detik dalam ukuran dunia;
- jumlah atau nama musim;
- panjang musim;
- hubungan musim dengan calendar date;
- waktu matahari terbit/terbenam universal;
- kecepatan waktu untuk semua action;
- durasi universal Turn;
- travel duration;
- combat duration;
- crafting duration;
- sleep/rest duration;
- progression duration;
- event schedule;
- formula time dilation;
- time manipulation magic;
- atau formula temporal universal lain yang belum ditetapkan.

Detail tersebut hanya menjadi Canon setelah didefinisikan secara eksplisit oleh system atau data yang berwenang.

## 30. Integrity Rules

1. Time & Calendar adalah canonical owner untuk temporal representation dan calendar rules yang telah ditetapkan.
2. System lain tidak boleh membuat kalender atau World Time authority sendiri secara diam-diam.
3. World Time tidak boleh dibuat hanya untuk melengkapi narrative.
4. Duration harus memiliki basis yang dapat ditelusuri ketika duration memengaruhi State atau World Time.
5. One Turn tidak otomatis memiliki fixed duration.
6. Sequential actions harus menggunakan temporal context hasil action sebelumnya ketika elapsed time terjadi.
7. Concurrent processes tidak boleh diurutkan secara arbitrer jika tidak diperlukan.
8. Timestamp yang tidak cukup presisi tidak boleh diubah menjadi exact time tanpa source.
9. Unknown / Undefined tidak boleh diisi dengan nilai temporal default.
10. Calendar representation tidak boleh dianggap sebagai World Time itu sendiri.
11. Calendar conversion membutuhkan rule yang valid.
12. Season, weather, dan climate tidak boleh disamakan.
13. Time System tidak mengambil alih domain Event, Travel, Combat, Crafting, Ecology, Economy, Politics, atau domain lain.
14. Persistent temporal changes harus mengikuti State & History Model.
15. History dan State harus dapat direkonsiliasi dengan temporal state.
16. Autonomous time advancement membutuhkan proses atau duration yang valid.
17. Tidak boleh ada time skip arbitrer untuk kebutuhan narrative.
18. Konflik temporal adalah integrity issue dan tidak boleh diselesaikan diam-diam.
19. Ekstensi Time & Calendar tidak boleh mengubah Core Canon lain secara implisit.
20. Setiap perubahan Canon dilakukan secara eksplisit melalui Repository.

## 31. Progressive Development

Time & Calendar dikembangkan bertahap:

```text
TEMPORAL AUTHORITY FRAMEWORK
↓
TEMPORAL REPRESENTATION
↓
CALENDAR DEFINITION
↓
WORLD TIME DATA
↓
TIME ADVANCEMENT RULES
↓
SYSTEM-SPECIFIC DURATION RULES
↓
TEMPORAL EVENTS / DEADLINES
↓
CURRENT STATE / HISTORY
```

System v0.1 menyediakan fondasi dan authority boundary. Detail calendar dan duration dapat ditambahkan melalui Canon yang eksplisit tanpa mengubah ownership temporal.
