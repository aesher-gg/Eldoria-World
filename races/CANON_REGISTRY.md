# ELDORIA WORLD — RACE CANON REGISTRY

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1
> **Purpose:** Registry resmi ras Canon Eldoria

## 1. Authority

File ini adalah satu-satunya registry resmi untuk identity dan definition ras Canon Eldoria.

AI GM boleh menggunakan ras yang terdaftar untuk Character, NPC, Population Model, Faction, dan runtime generation sesuai rules.

AI GM **tidak boleh** membuat ras Canon baru, mengubah definition, atau menghapus ras Canon melalui narrative/runtime generation.

Perubahan registry membutuhkan Admin Canon update.

## 2. Race Identity Contract

Setiap ras Canon yang terdaftar memiliki stable:

```text
RACE_CANON_ID
NAME
CLASSIFICATION
DESCRIPTION
ORIGIN
HISTORY
LIFESPAN / AGING MODEL
BIOLOGICAL TRAITS
INNATE CAPABILITIES
HABITAT / HISTORICAL DISTRIBUTION
CULTURAL VARIATION BOUNDARIES
CANON_ORIGIN
STATUS
```

Field yang belum ditetapkan = `???`.

## 3. Canon vs Runtime

```text
CANON RACE DEFINITION
        ↓
Population / Character / NPC / Faction / World Simulation
        ↓
CURRENT STATE
```

Race Canon adalah identity/definition. Current population, location, migration, relationship, affiliation, dan kondisi lain berada pada state layer yang relevan.

## 4. Population Rule

Registry tidak menentukan jumlah individu atau persentase populasi.

Satu ras dapat memiliki populasi sangat besar tanpa file individual untuk setiap anggota.

Distribusi populasi ditentukan oleh Canon geography, history, migration, culture, settlement context, faction policy, environment, dan Population Model yang sah.

## 5. Classification Rule

`CLASSIFICATION` membedakan kategori ras Canon yang ditetapkan Admin.

Subrace, hybrid/mixed lineage, ethnicity, clan, cultural group, atau monster species/type tidak otomatis menjadi Race Canon terpisah.

## 6. OFFICIAL CANON RACES

Eldoria Canon v1.0 menetapkan **9 ras utama**. Daftar ini adalah fondasi awal dunia, bukan batas mutlak bahwa ras tambahan mustahil ada; ras baru hanya sah setelah Admin Canon menambahkannya ke registry.

### RACE-001 — HUMAN

```text
RACE_CANON_ID: RACE-001
NAME: Human
CLASSIFICATION: Sapient Humanoid — Generalist
DESCRIPTION: Ras humanoid yang tersebar luas dan memiliki variasi fisik, budaya, bahasa, organisasi sosial, serta pola hidup yang sangat beragam. Human menjadi salah satu ras dengan jangkauan geografis paling luas di Eldoria.
ORIGIN: ???
HISTORY: Populasi Human berkembang dan bermigrasi di berbagai wilayah Eldoria; sejarah awal dan hubungan dengan ras lain = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Anatomi humanoid adaptif dengan variasi populasi yang luas.
INNATE CAPABILITIES: Tidak memiliki kemampuan supernatural universal yang ditetapkan; kemampuan individual mengikuti Attributes, Class, Skills, Magic, training, equipment, dan progression.
HABITAT / HISTORICAL DISTRIBUTION: Tersebar luas di berbagai region dan settlement, termasuk wilayah heartland seperti Valedorn; distribusi persentase = ???
CULTURAL VARIATION BOUNDARIES: Variasi budaya sangat luas. Human tidak memiliki satu budaya atau satu political allegiance universal.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-002 — ELF

```text
RACE_CANON_ID: RACE-002
NAME: Elf
CLASSIFICATION: Sapient Humanoid — Long-lived Forest/Arcane Lineage
DESCRIPTION: Ras humanoid berumur panjang dengan tradisi yang secara historis memiliki hubungan kuat dengan hutan, lingkungan alami, pengetahuan lama, dan praktik arcane tertentu. Tidak semua Elf hidup dalam hutan atau memiliki kemampuan magic.
ORIGIN: ???
HISTORY: Memiliki sejarah panjang yang mencakup komunitas dan wilayah yang belum seluruhnya dipetakan dalam Canon; hubungan historis dengan ras lain = ???
LIFESPAN / AGING MODEL: Long-lived; nilai usia/lifecycle spesifik = ???
BIOLOGICAL TRAITS: Fisiologi humanoid berumur panjang; detail biologis tambahan = ???
INNATE CAPABILITIES: Sensory/biological traits spesifik = ???; magic tidak otomatis dimiliki semua Elf.
HABITAT / HISTORICAL DISTRIBUTION: Secara historis terkait dengan wilayah berhutan dan lingkungan yang kaya natural/arcane features; lokasi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Terdapat variasi budaya; Forest Elf, High Elf, atau subkelompok lain belum dianggap ras terpisah tanpa Canon definition.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-003 — DWARF

