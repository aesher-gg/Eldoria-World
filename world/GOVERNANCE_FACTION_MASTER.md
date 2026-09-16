# ELDORIA WORLD — GOVERNANCE & FACTION MASTER CONTEXT

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Master context governance dan faction sebagai prerequisite Canon NPC.
> **Scope:** Architecture, authority boundaries, faction slots, dan Canonization gates. Tidak membuat NPC individual.

---

## 1. Canon Safety

File ini hanya menetapkan struktur dan fakta yang telah memiliki dasar Canon.

```text
KNOWN / CANON → boleh digunakan
???           → Unknown / Unresolved; tidak boleh ditebak
PENDING       → belum boleh digunakan sebagai fakta spesifik
```

Nama penguasa, hukum, faction spesifik, hubungan politik spesifik, dan detail kekuasaan yang belum ditetapkan tetap `???`.

---

## 2. Governance Hierarchy

```text
EMPIRE-001 — Kekaisaran Valthera
        ↓
KINGDOM-001 — Valedorn
KINGDOM-002 — Brannor
KINGDOM-003 — Mariselle
KINGDOM-004 — Sylvaran
KINGDOM-005 — Sahrad
        ↓
REGION → CITY → SETTLEMENT
```

### 2.1 Empire Governance — Canon

```text
POLITICAL_SYSTEM: Monarki Kekaisaran Terdesentralisasi
HEAD_OF_STATE: NPC-CANON-011 — Aurelian Valthera
CENTRAL_AUTHORITY: Pemerintahan Kekaisaran
KINGDOM_AUTONOMY: Internal governance permitted within Imperial law
IMPERIAL_SCOPE: Pertahanan bersama, hukum kekaisaran, hubungan antar-kerajaan, kepentingan strategis, dan urusan yang ditetapkan oleh hukum kekaisaran
LOCAL_SCOPE: Pemerintahan kerajaan dan administrasi lokal berada pada kerajaan masing-masing sesuai hukum yang berlaku
```

### 2.2 Kingdom Governance — Canon

Kelima Kingdom memiliki internal autonomy dalam batas `38_LAW_SYSTEM.md` dan hukum Kekaisaran Valthera.

| Kingdom | Head of State | Central Government Body | Succession Baseline |
|---|---|---|---|
| KINGDOM-001 Valedorn | NPC-CANON-012 — Cedric Varen | Royal Court of Valedorn | Designated-heir primogeniture, gender-neutral |
| KINGDOM-002 Brannor | NPC-CANON-013 — Tharok Brann | High Crown Council of Brannor | Designated-heir primogeniture, gender-neutral |
| KINGDOM-003 Mariselle | NPC-CANON-014 — Celestine Aureon | Maritime Crown Council of Mariselle | Designated-heir primogeniture, gender-neutral |
| KINGDOM-004 Sylvaran | NPC-CANON-015 — Edrien Sylvar | Royal Stewardship Council of Sylvaran | Designated-heir primogeniture, gender-neutral |
| KINGDOM-005 Sahrad | NPC-CANON-016 — Nadir Qasrane | Royal Oasis Council of Sahrad | Designated-heir primogeniture, gender-neutral |

Detailed legal rules are authoritative in `38_LAW_SYSTEM.md`.

### 2.3 Kingdom Authority Boundaries

**Crown / Kingdom central authority** memiliki authority atas:

- kingdom executive administration;
- lawful title grants dan recognition dalam Kingdom scope;
- high-level domain grants dan delegated administration;
- kingdom-wide taxation/revenue policy sesuai hukum;
- kingdom military/security organization dalam batas Imperial law;
- inter-kingdom representation sesuai Imperial scope;
- appointment/removal of lawful royal offices;
- succession administration sesuai local succession law.

**Regional / City / Settlement authority** hanya memiliki kewenangan yang didelegasikan atau diberikan oleh hukum lokal. Nama wilayah, kota, atau settlement tidak dengan sendirinya menciptakan office, title, sovereignty, tax power, military command, atau judicial supremacy.

**Noble House / Noble Title** tidak otomatis memiliki authority di luar lawful grant, office, domain right, contract, atau delegation yang relevan.

### 2.4 Succession Authority

Succession resolution wajib mengikuti:

```text
CLAIM
↓
ELIGIBILITY
↓
LOCAL SUCCESSION LAW
↓
LEGAL / INSTITUTIONAL CONFIRMATION
↓
STATE UPDATE
↓
HISTORY + ORIGIN
```

Military force, wealth, magic, popularity, race, House membership, atau personal influence tidak menggantikan legal succession basis.

