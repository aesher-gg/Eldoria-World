# Eldoria World — INDEX

> **Repository:** `aesher-gg/Eldoria-World`  
> **Version:** Architecture / Repository Initialization v0.1  
> **Authority:** Official Canon + Persistent State Source

## 1. Purpose

`INDEX.md` adalah entry point utama bagi AI GM untuk memahami struktur Repository Eldoria-World dan menentukan sumber yang relevan sebelum menjalankan gameplay.

INDEX bukan database dunia, bukan character save, dan bukan pengganti modul Canon.

## 2. Repository Authority

Repository adalah **Official Canon + Persistent State Source**.

- Canon resmi harus berasal dari Repository.
- Current State adalah kondisi terkini yang tersimpan.
- History menjelaskan perubahan dan asal-usul State.
- Percakapan tidak menjadi sumber Canon permanen dengan sendirinya.

## 3. Architecture

Eldoria menggunakan enam lapisan konseptual:

```text
CANON
REGISTRY
STATE
RUNTIME
INTERACTION
PERSISTENCE
```

Pemisahan ini menjaga agar aturan dunia, registrasi karakter, kondisi terkini, simulasi, interaksi, dan penyimpanan tidak tercampur.

## 4. Core Navigation

Struktur utama Repository dirancang untuk berkembang secara modular:

```text
Eldoria-World/
├── INDEX.md
├── README.md
├── core/
│   ├── CORE_RULES.md
│   └── RUNTIME_TURN_MODEL.md
├── characters/
│   ├── players.md
│   ├── CHARACTER_DATA_MODEL.md
│   └── players/
├── world/
│   ├── WORLD_FOUNDATION.md
│   ├── GEOGRAPHY.md
│   ├── CIVILIZATION.md
│   └── PEOPLES_RACES.md
├── systems/
├── state/
│   └── STATE_AND_HISTORY_MODEL.md
└── history/
```

Directory atau modul baru hanya ditambahkan ketika memang telah didefinisikan sebagai bagian dari Canon Eldoria.

## 5. Loading Principle

AI GM harus memuat sumber sesuai kebutuhan, bukan menganggap seluruh Repository sebagai satu dokumen.

Prinsip umum:

```text
INDEX
  ↓
IDENTIFY RELEVANT MODULES / DATA
  ↓
FETCH SOURCE
  ↓
VALIDATE CONTEXT
  ↓
RUN SIMULATION
```

Jika suatu fakta belum tersedia dalam Canon atau State yang relevan, AI GM tidak boleh mengubah ketidaktahuan menjadi fakta Canon.

## 6. Core Rules

`core/CORE_RULES.md` adalah aturan dasar yang berlaku lintas sistem.

## 7. Runtime / Turn Model

`core/RUNTIME_TURN_MODEL.md` mendefinisikan pipeline runtime dan prinsip satu Player Message = satu Turn, termasuk parsing, validation, resolution, consequences, State Change, History, persistence, dan response.

## 8. Character Registry

`characters/players.md` adalah **Official Player/Character Registry**.

Registry menyimpan informasi minimal untuk identifikasi dan boot karakter. Registry bukan gameplay save.

Detail karakter disimpan pada file karakter masing-masing di:

```text
characters/players/
```

## 9. Character Data Model

`characters/CHARACTER_DATA_MODEL.md` mendefinisikan struktur data karakter, termasuk Identity, Background, Origin, Physical Profile, Attributes, Abilities, Equipment, Possessions, Relationships, Starting State, Current State, Conditions, History Reference, dan Metadata.

Modul ini mendefinisikan struktur, bukan mekanik gameplay rinci.

## 10. State & History

`state/STATE_AND_HISTORY_MODEL.md` adalah fondasi resmi untuk persistent State dan History.

- **State** = snapshot kondisi saat ini.
- **Starting State** = kondisi resmi saat karakter mulai gameplay.
- **Current State** = kondisi aktual terkini.
- **State Change** = perubahan tervalidasi dari satu State ke State berikutnya.
- **History** = catatan kejadian/perubahan yang menjelaskan bagaimana State terbentuk.
- **Origin/Source** = provenance yang memungkinkan perubahan penting ditelusuri.

State dan History dipisahkan tetapi harus dapat direkonsiliasi. History tidak boleh dihapus/ditimpa secara diam-diam; koreksi harus tetap dapat diaudit.

## 11. World Foundation

`world/WORLD_FOUNDATION.md` adalah **Official Canon** untuk fondasi identitas dan arah dunia Eldoria.

Fondasi yang ditetapkan:

- **Identity:** Medieval Fantasy yang luas, terbuka, persisten, imersif, dan realistis.
- **Tone:** Realistic Adventure + Dark Realistic + Realistic Heroic.
- **Scale:** Dunia sangat luas, multi-wilayah/multi-benua, terungkap secara bertahap.
- **Peoples & Creatures:** Manusia tidak otomatis menjadi mayoritas; masyarakat makhluk berakal dapat memiliki peradaban sendiri; hubungan antarkelompok beragam; Orc, Goblin, dan kelompok sejenis diklasifikasikan sebagai monster; makhluk harus dipahami sebagai bagian dari ekosistem.
- **Technology:** Medieval Fantasy fleksibel dan dapat berbeda menurut wilayah.
- **Supernatural:** Umum dan diakui sebagai bagian dari kehidupan dunia, tetapi tidak berarti semua individu dapat menggunakan kekuatan supernatural.
- **Player Freedom:** Open-world tanpa class/profession/main path wajib. Player dapat mengejar tujuan besar, termasuk membangun usaha, organisasi, wilayah, atau kerajaan, selama dunia memungkinkan dan konsekuensinya dijalani.
- **Plot Armor:** Tidak ada perlindungan naratif khusus untuk Player maupun NPC.
- **Theme:** **Dunia yang hidup, Player yang bebas, dan cerita yang lahir dari konsekuensi.**

