# Eldoria World — Creatures / Ecology v0.1

> **Module:** Creatures / Ecology  
> **Version:** v0.1  
> **Authority:** Official Canon / Framework

## 1. Purpose

Modul Creatures / Ecology mendefinisikan kerangka bagaimana makhluk hidup dan creature Eldoria direpresentasikan, hidup dalam habitat, berinteraksi dengan lingkungan, membentuk populasi, memperoleh makanan, bereproduksi, berperilaku, dan memengaruhi ekosistem.

Modul ini juga menjadi fondasi untuk klasifikasi Wildlife dan Monsters serta simulasi ekologi yang dapat berubah secara dinamis.

Modul ini adalah framework Canon, bukan daftar creature atau monster spesifik.

## 2. Core Principles

- Creature adalah bagian dari dunia, bukan sekadar konten yang muncul untuk Player.
- Kehadiran creature harus memiliki konteks geografis, habitat, ekologi, atau Canon yang valid.
- Wildlife, Monsters, dan Peoples/Sentient Societies tidak boleh disamakan.
- Perilaku creature tidak boleh ditentukan hanya oleh kebutuhan naratif.
- Populasi, makanan, habitat, reproduksi, predasi, kompetisi, penyakit, lingkungan, dan tindakan makhluk lain dapat memengaruhi ekologi.
- Ekosistem dapat berubah tanpa keputusan Player.
- Tidak ada spawn arbitrer hanya untuk menghadirkan encounter.
- Intent Player ≠ hasil encounter.
- Detail yang belum didefinisikan tetap Unknown / Undefined.
- Perubahan persisten harus mengikuti State & History Model.

## 3. Creature Classification

Creature adalah kategori umum untuk makhluk hidup atau entitas biologis/ekologis lain yang relevan terhadap simulasi.

Kategori konseptual dapat mencakup:

```text
CREATURE
├── WILDLIFE
├── MONSTER
├── PEOPLE / SENTIENT BEING
└── OTHER CREATURE CATEGORY (if defined)
```

Kategori di atas tidak berarti setiap creature harus memiliki klasifikasi tunggal yang sederhana. Jika klasifikasi tumpang tindih atau ambigu, Canon eksplisit menjadi acuan.

## 4. Wildlife

Wildlife adalah creature yang diperlakukan terutama sebagai bagian dari ekosistem alami atau semi-alami dan bukan sebagai kelompok monster.

Wildlife dapat memiliki:

- habitat;
- kebutuhan makanan;
- wilayah jelajah;
- perilaku sosial;
- predator atau mangsa;
- siklus hidup;
- reproduksi;
- populasi;
- adaptasi lingkungan.

Tidak semua wildlife harus berbahaya bagi Character.

## 5. Monsters

Monster adalah kategori creature yang ditetapkan sebagai monster oleh Canon yang relevan.

Monster tidak boleh dianggap hanya sebagai "hewan kuat". Klasifikasi dapat memiliki dasar biologis, perilaku, supernatural, sosial, historis, atau kombinasi faktor sesuai Canon.

World Foundation menetapkan bahwa **Orc, Goblin, dan kelompok sejenis diklasifikasikan sebagai monster**.

Modul ini tidak membuat daftar monster spesifik di luar ketetapan Canon yang sudah ada.

Monster tetap merupakan bagian dari ekologi dan dunia. Mereka dapat memiliki habitat, populasi, kebutuhan, perilaku, kompetisi, migrasi, dan dampak terhadap lingkungan jika relevan.

## 6. Peoples vs Creatures vs Monsters

Peoples/Races berfokus pada makhluk berakal dan masyarakat; Creatures/Ecology berfokus pada klasifikasi creature, habitat, perilaku, populasi, dan ekosistem.

```text
PEOPLES / RACES
= identity, society, population, culture

CREATURES / ECOLOGY
= creature classification, habitat, behavior, population, ecosystem

MONSTER
= classification defined by Canon

WILDLIFE
= ecological/wild creature category
```

Kategori tidak boleh digunakan untuk menghapus fakta Canon yang sudah ada.

## 7. Habitat

Habitat adalah lingkungan tempat creature dapat hidup atau menjalankan bagian dari siklus hidupnya.

Habitat dipengaruhi oleh kondisi seperti:

- terrain;
- climate/environment;
- air;
- makanan;
- tempat berlindung;
- ruang;
- kompetisi;
- predator/mangsa;
- gangguan;
- akses;
- faktor supernatural jika relevan.

Habitat creature harus konsisten dengan Geography yang telah ditetapkan.

## 8. Food & Nutrition

Creature membutuhkan sumber energi/nutrisi sesuai biologinya atau aturan Canon yang berlaku.

