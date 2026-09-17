# Eldoria World — Core Rules v0.1

> **Module:** Core Rules  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Core Rules mendefinisikan prinsip dasar yang berlaku lintas dunia dan gameplay Eldoria. Modul ini menjadi fondasi bagi Runtime, State, Character, World, dan sistem lain.

Core Rules tidak mendefinisikan daftar kingdom, race, monster, faction, magic, atau lore rinci. Detail tersebut harus dibuat dalam modul Canon yang sesuai.

## 2. Repository Authority

Repository adalah **Official Canon + Persistent State Source**.

- Canon resmi berasal dari Repository.
- Current State adalah kondisi terkini yang tersimpan.
- History menjelaskan kejadian dan perubahan yang membentuk State.
- Percakapan tidak otomatis menjadi Canon permanen.
- AI GM tidak boleh mengubah ketidaktahuan menjadi fakta Canon.

## 3. World Independence

Eldoria adalah dunia yang berjalan dengan aturan dan kondisi internalnya sendiri.

Dunia tidak menyesuaikan diri agar Player berhasil.

NPC, faction, masyarakat, lingkungan, ekonomi, dan event dapat bertindak atau berubah berdasarkan kondisi dunia tanpa harus menunggu keputusan Player.

Perubahan tersebut harus tetap memiliki dasar Canon, State, aturan sistem, atau kejadian yang valid.

## 4. Player Agency

Player mengendalikan keputusan dan intent karakter.

Player tidak secara otomatis mengendalikan:

- hasil action;
- keputusan NPC;
- kondisi dunia;
- keberhasilan suatu rencana;
- konsekuensi action.

Prinsip:

> **Kebebasan tujuan tidak sama dengan kebebasan dari konsekuensi.**

Tidak ada class, profession, atau main path yang wajib secara global kecuali sistem atau kondisi dunia tertentu secara sah memberlakukan batasan.

## 5. Intent ≠ Result

Pernyataan Player mengenai apa yang ingin dilakukan adalah **intent**, bukan hasil yang sudah terjadi.

```text
PLAYER INTENT
↓
VALIDATION
↓
RESOLUTION
↓
RESULT
↓
CONSEQUENCES
```

AI GM tidak boleh menganggap tujuan Player berhasil hanya karena Player menyatakannya.

## 6. Fair Simulation

Action dapat:

- berhasil;
- berhasil sebagian;
- gagal;
- diblokir;
- tertunda;
- terinterupsi;
- menghasilkan konsekuensi tidak terduga.

Failure adalah hasil simulasi yang sah.

AI GM tidak boleh memberikan plot armor kepada Player maupun NPC. Sebaliknya, AI GM juga tidak boleh menciptakan kegagalan arbitrer tanpa dasar kondisi, aturan, atau resolusi yang relevan.

## 7. Character Control Boundary

AI GM tidak boleh secara sepihak menetapkan keputusan, keyakinan, niat, atau tindakan penting karakter Player yang belum diberikan atau dibenarkan oleh Player.

AI GM boleh menyimulasikan keadaan eksternal yang memengaruhi karakter, tetapi respons internal dan keputusan karakter tetap berada pada Player kecuali ada aturan Canon yang secara eksplisit memengaruhinya.

## 8. Canon, State, History

Eldoria memisahkan:

### Canon
Aturan dan fakta resmi tentang dunia.

### State
Snapshot kondisi dunia atau karakter pada suatu waktu.

### History
Catatan kejadian dan perubahan yang menjelaskan bagaimana State terbentuk.

Contoh:

```text
Canon: Sebuah kota memiliki pelabuhan.
State: Pelabuhan sedang ditutup.
History: Pelabuhan ditutup setelah suatu kejadian.
```

Ketiganya tidak boleh diperlakukan sebagai data yang sama.

## 9. Starting State vs Current State

**Starting State** adalah kondisi resmi karakter ketika memasuki gameplay.

**Current State** adalah kondisi karakter yang berlaku sekarang.

Starting State tidak boleh ditimpa oleh perkembangan gameplay.

Current State menjadi dasar untuk Turn berikutnya.

## 10. State Changes

State Change hanya boleh diterapkan setelah:

1. action atau event diidentifikasi;
2. kondisi dan aturan relevan divalidasi;
3. resolution ditentukan;
4. consequence dihitung;
5. perubahan diperiksa terhadap State sebelumnya;
6. Origin/Source tersedia untuk perubahan yang memerlukannya.

Konseptual bentuk perubahan:

```text
State Change
├── Change ID
├── Target
├── Field
├── Previous Value
├── New Value
├── Origin
├── Source
└── World Time
```

Tidak semua Player Message menghasilkan State Change.

## 11. History Integrity

History harus dapat ditelusuri dan tidak boleh dihapus atau ditimpa secara diam-diam untuk menghilangkan kejadian masa lalu.

Jika terjadi koreksi:

```text
Original Record
↓
Correction Record
```

Current State dapat dikoreksi, tetapi koreksi penting harus tetap dapat diaudit.

## 12. Runtime Turn

Satu Player Message diperlakukan sebagai satu Turn.

Satu Turn dapat berisi nol atau beberapa action.

Jika terdapat beberapa action yang saling bergantung, action diproses secara berurutan dan hasil action sebelumnya menjadi kondisi untuk action berikutnya.

Action dapat gagal atau terinterupsi sebelum action berikutnya dijalankan.

Tidak ada durasi Turn universal yang ditetapkan dalam Core Rules v0.1. Durasi action akan ditentukan oleh sistem atau konteks yang relevan ketika sistem tersebut dibuat.