```text
RACE_CANON_ID: RACE-003
NAME: Dwarf
CLASSIFICATION: Sapient Humanoid — Mountain/Artisan Lineage
DESCRIPTION: Ras humanoid bertubuh kokoh yang secara historis berkaitan dengan wilayah pegunungan, pertambangan, metalurgi, rekayasa, dan kerajinan presisi.
ORIGIN: ???
HISTORY: Sejarah awal dan jaringan kerajaan/komunitas bawah tanah atau pegunungan = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Struktur tubuh kokoh dan adaptasi fisik yang sesuai dengan lingkungan berat; detail biologis = ???
INNATE CAPABILITIES: Ketahanan/karakteristik biologis spesifik = ???; keterampilan crafting tetap memerlukan training/skill.
HABITAT / HISTORICAL DISTRIBUTION: Secara historis berkaitan dengan pegunungan, kawasan batuan, dan pusat pertambangan/kerajinan; lokasi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Komunitas Dwarf dapat memiliki budaya, guild, clan, dan kepentingan politik berbeda.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-004 — HALFLING

```text
RACE_CANON_ID: RACE-004
NAME: Halfling
CLASSIFICATION: Sapient Humanoid — Small-bodied Agrarian/Trade Lineage
DESCRIPTION: Ras humanoid berukuran relatif kecil yang secara historis memiliki hubungan kuat dengan komunitas pertanian, settlement, perdagangan lokal, hospitality, dan jaringan sosial berbasis komunitas.
ORIGIN: ???
HISTORY: Sejarah migrasi dan pembentukan komunitas = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Postur relatif kecil dan adaptasi biologis lainnya = ???
INNATE CAPABILITIES: Tidak ada kemampuan supernatural universal yang ditetapkan; trait khusus = ???
HABITAT / HISTORICAL DISTRIBUTION: Umumnya dapat ditemukan dalam settlement agraris, jalur perdagangan, dan komunitas campuran; lokasi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Banyak komunitas dapat berbagi akar budaya tanpa harus memiliki identitas politik yang sama.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-005 — BEASTFOLK

```text
RACE_CANON_ID: RACE-005
NAME: Beastfolk
CLASSIFICATION: Sapient Humanoid — Bestial-Ancestry Lineage
DESCRIPTION: Kelompok ras sapient humanoid dengan ciri fisik yang berasal dari berbagai garis keturunan bestial. Beastfolk diperlakukan sebagai satu Race Canon tingkat utama, sementara sublineage atau bentuk spesifik tidak otomatis menjadi ras terpisah.
ORIGIN: ???
HISTORY: Asal-usul garis keturunan dan sejarah hubungan antarkomunitas Beastfolk = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Ciri anatomi bestial bervariasi menurut lineage; parameter spesifik = ???
INNATE CAPABILITIES: Trait sensorik/fisik tertentu dapat berbeda menurut lineage dan harus ditetapkan/dirutekan secara sah; tidak ada kemampuan universal yang ditebak.
HABITAT / HISTORICAL DISTRIBUTION: Dapat ditemukan pada berbagai lingkungan sesuai lineage, migrasi, dan sejarah; distribusi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Beastfolk tidak memiliki satu budaya atau satu political allegiance. Lineage, clan, komunitas, dan budaya dapat berbeda.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-006 — ORC

```text
RACE_CANON_ID: RACE-006
NAME: Orc
CLASSIFICATION: Sapient Humanoid — Robust Frontier Lineage
DESCRIPTION: Ras humanoid bertubuh kuat yang secara historis memiliki komunitas di wilayah frontier, padang terbuka, hutan, dan kawasan dengan tekanan survival tinggi. Orc tidak secara Canon dianggap identik dengan evil, barbarism, atau hostility.
ORIGIN: ???
HISTORY: Sejarah migrasi, konflik, dan pembentukan komunitas = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Fisiologi relatif kuat; detail biologis = ???
INNATE CAPABILITIES: Trait fisik spesifik = ???; combat skill dan profession tidak otomatis ditentukan oleh ras.
HABITAT / HISTORICAL DISTRIBUTION: Frontier, open terrain, forest margin, dan wilayah lain sesuai sejarah migrasi; lokasi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Orc memiliki kemungkinan variasi clan, tribe, settlement, faction, dan political affiliation yang berbeda.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-007 — GNOME