---

## 3. Governance Scope Matrix

| Scope | Authority baseline | Known | Unresolved |
|---|---|---|---|
| Empire | Imperial central authority + defined imperial scope | Political system, ruler identity, broad scope, Law hierarchy | Detailed ministries, full judicial/economic institutions |
| Kingdom | Internal autonomy under Imperial law | Five rulers, five central governance bodies, succession baseline, 10 Canon Noble Houses | Detailed lower offices, additional specific laws |
| Region | Parent kingdom administration | Parent hierarchy | Regional offices/authority = ??? unless delegated/Canonized |
| City | Parent kingdom/local administration | Parent hierarchy | City government/offices = ??? unless delegated/Canonized |
| Settlement | Local administration under parent hierarchy | Parent hierarchy | Local offices/authority = ??? unless delegated/Canonized |

No lower-level office may be inferred solely from settlement or city name.

---

## 4. Faction Architecture

Faction identity follows `04_FACTIONS.md`. Operational behavior follows `19_FACTION_SYSTEM.md`.

Every persistent specific faction must have:

```text
FACTION_ID
NAME
TYPE
LEADERSHIP
GOALS
INTERESTS
CURRENT_STATE
ORIGIN
HISTORY
```

Possible faction types are framework categories, not a declaration that a specific faction currently exists:

```text
KINGDOM
NOBLE_HOUSE
GUILD
MILITARY_ORDER
RELIGIOUS_ORGANIZATION
CRIMINAL_ORGANIZATION
MERCANTILE_ORGANIZATION
ADVENTURING_GROUP
TRIBE
LOCAL_COMMUNITY
OTHER_VALID_TYPE
```

### 4.1 Faction Layers

```text
IMPERIAL
  ↓
KINGDOM
  ↓
REGIONAL / CITY
  ↓
SETTLEMENT / LOCAL
  ↓
CROSS-TERRITORIAL
```

A faction may operate across multiple geographic scopes when its actual territory, influence, membership, or activity supports that scope.

### 4.2 Faction Status

Each specific faction must be classified as one of:

```text
CANON
DYNAMIC
DYNAMIC_PERSISTENT
```

A dynamic faction does not become Canon merely because it becomes persistent.

---

## 5. Faction Master Planning Slots

These are **planning slots**, not named factions. No slot implies that a faction already exists.

### Empire-level slots

```text
IMPERIAL_GOVERNANCE
IMPERIAL_MILITARY
IMPERIAL_JUDICIAL / LEGAL
IMPERIAL_ECONOMIC / MERCANTILE
IMPERIAL_RELIGIOUS / CULTURAL
IMPERIAL_DIPLOMATIC
OTHER_STRATEGIC_FACTIONS: ???
```

### Kingdom-level slots — each Kingdom

```text
ROYAL / CENTRAL_GOVERNANCE
MILITARY / SECURITY
ECONOMIC / MERCANTILE
NOBILITY / POLITICAL
RELIGIOUS / CULTURAL
LOCAL / REGIONAL INTEREST GROUPS
OTHER_KINGDOM-SPECIFIC_FACTIONS: ???
```

### City-level slots

```text
CITY_GOVERNANCE
TRADE / CRAFT / SERVICE
SECURITY / WATCH
RELIGIOUS / COMMUNITY
OTHER_LOCAL_FACTIONS: ???
```

### Settlement-level slots

```text
LOCAL_COMMUNITY
LOCAL_ECONOMIC_GROUP
LOCAL_SECURITY / DEFENSE
OTHER_LOCAL_GROUPS: ???
```

These slots are used to test whether future NPC roles have a valid institutional or social context. They do not require every scope to contain every faction type.

---

## 6. NPC Governance/Faction Dependency

Canon NPC creation must pass this gate:

```text
GEOGRAPHY
↓
POPULATION MODEL
↓
GOVERNANCE CONTEXT
↓
FACTION CONTEXT (when applicable)
↓
NPC ROLE / AUTHORITY
↓
CANON NPC
```

For each future Canon NPC:

```text
ROLE              → must have a valid context
FACTION           → must reference an existing/valid faction or be explicitly ???
AUTHORITY         → must be supported by governance/faction structure
CORE RELATIONSHIPS → must not contradict established political structure
KNOWLEDGE_BOUNDARY → must follow actual position/access
```

NPC tidak boleh memperoleh jabatan, faction, political influence, atau authority hanya karena dibutuhkan untuk memenuhi Coverage Matrix.

---

