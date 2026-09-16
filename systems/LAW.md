# Eldoria World — Law / Legal Procedures v0.1

> **Module:** System #08 — Law / Legal Procedures  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Law / Legal Procedures menetapkan canonical owner untuk bagaimana hukum dan proses hukum direpresentasikan, diterapkan, diproses, dan menghasilkan konsekuensi legal dalam dunia Eldoria.

Modul ini adalah **framework Canon**, bukan daftar hukum spesifik, kitab hukum, kerajaan, pengadilan, hukuman, atau prosedur universal. Detail menjadi Canon hanya setelah ditetapkan secara eksplisit pada legal system, jurisdiction, atau data yang relevan.

## 2. Core Principle

Hukum adalah bagian dari kondisi sosial dan institusional dunia yang dapat berbeda menurut jurisdiction, authority, sejarah, masyarakat, dan konteks.

```text
POLITICS
→ authority / governance / jurisdiction

LAW
→ legal rules / applicability / procedures / legal status

STATE & HISTORY
→ persistent legal state / provenance
```

Tidak ada satu sistem hukum universal yang wajib berlaku di seluruh Eldoria.

## 3. Law vs Other Systems

Canonical ownership:

```text
LAW
= legal rules, legal applicability,
  legal status, legal procedures,
  adjudication, enforcement,
  legal consequences

POLITICS
= authority, governance, jurisdiction,
  political institutions and relations

ECONOMY
= economic processes, transactions,
  ownership, debt, markets

NPC BEHAVIOR
= NPC decision-making and agency

RELATIONSHIPS
= relationship state and lifecycle

REPUTATION
= socially attributed reputation

COMBAT
= combat / conflict resolution

HEALTH & INJURY
= health / injury state and consequences

TIME & CALENDAR
= temporal authority

STATE & HISTORY
= state, provenance, history, persistence
```

Law tidak mengambil alih resolution owner system lain.

## 4. Jurisdiction

Legal rules hanya berlaku jika terdapat dasar jurisdiction yang sah.

Jurisdiction dapat berhubungan dengan:

- wilayah;
- institusi;
- status hukum subjek;
- jenis perkara;
- otoritas tertentu;
- konteks lain yang ditetapkan Canon.

Political jurisdiction dan legal applicability saling berhubungan tetapi bukan konsep yang identik.

```text
POLITICAL JURISDICTION
≠
AUTOMATIC UNIVERSAL LEGAL RULE
```

Jika jurisdiction atau legal applicability belum diketahui, statusnya tetap Unknown / Undefined.

## 5. Legal System

Sebuah Legal System adalah kerangka hukum yang berlaku pada jurisdiction atau konteks tertentu.

Struktur konseptual:

```text
LEGAL SYSTEM
├── Legal System ID
├── Name
├── Jurisdiction Reference
├── Authority Reference
├── Legal Sources
├── Legal Domains
├── Rules Reference
├── Institutions
├── Procedures
├── Enforcement Structure
├── Current State Reference
├── History Reference
└── Metadata
```

Tidak semua field wajib tersedia untuk setiap legal system.

## 6. Legal Rule

Legal Rule adalah aturan hukum yang dapat menentukan kewajiban, larangan, izin, hak, status, prosedur, atau konsekuensi legal dalam scope yang sah.

Struktur konseptual:

```text
LEGAL RULE
├── Rule ID
├── Legal System Reference
├── Jurisdiction
├── Source
├── Scope
├── Applicable Subjects
├── Conditions
├── Prohibited Acts
├── Required Acts
├── Permitted Acts
├── Exceptions
├── Legal Consequences
├── Effective Context / Time
├── Knowledge Requirements (if applicable)
├── Current State Reference
├── History Reference
└── Metadata
```

Rule tidak boleh dianggap berlaku di luar scope yang ditetapkan.

## 7. Legal Status

Legal Status merepresentasikan kondisi hukum yang berlaku terhadap subject atau case.