World Foundation tidak menetapkan lore rinci yang belum dibuat. Detail dunia berikutnya harus ditambahkan melalui modul Canon yang relevan.

## 12. Geography

`world/GEOGRAPHY.md` adalah **Official Canon** untuk kerangka geografis dan prinsip spasial Eldoria.

Modul ini menetapkan struktur geografis bertingkat, prinsip regional diversity, terrain, water systems, climate/environment, natural resources, travel/connectivity, settlements, natural barriers, spatial relationships, mapping/knowledge boundaries, dan progressive revelation.

Geography v0.1 belum menetapkan nama atau jumlah benua, wilayah, kota, desa, lokasi, peta final, batas politik, distribusi sumber daya spesifik, atau durasi perjalanan universal.

## 13. Civilization

`world/CIVILIZATION.md` adalah **Official Canon** untuk kerangka bagaimana masyarakat dan peradaban Eldoria terbentuk, berkembang, berfungsi, dan berubah.

Civilization v0.1 menetapkan framework untuk settlement development, urbanization, rural/urban communities, social organization, institutions, governance reference, technology/material culture, infrastructure, culture/daily life, knowledge/education, economic interface, hubungan antar-peoples, civilization change, world autonomy, data model, dan integrasi State/History.

Modul ini **tidak** menetapkan daftar kingdom, negara, kota, desa, peoples/races, budaya spesifik, sistem politik, mata uang, teknologi universal, atau lore civilization tertentu. Detail yang belum ditetapkan tetap Unknown / Undefined.

## 14. Peoples / Races

`world/PEOPLES_RACES.md` adalah **Official Canon** untuk kerangka representasi Peoples / Races dalam Eldoria.

Peoples / Races v0.1 menetapkan framework untuk klasifikasi konseptual, hubungan People/Race dengan individu, population dan community, internal diversity, biology/physiology, environmental adaptation, culture/identity, language/communication, social organization, demography, migration/diaspora, inter-peoples relations, hubungan dengan Civilization, supernatural characteristics, character integration, knowledge boundaries, world autonomy, data model, dan integrasi State/History.

Modul ini **tidak** menetapkan daftar final race/people, statistik biologis universal, lifespan universal, kemampuan rasial universal, daftar bahasa, budaya spesifik, wilayah asal spesifik, jumlah populasi, hubungan politik spesifik, sistem monster lengkap, atau magic mechanics. Detail yang belum ditetapkan tetap Unknown / Undefined.

Ketetapan World Foundation bahwa **Orc, Goblin, dan kelompok sejenis diklasifikasikan sebagai monster** tetap berlaku dan tidak diubah oleh modul ini.

## 15. Canon Development Order

World lore tidak dibuat sebagai daftar besar sekaligus. Fondasi menjadi dasar untuk pengembangan bertahap:

```text
WORLD FOUNDATION
↓
GEOGRAPHY
↓
CIVILIZATION
↓
PEOPLES / RACES
↓
POLITICS
↓
SUPERNATURAL / MAGIC
↓
ECONOMY
↓
CREATURES / ECOLOGY
↓
FACTIONS
↓
OTHER WORLD SYSTEMS
```

Pada tahap saat ini, **Peoples / Races v0.1 telah ditetapkan** sebagai framework Canon. Urutan berikutnya adalah pengembangan Politics v0.1.

## 16. Authority Boundary

```text
ADMIN
└── Repository / Canon

AI GM
└── Simulation / Resolution / NPC / World / Events

PLAYER
└── Character decisions / intent
```

Player memiliki kebebasan menentukan keputusan karakter, tetapi tidak menentukan hasil dunia atau keputusan NPC.

AI GM menjalankan simulasi berdasarkan Canon dan State, tetapi tidak mengubah Player menjadi pemenang secara otomatis.

## 17. Integrity Principles

- Intent ≠ Result.
- Failure adalah hasil yang valid.
- World tidak menyesuaikan diri agar Player selalu berhasil.
- Narrative adalah output simulasi, bukan sumber State.
- State Change harus konsisten dengan State sebelumnya dan memiliki asal yang dapat ditelusuri.
- History tidak dihapus atau ditimpa secara diam-diam.
- Canon yang belum didefinisikan tidak boleh diada-adakan sebagai fakta.
- Autonomous NPC, faction, event, dan world changes harus memiliki dasar aturan/data dan dapat ditelusuri.
- Civilization harus tetap diperlakukan sebagai framework Canon sampai detail spesifik ditetapkan secara eksplisit.
- Peoples / Races harus tetap diperlakukan sebagai framework Canon sampai detail spesifik ditetapkan secara eksplisit.
- Identitas People / Race tidak boleh digunakan untuk menentukan perilaku individual tanpa dasar Canon atau data karakter yang relevan.
