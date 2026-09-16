# Eldoria World — Health & Injury System v0.1

> **Module:** Health & Injury  
> **Version:** v0.1  
> **Authority:** Official Canon / World System

## 1. Purpose

Health & Injury v0.1 menetapkan canonical owner untuk representasi kondisi kesehatan, cedera, luka, gangguan fungsi fisik, perkembangan kondisi, recovery, treatment, dan konsekuensi kesehatan yang relevan terhadap simulasi Eldoria.

Modul ini menjadi fondasi kesehatan untuk Character, NPC, Creatures, Combat, Supernatural / Magic, Environment, Travel, dan system lain yang secara sah menghasilkan atau memengaruhi kondisi kesehatan.

Modul ini mendefinisikan struktur, boundary, lifecycle, dan prinsip resolusi. Modul ini **tidak** menetapkan HP universal, damage formula, healing rate universal, stat block, daftar penyakit, atau angka kesehatan tanpa Canon eksplisit.

## 2. Canonical Ownership

Health & Injury adalah canonical owner untuk **health-state dan injury-state representation**.

```text
CAUSE / PROCESS
      ↓
HEALTH & INJURY RESOLUTION
      ↓
HEALTH / INJURY STATE
      ↓
STATE / HISTORY
```

System lain dapat menjadi sumber penyebab atau konteks, tetapi tidak boleh diam-diam membuat definisi kesehatan yang bertentangan.

Dependency tidak memberikan hak kepada Health & Injury untuk mengambil alih domain system lain.

## 3. Core Principles

- Kondisi kesehatan adalah bagian dari simulasi, bukan sekadar deskripsi naratif.
- Injury tidak otomatis berarti satu angka damage.
- Tidak semua injury memiliki konsekuensi yang sama.
- Tidak semua kondisi kesehatan harus direpresentasikan dengan angka.
- Severity, symptoms, functional impact, cause, dan recovery dapat berbeda dan harus memiliki dasar.
- Intent Player ≠ injury result ≠ State Change.
- AI GM tidak boleh memberi luka atau menyembuhkan karakter tanpa basis resolution yang sah.
- Tidak ada plot armor maupun arbitrary punishment berbasis kesehatan.
- Healing bukan automatic reset.
- Recovery memerlukan waktu dan/atau proses apabila Canon yang relevan menetapkannya.
- Persistent health changes mengikuti State & History Model.
- Unknown / Undefined tetap dipertahankan ketika mekanismenya belum ditetapkan.

## 4. Health Concepts

### Health State

Kondisi kesehatan yang berlaku pada suatu subject pada suatu waktu.

### Injury

Kerusakan atau gangguan fisik yang dihasilkan oleh cause atau process yang valid.

### Wound

Jenis injury yang secara khusus berkaitan dengan kerusakan jaringan atau kondisi luka sebagaimana didefinisikan oleh Canon yang relevan.

### Condition

Keadaan kesehatan yang dapat bersifat sementara, berkelanjutan, berulang, atau menetap.

### Symptom

Manifestasi atau tanda kondisi kesehatan yang dapat diamati atau dirasakan.

### Functional Impact

Dampak suatu kondisi terhadap fungsi fisik atau kemampuan melakukan aktivitas.

### Recovery

Proses perubahan menuju kondisi yang lebih pulih setelah injury atau condition.

### Treatment

Intervensi yang ditujukan untuk menangani condition atau injury berdasarkan metode yang valid.

```text
HEALTH ≠ INJURY ≠ SYMPTOM ≠ FUNCTIONAL IMPACT ≠ TREATMENT ≠ RECOVERY
```

## 5. Health State Model

Model konseptual:

```text
HEALTH STATE
├── Health State ID
├── Subject ID
├── Overall Condition (if defined)
├── Active Injuries / Conditions
├── Functional Effects
├── Treatment / Recovery Status
├── Temporal Context
├── Origin / Source
├── Revision
└── Validation Status
```

Field final dapat diperluas oleh system kesehatan khusus tanpa melanggar canonical ownership.