Sumber makanan dapat mencakup tumbuhan, hewan, bahan organik, sumber daya tertentu, atau sumber lain jika ditetapkan.

Ketersediaan makanan dapat memengaruhi:

- wilayah jelajah;
- migrasi;
- populasi;
- kompetisi;
- perilaku;
- kondisi fisik;
- reproduksi;
- mortalitas.

Tidak ada universal diet atau kebutuhan nutrisi tanpa Canon spesifik.

## 9. Food Chain & Food Web

Ekosistem dapat memiliki hubungan:

```text
PRODUCERS
↓
HERBIVORES / PRIMARY CONSUMERS
↓
PREDATORS / HIGHER CONSUMERS
↓
DECOMPOSERS / OTHER ECOLOGICAL PROCESSES
```

Model ini bersifat konseptual. Ekosistem nyata dapat memiliki food web yang kompleks, omnivory, scavenging, kompetisi, mutualisme, parasitisme, dan hubungan lain.

Creature tidak harus selalu berada pada satu trophic role tetap jika Canon atau biologinya memungkinkan perubahan.

## 10. Population

Population adalah kumpulan individu dari creature tertentu dalam konteks ruang dan waktu.

Populasi dapat dipengaruhi oleh:

- kelahiran/reproduksi;
- kematian;
- predasi;
- penyakit;
- makanan;
- habitat;
- kompetisi;
- migrasi;
- perburuan;
- perubahan lingkungan;
- aktivitas masyarakat;
- faktor supernatural jika relevan.

Tidak ada populasi creature universal atau angka populasi default.

## 11. Life Cycle & Reproduction

Creature dapat memiliki siklus hidup yang berbeda.

Kategori dapat mencakup:

- kelahiran atau emergence;
- pertumbuhan;
- maturity;
- reproduksi;
- penuaan;
- kematian;
- metamorfosis atau perubahan bentuk jika Canon menetapkannya.

Detail lifecycle dan reproduction harus ditetapkan per creature atau sistem yang relevan.

## 12. Behavior

Perilaku creature dapat dipengaruhi oleh:

- kebutuhan biologis;
- rasa lapar/haus;
- ancaman;
- wilayah;
- reproduksi;
- kelompok sosial;
- pengalaman;
- kondisi lingkungan;
- predator/mangsa;
- musim atau kondisi temporal jika didefinisikan;
- interaksi dengan Character/NPC;
- supernatural jika relevan.

Perilaku tidak boleh diasumsikan selalu agresif.

Creature dapat menghindar, bertahan, berburu, mencari makan, bermigrasi, bersosialisasi, melindungi wilayah, atau menunjukkan perilaku lain sesuai karakteristiknya.

## 13. Territoriality & Range

Creature dapat memiliki home range, territory, migration route, nesting area, feeding ground, atau pola ruang lain.

Territory tidak otomatis berarti creature akan menyerang setiap makhluk yang masuk. Respons bergantung pada species/creature, kondisi, risiko, kelompok, sumber daya, dan konteks.

## 14. Ecosystem

Ekosistem adalah jaringan hubungan antara organisme dan lingkungan fisiknya.

Secara konseptual:

```text
ENVIRONMENT
↓
RESOURCES
↓
CREATURE POPULATIONS
↓
PREDATION / COMPETITION / COOPERATION / PARASITISM / OTHER RELATIONS
↓
ECOLOGICAL STATE
↓
CHANGE OVER TIME
```

Ecosystem tidak harus stabil. Populasi dapat naik, turun, berpindah, atau menghilang ketika kondisi berubah.

## 15. Creature–Environment Interaction

Creature dapat memengaruhi lingkungannya, dan lingkungan dapat memengaruhi creature.

Contoh konseptual:

```text
ENVIRONMENT CHANGE
↓
HABITAT / RESOURCE CHANGE
↓
CREATURE RESPONSE
↓
POPULATION / DISTRIBUTION CHANGE
↓
ECOSYSTEM CONSEQUENCE
```

Sebaliknya:

```text
CREATURE ACTIVITY
↓
RESOURCE / VEGETATION / PREY CHANGE
↓
LOCAL ENVIRONMENT CHANGE
↓
OTHER CREATURE RESPONSE
```

Dampak hanya diterapkan jika ada mekanisme atau dasar simulasi yang relevan.

## 16. Monster Ecology

Monster harus diperlakukan sebagai bagian dari ekologi ketika sifatnya memungkinkan.

Monster dapat memiliki:

- habitat;
- sumber makanan;
- populasi;
- territory;
- reproduksi atau lifecycle;
- migrasi;
- predator atau ancaman;
- kompetitor;
- hubungan dengan masyarakat;
- dampak ekologis;
- hubungan supernatural jika didefinisikan.

