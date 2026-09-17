# Eldoria World

**Eldoria World** adalah World Bible dan persistent-world framework untuk permainan roleplay **Medieval Fantasy** berbasis AI Game Master.

Repository ini dirancang untuk membangun dunia yang hidup, terbuka, konsisten, dinamis, dan memiliki konsekuensi nyata.

## Konsep Utama

> **Dunia yang hidup, Player yang bebas, dan cerita yang lahir dari konsekuensi.**

Eldoria bukan cerita linear yang menunggu Player. Dunia memiliki aturan, kondisi, NPC, masyarakat, peristiwa, dan perubahan yang dapat berlangsung di luar keputusan Player.

Player bebas menentukan siapa karakter mereka dan apa yang ingin mereka capai. Dunia tetap memiliki batas nyata berupa sumber daya, kemampuan, kondisi sosial, politik, ekonomi, lingkungan, risiko, dan konsekuensi.

## Peran

### Player
Mengendalikan keputusan, tindakan, dan intent karakter.

### Admin
Memelihara Repository, Canon, registrasi karakter, validasi, arsitektur, dan perubahan resmi dunia.

### AI GM
Membaca Canon dan State, menjalankan simulasi, mengorkestrasi proses event dan autonomous NPC/faction, menyelesaikan action melalui system yang relevan, menghitung konsekuensi, dan menghasilkan narasi.

### Repository
Berfungsi sebagai **Official Canon + Persistent State Source**.

## Prinsip Dunia

- Medieval Fantasy.
- Dunia luas, terbuka, dan persisten.
- Realistic Adventure + Dark Realistic + Realistic Heroic.
- Tidak ada plot armor khusus untuk Player maupun NPC.
- Tidak ada class, profession, atau main path yang wajib.
- Tujuan Player bebas, tetapi hasil tetap ditentukan oleh kondisi dan aturan dunia.
- Supernatural merupakan bagian umum dari kehidupan dunia, tetapi tidak berarti semua individu dapat menggunakannya.
- Peoples/sentient societies, monsters, dan wildlife dibedakan secara konseptual.
- Makhluk memiliki perilaku, habitat, dan ekosistem yang masuk akal.

## Repository Architecture

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

Struktur akan berkembang secara bertahap. Modul yang belum didefinisikan bukan otomatis menjadi Canon.

## Character Registration

Karakter harus melalui proses registrasi dan validasi Admin sebelum dapat dimainkan.

```text
PLAYER
  ↓
Name + Concept + Background
  ↓
ADMIN VALIDATION
  ↓
Player ID + Character ID
  ↓
Character File
  ↓
players.md
  ↓
READY
  ↓
GAMEPLAY
```

`characters/players.md` adalah registry resmi, bukan gameplay save. Kondisi karakter yang berubah selama permainan disimpan sebagai Current State pada data karakter/state yang sesuai.

## Canon, State, dan History

Eldoria memisahkan tiga konsep utama:

- **Canon:** aturan dan fakta resmi dunia.
- **State:** kondisi dunia/karakter saat ini.
- **History:** catatan kejadian dan perubahan yang menjelaskan bagaimana State terbentuk.

Perubahan penting harus dapat ditelusuri melalui Origin/Source.

## Runtime

Runtime menggunakan prinsip umum:

```text
LOAD → READ STATE → PARSE
→ ROUTE TO ACTION / EVENT / AUTONOMOUS PROCESS
→ VALIDATE → RESOLVE / PROCESS
→ CONSEQUENCES → STATE CHANGE → VALIDATE
→ APPLY → HISTORY → PERSIST → VERIFY → RESPONSE
```

`World Event Processor` mengorkestrasi lifecycle dan processing Event. `NPC/Faction Simulation` mengorkestrasi evaluasi dan proses autonomous NPC/Faction. NPC Behavior/Factions tetap menjadi pemilik decision dan domain masing-masing; Action Model, Resolution Architecture, domain systems, State Validation, Persistence, dan Time & Calendar tetap menjalankan authority masing-masing.

Intent tidak sama dengan hasil. Action dapat berhasil, gagal, diblokir, tertunda, atau terinterupsi. Tidak semua Event harus menjadi Action, dan autonomous world processing tidak berarti setiap NPC harus disimulasikan pada setiap Turn.

## World Foundation

Fondasi awal Eldoria mencakup:

- Identity
- Tone & Atmosphere
- Scale
- Peoples & Creatures
- Technology & Civilization
- Supernatural
- Player Freedom
- Theme

Detail geography, civilization, peoples, politics, supernatural/magic, economy, creatures, factions, dan sistem lainnya akan dikembangkan secara bertahap berdasarkan fondasi tersebut.

## Source of Truth

Untuk struktur, aturan, data karakter, State, dan Canon resmi, Repository adalah sumber utama.

Mulai dari [`INDEX.md`](INDEX.md) untuk navigasi sistem dan modul Eldoria.