Tidak ada label seperti healthy, wounded, critical, atau incapacitated yang menjadi universal hanya karena contoh tersebut digunakan dalam narrative.

## 6. Injury Model

```text
INJURY
├── Injury ID
├── Subject ID
├── Type / Classification (if defined)
├── Location / Body Context (if defined)
├── Cause
├── Onset Time
├── Severity (if defined)
├── Symptoms
├── Functional Impact
├── Active / Resolved Status
├── Treatment
├── Recovery State
├── Complications (if defined)
├── Origin
├── Source
├── Current State Reference
└── History Reference
```

Jenis, severity, body classification, dan consequence tidak boleh diisi dengan asumsi ketika Canon belum menyediakan mekanisme.

## 7. Severity

Severity adalah representasi tingkat dampak suatu injury atau condition apabila system yang relevan membutuhkannya.

Severity dapat menggunakan:

- kategori kualitatif;
- nilai terukur;
- kombinasi beberapa indikator;
- atau representasi lain yang ditetapkan Canon.

V0.1 tidak menetapkan skala universal seperti 1–10, persentase, tier, atau threshold HP.

Severity ≠ damage amount secara otomatis.

## 8. Functional Impact

Kondisi kesehatan dapat memengaruhi fungsi karakter/entity.

Contoh kategori konseptual:

- movement;
- strength or exertion;
- manipulation;
- perception;
- communication;
- concentration;
- endurance;
- ability to perform particular actions.

Contoh tersebut bukan daftar universal effect. Dampak spesifik harus ditentukan oleh kondisi dan system resolution yang relevan.

Health & Injury tidak boleh mengubah seluruh kemampuan karakter secara otomatis hanya karena injury tercatat.

## 9. Pain, Symptoms & Observable Effects

Pain dan symptoms dapat menjadi bagian dari Health State jika relevan.

Perbedaan harus dijaga antara:

```text
INTERNAL CONDITION
≠
SUBJECTIVE EXPERIENCE
≠
OBSERVABLE SYMPTOM
≠
FUNCTIONAL CONSEQUENCE
```

AI GM tidak boleh mengasumsikan pengalaman internal karakter Player tanpa dasar yang diberikan Player atau aturan Canon yang sah.

## 10. Causes of Injury / Health Change

Health changes dapat berasal dari:

- Player action;
- NPC action;
- creature interaction;
- combat;
- environmental hazard;
- accident;
- disease or biological process;
- supernatural / magic effect;
- treatment;
- recovery process;
- autonomous world process;
- atau source valid lain.

Health & Injury merepresentasikan konsekuensi kesehatan. System sumber tetap memiliki authority atas mekanisme penyebabnya.

## 11. Multiple Injuries & Conditions

Satu subject dapat memiliki beberapa injury atau condition secara bersamaan.

```text
SUBJECT
├── INJURY A
├── INJURY B
├── CONDITION C
└── CONDITION D
```

System harus mempertahankan identitas kondisi yang berbeda ketika kondisi tersebut memiliki lifecycle, cause, treatment, atau consequence yang berbeda.

Kondisi tidak boleh digabung atau dihapus hanya untuk menyederhanakan narrative.

Jika beberapa kondisi saling memengaruhi, interaksi tersebut harus memiliki dasar resolution yang valid.

## 12. Onset, Progression & Aggravation

Condition dapat:

- muncul;
- memburuk;
- membaik;
- stabil;
- kambuh;
- menjadi komplikasi;
- atau terselesaikan

apabila proses yang relevan menyediakan basis.

```text
CAUSE
↓
ONSET
↓
CURRENT CONDITION
↓
VALIDATED PROCESS
↓
NEW CONDITION
```

Health & Injury tidak boleh mengarang perkembangan hanya karena waktu telah berlalu. Temporal passage menyediakan waktu; health process menentukan apakah dan bagaimana kondisi berubah.

## 13. Recovery

Recovery adalah perubahan kondisi menuju pemulihan setelah injury atau condition.

Recovery dapat dipengaruhi oleh faktor yang ditetapkan oleh system relevan, misalnya:

- waktu;
- severity;
- rest;
- treatment;
- environment;
- nutrition/resources;
- supernatural intervention;
- repeated strain;
- complications;
- atau faktor lain yang telah memiliki Canon.

V0.1 tidak menetapkan recovery rate, healing points per day, atau durasi universal.

```text
INJURY
↓
VALID RECOVERY CONDITIONS
↓
RECOVERY PROCESS
↓
HEALTH STATE CHANGE
```

## 14. Treatment

Treatment adalah intervensi yang memengaruhi health condition.

Treatment dapat berasal dari:

- self-care;
- rest;
- another character;
- medical practitioner;
- equipment/item;
- supernatural method;
- environmental resource;
- atau metode lain yang Canon sahkan.

Treatment intent tidak menjamin treatment berhasil.

```text
TREATMENT INTENT
↓
VALIDATION
↓
RESOLUTION
↓
HEALTH RESULT
↓
STATE CHANGE
```

Tidak ada free healing atau automatic cure hanya karena treatment dinyatakan.

## 15. Aggravation & Re-injury

Aktivitas baru dapat memperburuk injury yang masih aktif apabila kondisi, action, dan resolution mendukungnya.

Re-injury harus dapat dibedakan dari progression condition lama ketika source dan timing berbeda.

Tidak boleh ada automatic stacking formula tanpa Canon.

## 16. Complications

Complication adalah perkembangan tambahan yang muncul dari condition atau proses kesehatan apabila mekanisme yang relevan menetapkannya.

Complication dapat bersifat:

- immediate;
- delayed;
- temporary;
- persistent;
- reversible;
- irreversible,

jika Canon yang relevan mendukung klasifikasi tersebut.

V0.1 tidak menetapkan daftar komplikasi universal maupun probabilitasnya.

## 17. Incapacitation & Critical Conditions

Health condition dapat membatasi atau menghentikan kemampuan melakukan action tertentu apabila resolution yang valid menghasilkan keadaan tersebut.

Istilah seperti incapacitated, unconscious, critical, dying, atau dead harus diperlakukan sebagai State yang memiliki definisi dan trigger sah ketika digunakan sebagai mekanik.

V0.1 tidak menetapkan threshold universal untuk status tersebut.

Death adalah state outcome yang harus berasal dari resolution yang valid, bukan hukuman narrative otomatis.

## 18. Death & Irreversible Outcomes

Jika suatu resolution menghasilkan kematian atau outcome kesehatan permanen, perubahan tersebut harus memiliki:

- cause;
- valid resolution;
- temporal context;
- State Change;
- History;
- persistence verification ketika persistence diperlukan.

AI GM tidak boleh membatalkan atau memberikan kebangkitan otomatis tanpa Canon yang sah.

Jika resurrection atau equivalent supernatural mechanism kelak dibuat, system tersebut harus memiliki rules sendiri dan berintegrasi dengan Health & Injury serta State/History.

## 19. Time Integration

Health & Injury menggunakan `systems/TIME_AND_CALENDAR.md` sebagai canonical temporal authority.

```text
HEALTH PROCESS
↓
VALIDATED DURATION
↓
TIME ADVANCEMENT
↓
HEALTH STATE UPDATE
```

Time & Calendar menentukan representasi waktu dan temporal ordering.

Health & Injury menentukan apakah suatu health process membutuhkan waktu dan apa consequence yang sah berdasarkan rules-nya.

Tidak ada universal recovery duration dalam v0.1.

## 20. Runtime Integration

Health-related action mengikuti Runtime Turn Model:

```text
PLAYER / NPC / WORLD INPUT
↓
PARSE
↓
VALIDATE
↓
RESOLVE CAUSE / PROCESS
↓
CALCULATE HEALTH CONSEQUENCES
↓
GENERATE HEALTH STATE CHANGES
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
↓
RESPONSE
```

Jika health process menghasilkan elapsed time, temporal resolution harus dilakukan melalui Time & Calendar.

Health state tidak boleh berubah hanya karena narrative menyebutkan luka atau pemulihan.

## 21. Character Integration

Health & Injury menggunakan struktur Character Data Model, terutama:

- Physical Profile;
- Current State;
- Conditions;
- History Reference.

Character Data Model tetap menjadi canonical owner struktur karakter.

Health & Injury menjadi owner atas health/injury information yang disimpan di dalam struktur tersebut.

Starting State tetap tidak ditimpa oleh injury gameplay.

```text
STARTING HEALTH STATE
        ↓
VALIDATED HEALTH CHANGES
        ↓
CURRENT HEALTH STATE
```

## 22. NPC & Creature Integration

Health & Injury dapat diterapkan pada NPC atau creature ketika subject tersebut memiliki persistent state yang relevan.

NPC/creature health tidak otomatis memiliki formula berbeda dari Character hanya karena subject berbeda.

Perbedaan biology atau anatomy hanya berlaku jika Canon subject yang relevan telah mendefinisikannya.

## 23. Combat Integration

Combat System kelak menjadi canonical owner untuk combat resolution.

Health & Injury menjadi canonical owner untuk konsekuensi kesehatan yang dihasilkan combat.

```text
COMBAT RESOLUTION
↓
VALIDATED CONSEQUENCE
↓
HEALTH & INJURY
↓
HEALTH STATE
```

Combat tidak boleh membuat health formula yang bertentangan dengan system ini.

Health & Injury tidak menentukan seluruh aturan combat.

## 24. Creature / Ecology Integration

Creature interaction dapat menghasilkan health consequences apabila encounter atau ecological process memiliki basis yang sah.

Creature-specific biology, venom, disease, attack method, atau environmental interaction tetap harus berasal dari Creature Canon atau system terkait jika telah didefinisikan.

Tidak semua creature interaction menghasilkan injury.

## 25. Supernatural / Magic Integration

Magic dapat menjadi cause atau treatment untuk health conditions jika mekanisme magic yang relevan telah ditetapkan.

```text
MAGIC RESOLUTION
↓
SUPERNATURAL CONSEQUENCE
↓
HEALTH & INJURY STATE
```

Health & Injury tidak menciptakan spell, mana, magic cost, resurrection rule, atau magical healing formula.

## 26. Environment & Travel Integration

Environment atau travel dapat menjadi source health changes melalui hazard atau process yang valid.

Geography menentukan konteks ruang dan environment sesuai Canon-nya.

Travel System kelak menentukan proses perjalanan.

Health & Injury menentukan konsekuensi kesehatan yang dihasilkan jika resolution memberikan dasar yang valid.

## 27. Knowledge Boundary

```text
HEALTH CANON
≠
CHARACTER KNOWLEDGE
≠
PLAYER KNOWLEDGE
```

Karakter tidak otomatis mengetahui diagnosis, severity, hidden condition, atau internal state hanya karena data tersebut tersedia pada simulation layer.

Character Knowledge tentang health harus berasal dari perception, experience, education, treatment, information source, atau mekanisme valid lain.

AI GM tidak boleh menggunakan hidden health data sebagai pengetahuan karakter tanpa basis.

## 28. State & History Integration

Health State Change mengikuti State & History Model.

Minimum conceptual record:

```text
HEALTH STATE CHANGE
├── Change ID
├── Subject ID
├── Health Field / Condition
├── Previous Value
├── New Value
├── Cause / Origin
├── Source
├── World Time
└── Validation Status
```

History harus dapat menjelaskan bagaimana kondisi kesehatan saat ini terbentuk.

Correction terhadap health history tidak boleh dilakukan dengan menghapus record secara diam-diam.

## 29. Autonomous Health Processes

World dapat mengalami health-related changes tanpa Player input apabila system yang relevan memiliki autonomous process yang sah.

Contoh konseptual:

- NPC recovery;
- creature injury progression;
- disease process;
- environmental exposure;
- treatment process;
- delayed complication.

Autonomy ≠ random health change tanpa basis.

Setiap persistent change harus memiliki source dan valid temporal context.

## 30. Resolution & Formula Discipline

V0.1 tidak menetapkan universal:

- HP maximum;
- HP current;
- damage;
- damage multiplier;
- armor mitigation;
- injury probability;
- critical threshold;
- healing rate;
- recovery duration;
- death threshold;
- disease probability;
- treatment success probability;
- pain scale;
- regeneration rate;
- atau numeric health formula lain.

Jika formula diperlukan, urutannya:

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

Tidak boleh menggunakan default numeric fallback.

## 31. Health Data Model

```text
HEALTH ENTITY
├── Health ID
├── Subject ID
├── Current Health State
├── Active Injuries
├── Active Conditions
├── Functional Effects
├── Treatment / Recovery References
├── Temporal Context
├── Current State Reference
├── History Reference
└── Metadata
```

### Injury Entity

```text
INJURY ENTITY
├── Injury ID
├── Subject ID
├── Classification (if defined)
├── Body Context (if defined)
├── Cause
├── Onset Time
├── Severity (if defined)
├── Symptoms
├── Functional Impact
├── Treatment
├── Recovery State
├── Complications (if defined)
├── Status
├── Origin
├── Source
├── Current State Reference
└── History Reference
```

## 32. Canon Boundary

Health & Injury v0.1 **tidak** menetapkan:

- universal HP system;
- universal health points;
- damage formula;
- armor/damage mitigation;
- final injury taxonomy;
- final disease list;
- universal anatomy;
- universal biology;
- universal pain scale;
- universal severity scale;
- universal healing rate;
- universal treatment success rate;
- medical profession rules;
- medicine item list;
- resurrection rules;
- combat rules;
- creature attack stats;
- magic healing spells;
- travel hazard formulas;
- survival formulas;
- death threshold;
- permanent disability list;
- or other mechanics owned by future systems.

Undefined mechanics remain `Unknown / Undefined` until explicitly established by Canon.

## 33. Progressive Development

```text
HEALTH & INJURY FRAMEWORK
↓
HEALTH / INJURY DATA MODEL
↓
CONDITION CLASSIFICATION
↓
RESOLUTION RULES
↓
COMBAT / CREATURE / MAGIC / ENVIRONMENT INTEGRATION
↓
TREATMENT / RECOVERY EXTENSIONS
↓
STATE / HISTORY
↓
PERSISTENT HEALTH SIMULATION
```

Future specialized modules may extend this system without silently replacing its canonical ownership.

## 34. Dependencies & Integration

Primary dependencies:

```text
core/CORE_RULES.md
core/RUNTIME_TURN_MODEL.md
characters/CHARACTER_DATA_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
systems/TIME_AND_CALENDAR.md
world/WORLD_FOUNDATION.md
world/GEOGRAPHY.md
world/PEOPLES_RACES.md
world/SUPERNATURAL_MAGIC.md
world/CREATURES_ECOLOGY.md
world/ECONOMY.md
world/POLITICS.md
world/FACTIONS.md
```

Not every health process requires every dependency. Runtime resolution must load only relevant Canon/data.

## 35. Integrity Rules

1. Health state must have a valid subject.
2. Injury/condition changes require a valid cause or process.
3. Intent is never treated as health result.
4. Narrative is not itself a State Change.
5. Health changes must be compatible with Current State.
6. Starting State must not be overwritten by gameplay changes.
7. Persistent changes require appropriate State/History handling.
8. Time-dependent health processes require valid temporal context.
9. No arbitrary healing or injury.
10. No hidden numeric fallback.
11. Health system must not duplicate combat, magic, creature, travel, or economy authority.
12. Character Knowledge must not be inferred from hidden simulation data.
13. Multiple interdependent health changes must be validated together when necessary.
14. Death or permanent outcomes require valid resolution and provenance.
15. Autonomous health changes require a valid system/process basis.
16. Unknown / Undefined must remain Unknown / Undefined.
17. Cross-system conflicts are integrity issues and must not be silently resolved.
18. Canon changes must occur explicitly through the Repository.

## 36. Design Status

**Health & Injury v0.1 — Official Canon Framework**

This module establishes the canonical health/injury boundary and integration architecture for Eldoria. It intentionally leaves detailed numerical mechanics and specialized medical/combat mechanics for later explicit Canon development.
