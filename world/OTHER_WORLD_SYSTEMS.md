# Eldoria World — Other World Systems v0.1

> **Module:** Other World Systems  
> **Version:** v0.1  
> **Authority:** Official Canon / Architecture Framework

## 1. Purpose

Modul ini menetapkan kerangka arsitektur untuk **world systems** Eldoria yang belum memiliki modul khusus dalam World Canon v0.1.

Tujuannya adalah memastikan sistem baru dapat ditambahkan secara bertahap tanpa tumpang tindih, tanpa menciptakan aturan universal secara diam-diam, dan tanpa mengubah authority boundary Repository.

Modul ini adalah **architecture framework**, bukan daftar sistem final dan bukan tempat untuk menumpuk semua mekanik dunia yang belum dirancang.

## 2. Current Canon Context

World Canon yang telah ditetapkan sebelum modul ini:

```text
WORLD FOUNDATION
GEOGRAPHY
CIVILIZATION
PEOPLES / RACES
POLITICS
SUPERNATURAL / MAGIC
ECONOMY
CREATURES / ECOLOGY
FACTIONS
```

Sistem baru harus terlebih dahulu diperiksa apakah sebenarnya merupakan perluasan salah satu modul yang sudah ada. Modul baru hanya dibuat jika memiliki domain, data, rules, atau lifecycle yang cukup berbeda untuk membutuhkan boundary tersendiri.

## 3. Core Principles

- Repository tetap menjadi Official Canon + Persistent State Source.
- Setiap world system harus memiliki domain dan boundary yang jelas.
- Tidak ada world system yang otomatis berlaku universal tanpa Canon yang menetapkannya.
- Sistem baru tidak boleh menduplikasi authority modul lain.
- Sistem baru harus kompatibel dengan Core Rules, Runtime, Character Data Model, dan State & History Model.
- Unknown / Undefined tetap dipertahankan ketika detail belum ditetapkan.
- Framework tidak boleh dianggap sebagai mekanik final.
- Narrative tidak boleh menjadi sumber aturan sistem.
- Intent ≠ Result ≠ State Change.
- Autonomous world processing tetap memerlukan dasar yang valid.
- Persistent changes harus memiliki provenance dan mengikuti State/History.
- Sistem yang membutuhkan formula tidak boleh mengarang formula sebelum formula tersebut ditetapkan sebagai Canon.

## 4. System Classification

World System dapat berupa mekanisme yang mengatur aspek dunia tertentu, misalnya secara konseptual:

- waktu dan kalender;
- hukum atau legal procedures;
- religion / belief systems;
- social customs;
- quests / objectives;
- events;
- NPC behavior;
- relationships;
- reputation;
- combat;
- health / injury;
- travel;
- crafting;
- knowledge / information;
- progression;
- property / settlement management;
- diplomacy;
- war;
- atau domain lain yang memang membutuhkan aturan tersendiri.

Daftar tersebut **bukan daftar sistem Canon final**. Penyebutan kategori tidak menetapkan mekanik, formula, nilai, atau keberadaan sistem tersebut.

## 5. System Boundary

Sebelum membuat modul baru, tentukan:

```text
SYSTEM
├── Domain
├── Purpose
├── Inputs
├── Rules
├── Outputs
├── State affected
├── History affected
├── Runtime integration
├── Dependencies
└── Canon boundary
```

Sebuah sistem tidak boleh mengambil alih domain modul lain tanpa alasan arsitektural yang eksplisit.

Contoh boundary konseptual:

```text
ECONOMY
→ transaksi, produksi, nilai, sumber daya ekonomi

POLITICS
→ authority, governance, jurisdiction, political relations

FACTIONS
→ kelompok terorganisasi/informal, membership, internal/external relations

CREATURES / ECOLOGY
→ creature, habitat, population, ecological processes

OTHER SYSTEM
→ hanya domain yang belum memiliki owner Canon yang tepat
```

## 6. System Ownership

Setiap rule atau data penting harus memiliki **canonical owner** yang dapat diidentifikasi.

Prinsip:

```text
ONE CANONICAL OWNER
        ↓
CLEAR DEPENDENCIES
        ↓
NO SILENT DUPLICATION
```

Jika suatu aturan membutuhkan beberapa domain, modul yang menggunakan aturan tersebut harus merujuk kepada owner masing-masing, bukan menyalin definisi yang dapat menjadi berbeda.

## 7. Dependency Model

Sistem baru dapat bergantung pada satu atau beberapa modul sebelumnya.

Contoh konseptual:

```text
SYSTEM X
├── Geography
├── Civilization
├── Politics
└── Economy
```