## 7. Political Relationship Rules

Relationship antar-faction menggunakan state yang diizinkan Module 04:

```text
ALLY
FRIENDLY
NEUTRAL
TENSE
HOSTILE
AT_WAR
```

Hubungan spesifik antar-faction belum ditetapkan pada Master Context ini.

```text
EMPIRE ↔ KINGDOM RELATIONS: baseline defined by imperial hierarchy; specific political relationship = ???
KINGDOM ↔ KINGDOM RELATIONS: ???
FACTION ↔ FACTION RELATIONS: ???
```

No relationship may be invented to give an NPC a political connection.

---

## 8. Authority Rules

1. Empire memiliki authority pada scope yang telah ditetapkan Canon dan `38_LAW_SYSTEM.md`.
2. Kingdom memiliki internal governance autonomy dalam batas hukum kekaisaran.
3. Lower-level authority tidak boleh mengklaim kewenangan yang belum ditetapkan atau didelegasikan.
4. Faction influence tidak sama dengan sovereignty.
5. Claim, control, influence, dan occupation tetap konsep berbeda.
6. Membership tidak otomatis memberikan authority.
7. NPC position does not automatically imply access to information, resources, or decision-making power.
8. Noble title tidak otomatis memberikan domain, military command, taxation rights, judicial supremacy, atau magical authority.
9. Material political changes wajib melalui resolution dan persistence.

---

## 9. Law Authority Reference

`38_LAW_SYSTEM.md` adalah authority reference untuk:

```text
LAW HIERARCHY
IMPERIAL LEGAL BASELINE
KINGDOM SUCCESSION
TITLE RECOGNITION
DOMAIN AUTHORITY
MILITARY AUTHORITY
TAX AUTHORITY
DISPUTED SUCCESSION
```

Jika dokumen governance dan law tampak berbeda pada authority/succession, resolution harus menggunakan hierarchy hukum yang ditetapkan Module 38 dan tidak boleh memilih hasil berdasarkan narasi.

---

## 10. Canonization Gate for Specific Factions

Sebelum faction spesifik ditetapkan sebagai Canon, Admin wajib dapat menentukan minimal:

```text
FACTION_ID
NAME
TYPE
PARENT / OPERATING_SCOPE
LEADERSHIP
GOALS
INTERESTS
CORE_MEMBERSHIP_CONTEXT
TERRITORY / INFLUENCE (jika relevan)
CURRENT_STATE
ORIGIN
HISTORY
```

Jika suatu field belum memiliki dasar Canon, nilainya tetap `???` dan faction belum boleh digunakan untuk mengarang detail lain yang bergantung padanya.

---

## 11. Relationship to NPC Coverage Matrix

`npcs/COVERAGE_MATRIX_v1_0.md` menentukan kebutuhan coverage NPC.

File ini menentukan konteks governance/faction yang harus tersedia sebelum NPC individual dibuat.

```text
COVERAGE MATRIX
      +
GOVERNANCE / FACTION MASTER CONTEXT
      ↓
NPC MASTER LIST
      ↓
INDIVIDUAL CANON NPC RECORDS
```

Coverage quota tidak boleh menjadi sumber lore.

---

## 12. Current Phase

```text
GEOGRAPHY CANON: COMPLETE
POPULATION MODEL: ACTIVE
NPC ARCHITECTURE: COMPLETE
NPC COVERAGE MATRIX: COMPLETE
GOVERNANCE BASELINE: ESTABLISHED
KINGDOM GOVERNANCE BODIES: CANON — 5 REGISTERED
KINGDOM SUCCESSION BASELINE: CANON — 5 KINGDOMS
HEAD-OF-STATE CANON: ACTIVE — 5 REGISTERED
NOBLE HOUSE CANON: ESTABLISHED — 10 ACTIVE CANON HOUSES
FACTION FRAMEWORK: ESTABLISHED
SPECIFIC FACTION CANON: ESTABLISHED — 53 ACTIVE CANON FACTIONS
INDIVIDUAL CANON NPC: ACTIVE — 21 REGISTERED
CURRENT NPC CREATION METHOD: CONTROLLED BATCHES OF UP TO 5
QUOTA STATUS: COVERAGE TARGET ONLY; NO MASS NPC FILLING
```

---

## 13. Final Principle

> **Governance dan faction menyediakan konteks authority dan kepentingan; law menentukan batas kewenangan dan succession; NPC dibangun dari konteks tersebut, bukan sebaliknya. `???` tidak boleh diisi hanya untuk membuat NPC terlihat lengkap.**