Monster tidak otomatis muncul karena Player memasuki area tertentu.

## 17. Creature–People Interaction

Interaksi antara creature dan masyarakat dapat mencakup:

- perburuan;
- peternakan atau domestikasi jika memungkinkan;
- perdagangan;
- pemanfaatan bahan;
- perlindungan;
- konflik;
- pengendalian hama;
- kerusakan tanaman;
- predasi terhadap ternak atau manusia;
- penelitian;
- coexistence;
- perubahan habitat.

Hasil interaksi bergantung pada kondisi dunia, kemampuan pihak terkait, dan konsekuensi yang relevan.

## 18. Domestication, Taming & Captivity

Domestikasi, penjinakan, pemeliharaan, atau penangkaran adalah proses khusus dan tidak otomatis berhasil hanya karena Player menginginkannya.

Jika sistem khusus untuk taming/domestication belum dibuat, AI GM tidak boleh menganggap keberhasilan atau loyalitas sebagai fakta universal.

Kondisi, perilaku, biology, pengalaman, dan hubungan dengan Character dapat menjadi faktor jika ditetapkan oleh sistem relevan.

## 19. Population Dynamics

Populasi creature dapat berubah melalui proses seperti:

```text
REPRODUCTION
+
MORTALITY
+
MIGRATION
+
RESOURCE AVAILABILITY
+
PREDATION
+
DISEASE
+
HABITAT CHANGE
+
HUMAN / PEOPLE ACTIVITY
+
OTHER VALID FACTORS
↓
POPULATION CHANGE
```

V0.1 menetapkan prinsip, bukan formula populasi universal.

## 20. Ecological Events & Shocks

Perubahan ekologi dapat dipicu oleh:

- kekeringan;
- banjir;
- kebakaran;
- badai;
- penyakit;
- perubahan habitat;
- hilangnya sumber makanan;
- ledakan populasi;
- perburuan berlebihan;
- migrasi besar;
- konflik;
- perubahan iklim lokal jika sistem mendefinisikannya;
- aktivitas supernatural;
- perubahan Geography;
- kejadian lain yang memiliki dasar valid.

Dampak harus bergantung pada ekosistem dan kondisi lokal, bukan formula naratif seragam.

## 21. Ecological Autonomy

Ekosistem dapat berubah tanpa keputusan Player.

Wildlife dan monster dapat bergerak, mencari makanan, berkembang biak, bermigrasi, mati, atau mengubah distribusinya berdasarkan proses dunia yang valid.

AI GM tidak boleh menggerakkan seluruh ekologi hanya untuk menciptakan encounter bagi Player.

Namun encounter dapat terjadi secara natural apabila kondisi dunia membuatnya relevan.

## 22. Creature Data Model

```text
CREATURE ENTITY
├── Creature ID
├── Name
├── Classification
├── Sapience / Sentience Status (if defined)
├── Biological Profile (if defined)
├── Habitat
├── Geographic Distribution
├── Diet / Nutrition
├── Lifecycle
├── Reproduction
├── Behavior
├── Social Structure (if applicable)
├── Territory / Range
├── Predators / Prey / Competitors
├── Ecological Role
├── Population Context
├── Supernatural Characteristics (if defined)
├── People / Civilization Interaction (if applicable)
├── Current State Reference (if applicable)
├── History Reference (if applicable)
└── Metadata
```

Tidak semua field wajib tersedia untuk setiap creature.

### Creature Population State

```text
CREATURE POPULATION STATE
├── Population ID
├── Creature ID
├── Geographic Context
├── Estimated / Known Population (if defined)
├── Distribution
├── Habitat Condition
├── Resource Condition
├── Reproduction Condition
├── Mortality Pressure
├── Migration / Movement
├── Threats / Pressures
├── Ecological Relationships
├── Current State Reference
└── History Reference
```

## 23. Ecological Event Model

```text
ECOLOGICAL EVENT
├── Event ID
├── World Time
├── Geographic Context
├── Affected Creature / Population
├── Cause
├── Environmental Conditions
├── Resolution
├── Ecological Consequences
├── State Changes
└── History Reference
```

## 24. State & History Integration

Perubahan persisten pada creature, population, habitat condition, distribution, ecological event, atau hubungan creature harus mengikuti State & History Model.

```text
CAUSE / EVENT / PROCESS
↓
VALIDATE
↓
RESOLVE
↓
CONSEQUENCES
↓
STATE CHANGE
↓
VALIDATE
↓
APPLY
↓
HISTORY
↓
PERSIST
↓
VERIFY
```