```text
RACE_CANON_ID: RACE-007
NAME: Gnome
CLASSIFICATION: Sapient Humanoid — Inventive/Craft Lineage
DESCRIPTION: Ras humanoid berukuran relatif kecil yang secara historis dikenal melalui komunitas pengrajin, eksperimen, engineering, alchemy, mekanisme, dan perdagangan pengetahuan. Keahlian individual tetap membutuhkan training dan skill.
ORIGIN: ???
HISTORY: Sejarah teknologi, komunitas, dan hubungan dengan Dwarf serta ras lain = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Postur relatif kecil; detail biologis tambahan = ???
INNATE CAPABILITIES: Tidak ada universal mastery atas crafting/alchemy/engineering; trait biologis spesifik = ???
HABITAT / HISTORICAL DISTRIBUTION: Settlement industri kecil, pusat kerajinan, kota dagang, atau komunitas khusus sesuai sejarah; lokasi spesifik = ???
CULTURAL VARIATION BOUNDARIES: Komunitas Gnome dapat berbeda dalam teknologi, craft tradition, faction, dan politik.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-008 — DRAGONKIN

```text
RACE_CANON_ID: RACE-008
NAME: Dragonkin
CLASSIFICATION: Sapient Humanoid — Draconic Lineage
DESCRIPTION: Ras sapient humanoid dengan warisan draconic. Dragonkin berbeda dari Dragon sebagai Monster Canon; lineage ini tidak berarti setiap Dragonkin adalah naga atau memiliki kekuatan naga penuh.
ORIGIN: ???
HISTORY: Asal-usul hubungan dengan Dragon dan sejarah komunitas Dragonkin = ???
LIFESPAN / AGING MODEL: ???
BIOLOGICAL TRAITS: Ciri draconic seperti sisik, tanduk, atau karakteristik lain dapat muncul sesuai lineage; detail = ???
INNATE CAPABILITIES: Kemampuan bawaan draconic spesifik = ??? dan tidak boleh diasumsikan setara dengan kemampuan Dragon Monster Canon.
HABITAT / HISTORICAL DISTRIBUTION: Tidak dibatasi pada satu kingdom; distribusi historis dan komunitas utama = ???
CULTURAL VARIATION BOUNDARIES: Dragonkin dapat memiliki budaya dan political allegiance berbeda. Bloodline/lineage tidak otomatis menentukan status sosial atau kekuatan.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

### RACE-009 — DARK ELF