Contoh kategori konseptual dapat meliputi:

- legal obligation;
- legal restriction;
- legal permission;
- pending legal case;
- legal order;
- warrant atau instrumen sejenis jika Canon mendefinisikannya;
- sentence atau decision;
- status hukum lain yang sah.

Kategori tersebut bukan daftar universal Eldoria.

Legal Status adalah State bila kondisi tersebut perlu dipertahankan oleh runtime.

## 8. Legal Actors & Institutions

Legal process dapat melibatkan actor atau institution yang memiliki kewenangan legal berdasarkan Canon dan jurisdiction.

Struktur konseptual:

```text
LEGAL ACTOR
├── Actor ID
├── Identity
├── Role
├── Authority Reference
├── Jurisdiction
├── Affiliation
├── Legal Powers
├── Current State Reference
└── History Reference
```

Memiliki jabatan atau afiliasi tidak otomatis berarti memiliki semua kewenangan hukum.

Authority harus memiliki dasar Canon yang relevan.

## 9. Legal Case / Dispute

Legal Case atau Dispute merepresentasikan proses hukum terhadap claim, allegation, dispute, atau perkara lain yang sah menurut legal system.

Struktur konseptual:

```text
LEGAL CASE
├── Case ID
├── Jurisdiction
├── Parties
├── Claim / Allegation
├── Legal Basis
├── Evidence References
├── Procedure State
├── Decision / Resolution
├── Consequences
├── Current State Reference
├── History Reference
└── Metadata
```

Adanya allegation atau claim tidak otomatis berarti pelanggaran atau kesalahan telah terbukti.

## 10. Legal Applicability

Sebelum suatu legal rule digunakan untuk resolution, runtime harus menentukan apakah rule tersebut berlaku pada action, subject, target, lokasi, waktu, dan konteks yang relevan.

Secara konseptual:

```text
ACTION / EVENT
↓
LEGAL RELEVANCE
↓
JURISDICTION
↓
APPLICABLE LEGAL RULES
↓
LEGAL RESOLUTION
```

Jika applicability tidak dapat ditentukan dari Canon dan State yang tersedia, runtime tidak boleh mengarang aturan.

## 11. Legal Resolution

Legal Resolution menentukan hasil proses hukum berdasarkan legal rules, jurisdiction, available facts/evidence, procedure, authority, dan konteks yang sah.

Hasil dapat berupa, jika didukung oleh legal system yang relevan:

- claim accepted;
- claim rejected;
- violation established;
- violation not established;
- dispute resolved;
- order issued;
- case pending;
- case dismissed;
- atau hasil lain yang ditetapkan Canon.

Daftar tersebut bersifat konseptual dan bukan hasil universal.

**Tidak ada formula legal universal pada v0.1.**

Jangan mengasumsikan:

```text
Evidence Score → automatic verdict
Crime Severity → automatic sentence
Wealth → automatic fine
```

kecuali mekanisme tersebut ditetapkan secara eksplisit oleh Canon yang relevan.

## 12. Evidence & Facts

Evidence adalah input yang dapat digunakan dalam proses hukum jika legal system yang relevan mengakuinya.

```text
FACT
≠
CLAIM
≠
ALLEGATION
≠
RUMOR
≠
EVIDENCE
```

Ketersediaan evidence tidak otomatis menentukan hasil legal tanpa proses resolution yang sah.

Character atau NPC juga dapat memiliki pengetahuan yang berbeda mengenai fakta dan evidence.

## 13. Legal Procedures

Legal procedure adalah proses yang digunakan untuk membawa legal matter dari satu status menuju status berikutnya.

Secara konseptual:

```text
LEGAL MATTER
↓
INITIATION
↓
PROCEDURE
↓
FACT / EVIDENCE PROCESSING
↓
ADJUDICATION / AUTHORIZED DECISION
↓
LEGAL RESULT
↓
ENFORCEMENT / CONSEQUENCE
```