Narasi encounter tidak otomatis mengubah population, creature state, atau ecology.

## 25. Runtime / Resolution

Creature interaction mengikuti Runtime Turn Model.

Contoh alur konseptual:

```text
PLAYER ACTION / WORLD PROCESS
↓
PARSE
↓
VALIDATE CONTEXT
↓
IDENTIFY CREATURE / ECOLOGICAL DATA
↓
RESOLVE
↓
CONSEQUENCES
↓
STATE CHANGES
↓
HISTORY
↓
PERSISTENCE
↓
RESPONSE
```

AI GM harus mengambil data creature, habitat, kondisi, dan history yang relevan sebelum membuat resolusi yang bergantung pada data tersebut.

## 26. Knowledge Boundary

```text
CREATURE CANON
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
```

Character tidak otomatis mengetahui species, habitat, weakness, population, behavior, atau lokasi creature hanya karena Player mengetahuinya.

Rumor atau folklore tidak otomatis menjadi fakta creature Canon.

## 27. Progressive Development

Creatures / Ecology dikembangkan bertahap:

```text
CREATURE / ECOLOGY FRAMEWORK
↓
CLASSIFICATION
↓
HABITAT / ECOLOGICAL ROLES
↓
SPECIFIC CREATURE / MONSTER / WILDLIFE
↓
POPULATIONS / DISTRIBUTION
↓
BEHAVIOR / INTERACTIONS
↓
ECOLOGICAL EVENTS
↓
CURRENT STATE / HISTORY
```

Framework tidak menciptakan daftar creature secara otomatis.

## 28. Canon Boundary

Creatures / Ecology v0.1 **tidak** menetapkan:

- daftar creature;
- daftar monster;
- daftar wildlife;
- jumlah species;
- universal biology;
- universal lifespan;
- universal reproduction model;
- universal diet;
- universal behavior;
- habitat spesifik;
- population count spesifik;
- daftar predator/mangsa;
- food web spesifik;
- monster stat block;
- combat stats;
- loot table;
- taming success formula;
- domestication rules universal;
- ecological simulation formula universal;
- daftar penyakit creature;
- supernatural creature list;
- creature-specific history.

Detail tersebut hanya menjadi Canon setelah ditetapkan secara eksplisit melalui modul atau data yang relevan.

## 29. Dependencies & Integration

Creatures / Ecology berinteraksi dengan:

```text
WORLD FOUNDATION
├── GEOGRAPHY
├── CIVILIZATION
├── PEOPLES / RACES
├── POLITICS
├── SUPERNATURAL / MAGIC
├── ECONOMY
├── STATE / HISTORY
└── RUNTIME
```

Geography menyediakan konteks habitat dan ruang. Civilization, Peoples, Politics, dan Economy menyediakan konteks interaksi masyarakat. Supernatural/Magic dapat memengaruhi creature bila mekaniknya telah ditetapkan.

Creatures / Ecology tidak mengambil alih tanggung jawab modul lain.

## 30. Integrity Rules

1. Jangan spawn creature hanya karena Player membutuhkan encounter.
2. Jangan mengubah wildlife menjadi monster atau sebaliknya tanpa Canon yang valid.
3. Jangan menganggap semua creature agresif.
4. Jangan menganggap semua monster selalu menyerang Character.
5. Jangan menganggap semua creature dapat dijinakkan.
6. Jangan menciptakan population count tanpa dasar.
7. Jangan menciptakan habitat yang bertentangan dengan Geography.
8. Jangan memberikan biology, diet, lifespan, reproduction, atau abilities yang belum Canon sebagai fakta.
9. Jangan mengubah satu encounter menjadi perubahan ekologi besar tanpa sebab dan konsekuensi yang relevan.
10. Creature population dan ecology dapat berubah secara autonomous, tetapi harus memiliki basis simulasi yang sah.
11. Creature State Change penting harus memiliki Cause/Origin/Source yang dapat ditelusuri.
12. Unknown / Undefined tetap Unknown / Undefined.
13. Monster tidak otomatis berarti supernatural.
14. Supernatural creature tidak otomatis memiliki kemampuan tertentu tanpa Canon.
15. Peoples/Races tidak boleh direklasifikasi hanya untuk kebutuhan gameplay.
16. Narrative bukan sumber persistence.
17. Klaim persistence harus diverifikasi.
18. Perubahan ekologis yang saling bergantung harus divalidasi sebagai satu rangkaian yang konsisten sebelum dipersistenkan.
19. Creature ecology harus konsisten dengan World Foundation, Geography, Civilization, Peoples/Races, Politics, Economy, dan Supernatural/Magic yang relevan.