```text
RACE_CANON_ID: RACE-009
NAME: Dark Elf
CLASSIFICATION: Sapient Humanoid — Distinct Elven Lineage/Culture
DESCRIPTION: Ras sapient yang secara Canon memiliki identitas berbeda dari Elf umum dan sejarah komunitas tersendiri. Dark Elf tidak secara otomatis evil, hostile, underground, atau villain.
ORIGIN: ???
HISTORY: Hubungan sejarah dengan Elf, wilayah asal, migrasi, dan konflik masa lalu = ???
LIFESPAN / AGING MODEL: Long-lived tendency; parameter spesifik = ???
BIOLOGICAL TRAITS: Humanoid dengan karakteristik elven yang berbeda; detail pembeda = ???
INNATE CAPABILITIES: Trait biologis atau sensory khusus = ???; magic tidak otomatis dimiliki semua Dark Elf.
HABITAT / HISTORICAL DISTRIBUTION: Habitat historis dan settlement utama = ???
CULTURAL VARIATION BOUNDARIES: Dark Elf memiliki variasi komunitas dan budaya; identitas moral individual tidak ditentukan oleh ras.
CANON_ORIGIN: Admin Canon v1.1 — Race Foundation
STATUS: CANON
```

## 7. Race Relationship Rules

Ras tidak memiliki hubungan universal seperti `ALLY`, `ENEMY`, `FRIEND`, atau `HOSTILE` hanya berdasarkan identity ras.

Hubungan antar-ras ditentukan oleh:

- history,
- migration,
- territory,
- economy,
- faction policy,
- religion/culture bila relevan,
- individual experience,
- reputation,
- events,
- goals,
- dan state yang sah.

## 8. Race vs Subrace / Lineage

Untuk mencegah ledakan jumlah ras Canon:

```text
RACE CANON
↓
POSSIBLE LINEAGE / SUBGROUP / CULTURE
```

Subrace atau lineage hanya menjadi Race Canon terpisah bila Admin secara eksplisit mendaftarkannya.

Khusus Beastfolk, variasi animal lineage tetap berada di bawah RACE-005 sampai ada keputusan Canon berbeda.

Khusus Dragonkin, Dragon Monster Canon tetap merupakan domain `14_MONSTER_ECOSYSTEM.md`; Dragonkin tidak menggantikan Monster Canon.

## 9. Population & Distribution Boundary

Tidak ada persentase ras resmi pada registry ini.

Distribusi ras untuk Kingdom-001, Kingdom-002, dan wilayah berikutnya akan ditentukan setelah Region/Settlement Canon, sejarah, migrasi, dan Population Model dibangun.

Dengan demikian, penetapan 9 ras ini **tidak otomatis berarti** setiap kingdom memiliki proporsi ras tertentu.

## 10. Canonization / Expansion Gate

Ras baru di masa depan harus melewati:

```text
PROPOSAL
↓
CHECK WORLD HISTORY
↓
CHECK GEOGRAPHY
↓
CHECK EXISTING RACE BOUNDARIES
↓
CHECK CULTURE / MIGRATION
↓
CHECK MONSTER BOUNDARY
↓
CHECK CHARACTER / NPC INTEGRATION
↓
ADMIN CANON DECISION
↓
REGISTRY ENTRY
```

Penambahan ras baru tidak boleh dilakukan hanya karena kebutuhan satu NPC atau satu scene.

## 11. No Guessing

Jika Race Canon Registry belum menentukan suatu fakta:

```text
VALUE = ???
```

AI GM tidak boleh mengubah `???` menjadi angka, sejarah, habitat, lifespan, kemampuan, atau distribusi yang dianggap resmi tanpa authority.

## 12. Integration

Race Registry diakses melalui:

`INDEX.md` → `36_RACE_SYSTEM.md` → `races/CANON_REGISTRY.md`

Runtime state dan persistence mengikuti:

`26_CHARACTER_STATE` · `27_NPC_STATE` · `28_MONSTER_STATE` · `30_HISTORY_SYSTEM` · `31_ORIGIN_LOG` · `32_MODULE_ROUTER` · `33_ACTION_RESOLVER` · `34_STATE_VALIDATOR` · `35_SAVE_PIPELINE`.

## 13. Current Status

```text
REGISTRY_STATUS: CANON_ACTIVE
CANON_RACE_COUNT: 9
RACE_CANON_SLOTS: OPEN FOR FUTURE ADMIN EXPANSION
```

## Final Principle

> **Sembilan ras utama Eldoria kini menjadi Canon resmi. Ras membentuk fondasi biologis dan historis dunia, tetapi tidak menjadi determinisme terhadap budaya, moralitas, politik, personality, atau outcome individual.**