## 13. Runtime Pipeline

Alur konseptual minimum:

```text
1. BOOT / LOAD CONTEXT
2. READ CURRENT STATE
3. RECEIVE PLAYER MESSAGE / WORLD PROCESS
4. PARSE / IDENTIFY PROCESS
5. ROUTE TO ACTION / EVENT / AUTONOMOUS ORCHESTRATION
6. VALIDATE RELEVANT PROCESS / ACTION
7. RESOLVE OR PROCESS EVENT
8. CALCULATE CONSEQUENCES
9. GENERATE STATE CHANGES
10. VALIDATE STATE CHANGES
11. APPLY STATE
12. CREATE HISTORY
13. PERSIST
14. VERIFY
15. GENERATE RESPONSE / NEXT PROCESS
16. END TURN / PROCESS
```

Untuk Event atau autonomous process, tidak setiap tahap Action berlaku secara identik. `WORLD_EVENT_PROCESSOR` dan `NPC_FACTION_SIMULATION` mengorkestrasi jalur yang relevan sebelum Action/Resolution/domain processing bila diperlukan.

Narrative adalah hasil dari proses tersebut, bukan sumber kebenaran State.

## 14. Validation

Validasi dilakukan secara berlapis sesuai kebutuhan sistem:

```text
CHARACTER VALIDATION
↓
STATE VALIDATION
↓
ACTION / PROCESS VALIDATION
↓
STATE CHANGE VALIDATION
↓
PERSISTENCE VALIDATION
```

Validasi bertujuan menjaga integritas simulasi dan konsistensi data.

## 15. Knowledge Boundaries

Sistem harus membedakan setidaknya:

- **Canon Fact** — fakta resmi yang tersedia dalam Repository.
- **Character Knowledge** — hal yang diketahui karakter.
- **Player Knowledge** — informasi yang diketahui Player di luar pengetahuan karakter.
- **Uncertain Information** — rumor, dugaan, informasi tidak terverifikasi, atau hal yang belum dipastikan.

Player Knowledge tidak otomatis menjadi Character Knowledge.

Uncertain Information tidak otomatis menjadi Canon Fact.

## 16. World Constraints

Player dapat mengejar tujuan yang sangat luas, termasuk membangun usaha, organisasi, wilayah, atau kerajaan.

Namun pencapaian tujuan tetap tunduk pada kondisi dunia, seperti:

- kemampuan karakter;
- sumber daya;
- waktu;
- lokasi;
- pengetahuan;
- hubungan;
- hukum dan politik;
- ekonomi;
- lingkungan;
- tindakan pihak lain;
- risiko dan konsekuensi.

Core Rules tidak menetapkan angka atau formula universal untuk faktor-faktor tersebut.

## 17. Realism & Consequences

Realistic Fantasy berarti hasil ditentukan oleh kondisi dan aturan dunia, bukan oleh kebutuhan naratif untuk membuat Player menang atau kalah.

Konsekuensi dapat bersifat:

- langsung atau tertunda;
- pribadi atau sosial;
- lokal atau lebih luas;
- positif, negatif, atau campuran.

Konsekuensi tidak boleh dibuat semata-mata untuk menghukum Player.

## 18. Supernatural Boundary

Supernatural adalah bagian umum dari kehidupan Eldoria, sesuai World Foundation.

Namun Core Rules tidak menganggap bahwa setiap karakter dapat menggunakan, memahami, atau mengakses supernatural.

Aturan penggunaan, batasan, sumber, risiko, dan mekanisme supernatural harus didefinisikan dalam sistem Canon tersendiri.

## 19. Unknown / Undefined Canon

Jika suatu aturan, fakta, angka, atau mekanisme belum didefinisikan dalam Canon yang relevan, AI GM tidak boleh menganggapnya sebagai fakta resmi hanya untuk menyelesaikan action.

Status yang belum ditentukan harus tetap diperlakukan sebagai **Unknown / Undefined** sampai Admin menetapkannya atau sistem yang relevan menyediakan mekanisme yang sah.

## 20. Persistence Integrity

State yang telah dinyatakan berubah harus benar-benar dipersist sesuai mekanisme Repository.

AI GM tidak boleh mengklaim perubahan telah tersimpan jika persistence belum berhasil diverifikasi.

Setelah perubahan penting diterapkan, State dan History harus tetap konsisten.

## 21. Canon Development Boundary

Core Rules v0.1 sengaja bersifat fundamental dan tidak memuat lore rinci.

Pengembangan arsitektur dan domain dilakukan secara modular:

```text
CORE RULES
↓
CHARACTER MODEL
↓
STATE / HISTORY MODEL
↓
RUNTIME MODEL
↓
ACTION MODEL
↓
RESOLUTION ARCHITECTURE
↓
WORLD EVENT PROCESSOR
↓
NPC / FACTION SIMULATION
↓
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
SYSTEMS
↓
STATE VALIDATION
↓
PERSISTENCE
```

Urutan di atas adalah dependency/orchestration guide, bukan urutan wajib implementasi atau runtime execution tunggal. `STATE VALIDATION` dan `PERSISTENCE` tetap merupakan canonical integrity/save boundaries yang digunakan setelah proposed State Changes dari jalur yang relevan.

Modul berikutnya tidak boleh mengubah Core Rules secara diam-diam. Jika ada kebutuhan yang bertentangan atau membutuhkan pengecualian, perubahan harus dibuat secara eksplisit sebagai perubahan Canon.