Dependency berarti sistem membaca atau menggunakan fakta/rules dari modul tersebut. Dependency tidak memberikan hak untuk mengubah Canon modul sumber secara diam-diam.

Jika dependency belum tersedia atau undefined, sistem tidak boleh mengisi kekosongan dengan asumsi Canon.

## 8. Runtime Integration

Setiap world system yang dapat memproses action atau event harus kompatibel dengan Runtime / Turn Model.

Secara konseptual:

```text
PLAYER / NPC / WORLD INPUT
↓
PARSE
↓
VALIDATE
↓
SYSTEM-SPECIFIC RESOLUTION
↓
CONSEQUENCES
↓
STATE CHANGE(S)
↓
VALIDATE
↓
HISTORY
↓
PERSIST
↓
VERIFY
```

Sistem tidak boleh melewati validation hanya karena hasilnya dianggap diperlukan oleh narrative.

Jika sistem belum mendefinisikan resolution mechanism, AI GM tidak boleh menciptakan formula atau hasil otomatis.

## 9. State Integration

World system dapat menghasilkan atau memengaruhi State hanya jika perubahan tersebut memang menjadi bagian dari domainnya.

Contoh konseptual:

```text
SYSTEM PROCESS
↓
VALIDATED RESULT
↓
STATE CHANGE
↓
CURRENT STATE
```

State Change harus tetap mengikuti `state/STATE_AND_HISTORY_MODEL.md`.

Starting State tidak boleh ditimpa oleh perubahan runtime.

## 10. History & Provenance

Perubahan penting yang dihasilkan world system harus dapat ditelusuri.

```text
SYSTEM RESULT
↓
ORIGIN
↓
SOURCE
↓
STATE CHANGE
↓
HISTORY
```

History bukan tempat untuk menciptakan rule baru. History mencatat apa yang terjadi dan bagaimana perubahan tersebut terjadi.

## 11. Autonomous Systems

World systems dapat menjalankan proses tanpa keputusan Player apabila sistem tersebut memang dirancang untuk simulasi autonomous.

Contoh konseptual:

```text
NPC PROCESS
FACTION PROCESS
ENVIRONMENTAL PROCESS
ECONOMIC PROCESS
POLITICAL PROCESS
ECOLOGICAL PROCESS
EVENT PROCESS
OTHER VALID SYSTEM PROCESS
```

Autonomy tidak berarti randomness tanpa batas. Setiap perubahan harus memiliki dasar dari Canon, State, aturan sistem, atau proses valid lainnya.

## 12. Interaction Between Systems

World systems dapat saling memengaruhi.

Model umum:

```text
SYSTEM A
   ↓
VALIDATED OUTPUT
   ↓
SYSTEM B
   ↓
CONSEQUENCES
   ↓
STATE / HISTORY
```

Interaksi tidak boleh membuat circular authority yang tidak jelas.

Jika dua sistem menghasilkan perubahan yang saling bergantung, perubahan harus divalidasi sebagai satu hasil terintegrasi ketika diperlukan untuk menjaga consistency.

## 13. Knowledge Boundary

Setiap sistem harus membedakan:

```text
SYSTEM CANON
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
≠
RUMOR / UNCERTAIN INFORMATION
```

Character tidak otomatis mengetahui seluruh aturan sistem, statistik, hidden state, atau informasi dunia hanya karena informasi tersebut tersedia bagi AI GM atau Player.

## 14. Time Dependency

World system dapat bergantung pada waktu jika domainnya memang membutuhkan waktu.

Namun:

- tidak ada kalender universal yang ditetapkan oleh modul ini;
- tidak ada durasi universal yang ditetapkan oleh modul ini;
- sistem waktu khusus harus menjadi Canon tersendiri jika dibutuhkan;
- sistem tidak boleh menciptakan World Time hanya untuk melengkapi simulasi.

Jika sistem waktu belum tersedia, status waktu yang diperlukan tetap Unknown / Undefined sesuai aturan Runtime dan State.

## 15. Formula & Quantitative Mechanics

World Systems v0.1 tidak menetapkan formula universal.

Formula hanya dapat menjadi Canon jika:

```text
DEFINE
↓
DOCUMENT
↓
VALIDATE
↓
INTEGRATE
↓
VERIFY
```

Tidak diperbolehkan menyisipkan angka default, multiplier, threshold, probability, stat scaling, cooldown, speed, atau nilai numerik lain sebagai "fallback Canon" tanpa definisi resmi.

## 16. System Data Model

Setiap sistem khusus dapat menggunakan struktur data yang sesuai domainnya.