Tahapan aktual, urutan, authority, dan persyaratan dapat berbeda antarlegal system.

Tidak ada satu prosedur pengadilan universal Eldoria pada v0.1.

## 14. Enforcement

Enforcement adalah proses pelaksanaan legal decision, order, restriction, atau consequence oleh actor atau institution yang memiliki dasar kewenangan.

Enforcement bukan otomatis sama dengan NPC behavior.

```text
LEGAL RESULT
↓
ENFORCEMENT REQUIREMENT
↓
AUTHORIZED ACTOR / PROCESS
↓
NPC OR FACTION DECISION
↓
ACTION
↓
STATE CHANGE
```

NPC atau faction tetap memiliki agency dalam batas kemampuan, pengetahuan, authority, resources, dan kondisi dunia.

## 15. Law & Politics

Politics menentukan struktur authority dan jurisdiction. Law menentukan aturan dan proses hukum yang berlaku di dalam struktur tersebut.

```text
POLITICAL AUTHORITY
↓
JURISDICTION
↓
LEGAL SYSTEM
↓
LEGAL RULES / PROCEDURES
```

Law tidak boleh secara diam-diam menciptakan kerajaan, pemerintah, batas politik, atau authority yang belum ditetapkan oleh Canon.

## 16. Law & Economy

Law dapat memberikan constraint atau status legal terhadap aktivitas ekonomi.

Contoh konseptual:

```text
ECONOMIC ACTION
↓
LEGAL APPLICABILITY
↓
LEGAL RESULT
```

Namun Law tidak mengambil alih economic resolution.

```text
LEGAL VALIDITY
≠
ECONOMIC SUCCESS
≠
OWNERSHIP CHANGE
```

Ownership, transaction, debt, price, market, dan proses ekonomi tetap berada pada Economy kecuali konsekuensi legalnya memang menghasilkan State Change yang sah.

## 17. Law & NPC Behavior

Hukum dapat menjadi constraint, information, motivation, risk, atau context bagi NPC.

Namun hukum tidak menentukan satu respons NPC secara otomatis.

```text
LEGAL CONDITION
↓
NPC KNOWLEDGE / CONTEXT
↓
NPC DECISION
↓
ACTION
```

NPC dapat patuh, melanggar, menolak, menghindar, melapor, meminta bantuan, atau memilih respons lain jika didukung kondisi dan kemampuan yang relevan.

## 18. Law & Relationships

Legal obligations atau disputes dapat memengaruhi relationship process, tetapi Law bukan owner relationship state.

```text
LEGAL PROCESS
→ possible relationship consequence

RELATIONSHIP
→ context for legal/social process
```

Tidak ada automatic relationship change hanya karena sebuah legal event terjadi kecuali proses yang relevan menghasilkan perubahan tersebut.

## 19. Law & Reputation

Legal events dapat menjadi sumber informasi yang memengaruhi Reputation apabila terjadi proses sosial atau informasi yang valid.

Namun:

```text
LEGAL VIOLATION
≠
AUTOMATIC BAD REPUTATION

ACQUITTAL
≠
AUTOMATIC GOOD REPUTATION
```

Reputation tetap bergantung pada audience, context, information, dan proses sosial yang relevan.

## 20. Knowledge Boundary

```text
LEGAL CANON
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
≠
UNCERTAIN INFORMATION
```

Karakter tidak otomatis mengetahui semua hukum yang diketahui Player atau AI GM.

Hukum yang berlaku dapat tidak diketahui, salah dipahami, diperdebatkan, atau diketahui hanya sebagian oleh actor.

Rumor tentang hukum, perkara, atau keputusan hukum tidak otomatis menjadi fakta Canon.

## 21. Law & Supernatural

Supernatural dapat berinteraksi dengan hukum jika legal system yang relevan mengakuinya.

Namun keberadaan supernatural tidak otomatis:

- mengubah legal rule;
- membuktikan claim;
- membatalkan procedure;
- menciptakan authority;
- menghapus consequence.

