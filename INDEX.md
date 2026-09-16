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
├── characters/
│   ├── players.md
│   └── players/
├── world/
├── systems/
├── state/
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

Core Rules akan menjadi aturan dasar yang berlaku lintas sistem.

**Planned:**

```text
core/CORE_RULES.md
```

File tersebut akan ditambahkan setelah Repository Initialization ini diverifikasi.

## 7. Character Registry

`characters/players.md` akan menjadi **Official Player/Character Registry**.

Registry menyimpan informasi minimal untuk identifikasi dan boot karakter. Registry bukan gameplay save.

Detail karakter disimpan pada file karakter masing-masing di:

```text
characters/players/
```

## 8. State & History

State dan History dipisahkan.

- **State** = snapshot kondisi saat ini.
- **Starting State** = kondisi resmi saat karakter mulai gameplay.
- **Current State** = kondisi aktual terkini.
- **History** = catatan kejadian/perubahan yang menjelaskan bagaimana State terbentuk.

Perubahan penting harus dapat ditelusuri melalui Origin/Source dan History.

## 9. Runtime Direction

Runtime Eldoria mengikuti alur konseptual:

```text
BOOT / LOAD CONTEXT
→ READ CURRENT STATE
→ RECEIVE PLAYER MESSAGE
→ PARSE
→ IDENTIFY ACTION / INTENT
→ VALIDATE
→ RESOLVE
→ CALCULATE CONSEQUENCES
→ GENERATE STATE CHANGES
→ VALIDATE STATE CHANGES
→ APPLY STATE
→ CREATE HISTORY
→ PERSIST
→ GENERATE RESPONSE
→ END TURN
```

Satu Player Message diperlakukan sebagai satu Turn. Satu Turn dapat berisi nol atau beberapa action yang diproses secara berurutan.

## 10. World Foundation

Fondasi dunia Eldoria yang telah disepakati:

- **Identity:** Medieval Fantasy yang luas, terbuka, persisten, imersif, dan realistis.
- **Tone:** Realistic Adventure + Dark Realistic + Realistic Heroic.
- **Scale:** Dunia sangat luas, multi-wilayah/multi-benua, terungkap secara bertahap.
- **Peoples & Creatures:** Manusia tidak otomatis menjadi mayoritas; masyarakat makhluk berakal dapat memiliki peradaban sendiri; hubungan antarkelompok beragam; Orc, Goblin, dan kelompok sejenis diklasifikasikan sebagai monster; makhluk memiliki perilaku dan ekosistem yang masuk akal.
- **Technology:** Medieval Fantasy fleksibel dan dapat berbeda menurut wilayah.
- **Supernatural:** Umum dan diakui sebagai bagian dari kehidupan dunia, tetapi tidak berarti semua individu dapat menggunakan kekuatan supernatural.
- **Player Freedom:** Open-world tanpa class/profession/main path wajib. Player dapat mengejar tujuan besar, termasuk membangun usaha, organisasi, wilayah, atau kerajaan, selama dunia memungkinkan dan konsekuensinya dijalani.
- **Plot Armor:** Tidak ada perlindungan naratif khusus untuk Player maupun NPC.
- **Theme:** **Dunia yang hidup, Player yang bebas, dan cerita yang lahir dari konsekuensi.**

## 11. Canon Development Order

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

Urutan ini adalah arah pengembangan, bukan izin untuk menganggap seluruh bagian yang belum ditulis sebagai Canon.

## 12. Authority Boundary

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

## 13. Integrity Principles

- Intent ≠ Result.
- Failure adalah hasil yang valid.
- World tidak menyesuaikan diri agar Player selalu berhasil.
- Narrative adalah output simulasi, bukan sumber State.
- State Change harus konsisten dengan State sebelumnya dan memiliki asal yang dapat ditelusuri.
- History tidak dihapus atau ditimpa secara diam-diam.
- Canon yang belum didefinisikan tidak boleh diada-adakan sebagai fakta.
- Autonomous NPC, faction, event, dan world changes harus memiliki dasar aturan/data dan dapat ditelusuri.