Model konseptual minimum:

```text
WORLD SYSTEM
├── System ID
├── Name
├── Version
├── Domain
├── Purpose
├── Rules / Constraints
├── Inputs
├── Outputs
├── Dependencies
├── State References
├── History References
├── Runtime Integration
├── Knowledge Boundary
├── Canon Boundary
└── Metadata
```

Model ini adalah template arsitektur, bukan kewajiban bahwa semua field harus menjadi field runtime literal.

## 17. Module Creation Criteria

Sebuah sistem baru layak dibuat sebagai modul tersendiri apabila minimal memiliki satu atau lebih kebutuhan berikut:

- domain yang berbeda secara jelas;
- rules khusus yang tidak cocok ditempatkan di modul lain;
- data model khusus;
- lifecycle atau state khusus;
- runtime resolution khusus;
- dependency yang perlu dikelola secara eksplisit;
- kebutuhan audit/integrity tersendiri.

Jika kebutuhan tersebut belum ada, lebih baik memperluas modul yang sudah menjadi canonical owner daripada membuat modul baru yang tumpang tindih.

## 18. Progressive Development

Pengembangan Other World Systems dilakukan bertahap:

```text
ARCHITECTURE FRAMEWORK
↓
IDENTIFY SYSTEM DOMAIN
↓
AUDIT EXISTING MODULES
↓
DEFINE CANONICAL OWNER
↓
CREATE SYSTEM MODULE
↓
DEFINE RULES / DATA MODEL
↓
INTEGRATE RUNTIME / STATE / HISTORY
↓
VALIDATE DEPENDENCIES
↓
VERIFY REPOSITORY
```

Tidak semua sistem harus dibuat sekaligus.

## 19. Canon Boundary

Other World Systems v0.1 **tidak** menetapkan secara universal:

- kalender atau sistem waktu final;
- combat system;
- health/injury formula;
- travel speed formula;
- crafting formula;
- progression system;
- quest generation rules;
- event generation formula;
- NPC personality/behavior formula;
- relationship/reputation score;
- religion atau daftar agama;
- legal code universal;
- settlement management formula;
- diplomacy/war formula;
- knowledge/statistics system;
- class/profession restriction;
- level/tier system;
- probability table;
- damage formula;
- resource regeneration formula;
- atau mekanik sistem spesifik lain yang belum ditetapkan.

Kategori yang disebut di atas hanya menunjukkan area yang **mungkin** membutuhkan modul tersendiri.

## 20. Integrity Rules

1. Jangan membuat modul baru jika domainnya sudah memiliki canonical owner tanpa alasan eksplisit.
2. Jangan menduplikasi rule Canon dari modul lain secara diam-diam.
3. Jangan mengubah authority modul lain melalui dependency.
4. Jangan mengisi Undefined / Unknown dengan asumsi.
5. Jangan membuat formula atau angka default sebagai fallback Canon.
6. Jangan menjadikan narrative sebagai sumber rule atau State.
7. Semua system-specific resolution harus kompatibel dengan Runtime.
8. Persistent State Change harus divalidasi dan memiliki provenance yang sesuai.
9. Perubahan penting harus dapat ditelusuri melalui History.
10. Autonomous processing harus memiliki dasar yang valid.
11. Inter-system changes yang saling bergantung harus divalidasi sebagai hasil terintegrasi bila diperlukan.
12. Character Knowledge dan Player Knowledge tidak boleh disamakan dengan System Canon.
13. Konflik antar-system harus diperlakukan sebagai masalah integritas dan tidak diselesaikan diam-diam.
14. Ekstensi sistem tidak boleh mengubah Core Canon secara implisit.
15. Setiap perubahan Canon harus dilakukan secara eksplisit melalui Repository.

## 21. Dependencies & Integration

Modul ini bergantung pada:

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
```

Modul khusus berikutnya harus menyatakan dependency aktualnya sendiri dan tidak otomatis bergantung pada seluruh Repository.

## 22. Future Architecture

Setelah framework ini ditetapkan, pengembangan berikutnya dapat memilih system berdasarkan dependency dan kebutuhan dunia, bukan sekadar menambah daftar modul.

Urutan pemilihan dapat mengikuti prinsip:

```text
IDENTIFY WORLD NEED
↓
CHECK EXISTING CANON OWNER
↓
AUDIT OVERLAP
↓
DEFINE NEW SYSTEM IF NECESSARY
↓
INTEGRATE
↓
VERIFY
```

Framework ini tidak menetapkan urutan wajib untuk semua system berikutnya.