Interaksi khusus harus memiliki dasar Canon.

## 22. Runtime Integration

Law diintegrasikan ke Runtime sebagai system-specific resolution ketika action, event, atau autonomous process memiliki aspek legal yang relevan.

```text
CURRENT STATE
↓
PLAYER / NPC / WORLD ACTION
↓
VALIDATION
↓
LEGAL RELEVANCE?
├── NO → CONTINUE RELEVANT SYSTEM
└── YES
     ↓
  JURISDICTION
     ↓
  APPLICABLE RULES
     ↓
  LEGAL PROCEDURE / RESOLUTION
     ↓
  LEGAL RESULT
     ↓
  CONSEQUENCES
     ↓
  STATE CHANGE
     ↓
  HISTORY
     ↓
  PERSISTENCE
     ↓
  VERIFY
```

Law tidak menggantikan Runtime pipeline.

## 23. Multiple System Resolution

Satu action dapat membutuhkan beberapa system.

Contoh konseptual:

```text
PLAYER ACTION
↓
ECONOMY RESOLUTION
↓
LEGAL VALIDATION / CONSEQUENCE
↓
RELATIONSHIP CONSEQUENCE (if applicable)
↓
REPUTATION CONSEQUENCE (if applicable)
↓
STATE CHANGE VALIDATION
```

Urutan aktual ditentukan berdasarkan dependency dan kondisi action. Tidak boleh ada system yang mengklaim ownership atas domain system lain.

## 24. State Integration

Legal State yang persistent harus mengikuti State & History Model.

```text
LEGAL RESULT
↓
VALIDATED STATE CHANGE
├── Target / Subject
├── Field / Property
├── Previous Value
├── New Value
├── Origin
├── Source
└── World Time
↓
CURRENT STATE
↓
HISTORY
```

Narrative tidak menjadi legal State hanya karena dinarasikan.

## 25. History & Provenance

Perubahan legal yang penting bagi continuity, status, atau audit harus dapat ditelusuri melalui History.

History harus dapat menunjukkan setidaknya hubungan antara:

- legal matter atau action;
- subject/target;
- legal basis;
- result atau consequence;
- Origin;
- Source;
- World Time;
- State Change yang dihasilkan.

Koreksi mengikuti State & History Model dan tidak boleh menghapus sejarah secara diam-diam.

## 26. Autonomous Legal Processes

Legal process dapat berkembang tanpa keputusan Player jika terdapat dasar Canon, State, event, action, atau system process yang sah.

Contoh konseptual:

```text
NPC ACTION
↓
LEGAL MATTER
↓
AUTHORIZED PROCESS
↓
LEGAL RESULT
↓
STATE / HISTORY
```

AI GM tidak boleh membuat legal case, arrest, trial, conviction, fine, atau punishment semata-mata untuk menggerakkan plot.

## 27. Failure / Uncertainty

Legal resolution dapat menghasilkan:

- unresolved;
- pending;
- insufficient basis;
- disputed facts;
- blocked procedure;
- failed enforcement;
- atau hasil lain yang sah menurut legal system.

Ketidakpastian tidak boleh diisi dengan asumsi.

```text
UNKNOWN
≠
GUILTY
≠
INNOCENT
```

Status legal harus mengikuti bukti, aturan, procedure, dan resolution yang benar-benar tersedia.

## 28. No Universal Legal Mechanics

Law v0.1 tidak menetapkan secara universal:

- crime list;
- punishment list;
- fine amount;
- prison duration;
- evidence score;
- guilt probability;
- sentence formula;
- legal severity score;
- court success percentage;
- corruption probability;
- universal limitation period;
- universal arrest rule;
- universal legal age;
- universal legal code;
- universal court structure.

Semua detail tersebut tetap Unknown / Undefined sampai ditetapkan oleh Canon yang relevan.

## 29. Law Data Model Summary

```text
LEGAL SYSTEM
├── Identity
├── Jurisdiction
├── Authority
├── Sources
├── Rules
├── Institutions
├── Procedures
├── Enforcement
├── Current State
├── History
└── Metadata

LEGAL RULE
├── Identity
├── Scope
├── Jurisdiction
├── Conditions
├── Rights / Obligations / Restrictions
├── Exceptions
├── Consequences
└── Provenance

LEGAL CASE
├── Identity
├── Jurisdiction
├── Parties
├── Claim / Allegation
├── Legal Basis
├── Evidence
├── Procedure State
├── Decision
├── Consequences
└── History

LEGAL ACTOR
├── Identity
├── Role
├── Authority
├── Jurisdiction
├── Legal Powers
├── Current State
└── History
```

## 30. Canon Boundary

Law / Legal Procedures v0.1 **tidak** menetapkan:

- nama atau jumlah kerajaan;
- government tertentu;
- jurisdiction tertentu;
- kitab hukum tertentu;
- daftar crime universal;
- hukuman universal;
- pengadilan tertentu;
- polisi atau aparat tertentu;
- prosedur pengadilan universal;
- sistem hukum universal;
- legal currency/fine;
- legal age universal;
- evidence formula;
- guilt probability;
- sentence formula;
- atau fakta legal spesifik yang belum ditetapkan.

Detail legal hanya menjadi Canon setelah ditetapkan pada legal system, jurisdiction, data, event, atau sumber Canon yang relevan.

## 31. Dependencies & Integration

Law terhubung dengan:

```text
CORE RULES
↓
RUNTIME / TURN MODEL
↓
STATE & HISTORY
↓
POLITICS
├── jurisdiction / authority context
├── CIVILIZATION
├── FACTIONS
└── ECONOMY

LAW
├── NPC BEHAVIOR
├── RELATIONSHIPS
├── REPUTATION
├── COMBAT
├── HEALTH & INJURY
├── TIME & CALENDAR
└── SUPERNATURAL / MAGIC
```

Dependencies memberikan konteks dan input; tidak memberikan permission kepada Law untuk mengambil alih ownership system lain.

## 32. Integrity Rules

- Law adalah canonical owner domain hukum dan proses hukum.
- Politics tetap owner authority, governance, dan political jurisdiction.
- Legal applicability harus memiliki dasar jurisdiction yang sah.
- Legal rule tidak otomatis berlaku secara universal.
- Claim/allegation tidak otomatis berarti violation terbukti.
- Legal result tidak boleh diciptakan hanya untuk kebutuhan narrative.
- Law tidak mengambil alih economic, combat, health, NPC, relationship, reputation, time, atau persistence resolution.
- NPC tetap memiliki agency ketika merespons hukum.
- Character Knowledge tidak otomatis sama dengan Canon atau Player Knowledge.
- Rumor tidak otomatis menjadi legal fact.
- Legal State yang persistent harus mengikuti State & History.
- Legal changes penting harus memiliki provenance yang dapat ditelusuri.
- Unknown / Undefined tetap Unknown / Undefined.
- Tidak ada numeric legal fallback pada v0.1.
- Tidak ada universal legal formula pada v0.1.
- Tidak ada universal law, court, crime, punishment, atau procedure pada v0.1.
- Narrative bukan sumber legal State atau persistence.

## 33. Future Extensions

Modul ini dapat diperluas melalui Canon tersendiri untuk:

```text
SPECIFIC LEGAL SYSTEMS
JURISDICTION DATA
LEGAL CODES
COURT / ADJUDICATION SYSTEMS
ENFORCEMENT SYSTEMS
LEGAL PROCEDURE DETAILS
LEGAL KNOWLEDGE / INFORMATION SYSTEMS
```

Ekstensi tidak boleh mengubah Core Rules atau ownership system lain secara diam-diam. Jika diperlukan perubahan Canon lintas sistem, perubahan harus dilakukan secara eksplisit dan diaudit.
