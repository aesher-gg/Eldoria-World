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

Nama penguasa, kementerian, dewan, hukum spesifik, faction spesifik, hubungan politik spesifik, dan detail kekuasaan yang belum ditetapkan tetap `???`.

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
HEAD_OF_STATE: Kaisar Valthera
CENTRAL_AUTHORITY: Pemerintahan Kekaisaran
KINGDOM_AUTONOMY: Internal governance permitted within Imperial law
IMPERIAL_SCOPE: Pertahanan bersama, hukum kekaisaran, hubungan antar-kerajaan, kepentingan strategis, dan urusan yang ditetapkan oleh hukum kekaisaran
LOCAL_SCOPE: Pemerintahan kerajaan dan administrasi lokal berada pada kerajaan masing-masing sesuai hukum yang berlaku
```

Detail berikut tetap unresolved:

```text
PERSONAL_NAME_OF_EMPEROR: ???
IMPERIAL_MINISTRIES: ???
IMPERIAL_COUNCIL: ???
SPECIFIC_IMPERIAL_LAWS: ???
DETAILED_AUTHORITY_BOUNDARIES: ???
MILITARY_STRUCTURE: ???
ECONOMIC_STRUCTURE: ???
CULTURAL_PROFILE: ???
RELIGIOUS_STRUCTURE: ???
MAJOR_IMPERIAL_FACTIONS: ???
EXTERNAL_RELATIONS: ???
```

### 2.2 Kingdom Governance — Canon Baseline

Kelima Kingdom berada di bawah hukum kekaisaran dan memiliki otonomi pemerintahan internal.

```text
KINGDOM-001: Kerajaan otonom di bawah hukum kekaisaran
KINGDOM-002: Kerajaan otonom di bawah hukum kekaisaran
KINGDOM-003: Kerajaan otonom di bawah hukum kekaisaran
KINGDOM-004: Kerajaan otonom di bawah hukum kekaisaran
KINGDOM-005: Kerajaan otonom di bawah hukum kekaisaran
```

Detail berikut belum ditetapkan per Kingdom dan tetap `???` sampai Canonized:

```text
RULER / RULING HOUSE
GOVERNMENT BODY
SUCCESSION LAW
LOCAL LAW
MILITARY COMMAND
TAX / REVENUE STRUCTURE
MAJOR NOBLE HOUSES
MAJOR POLITICAL BLOCS
MAJOR FACTIONS
KINGDOM-TO-KINGDOM RELATIONS
```

---

## 3. Governance Scope Matrix

| Scope | Authority baseline | Known | Unresolved |
|---|---|---|---|
| Empire | Imperial central authority + defined imperial scope | Political system and broad scope | Ruler name, institutions, laws, military, economy, factions |
| Kingdom | Internal autonomy under Imperial law | Autonomy baseline | Rulers, institutions, laws, military, factions |
| Region | Parent kingdom administration | Parent hierarchy | Regional offices/authority = ??? |
| City | Parent kingdom/local administration | Parent hierarchy | City government/offices = ??? |
| Settlement | Local administration under parent hierarchy | Parent hierarchy | Local offices/authority = ??? |

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
CORE_RELATIONSHIPS → must not contradict established political structure
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

1. Empire memiliki authority pada scope yang telah ditetapkan Canon.
2. Kingdom memiliki internal governance autonomy dalam batas hukum kekaisaran.
3. Lower-level authority tidak boleh mengklaim kewenangan yang belum ditetapkan.
4. Faction influence tidak sama dengan sovereignty.
5. Claim, control, influence, dan occupation tetap konsep berbeda.
6. Membership tidak otomatis memberikan authority.
7. NPC position does not automatically imply access to information, resources, or decision-making power.
8. Material political changes wajib melalui resolution dan persistence.

---

## 9. Canonization Gate for Specific Factions

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

## 10. Relationship to NPC Coverage Matrix

`npcs/COVERAGE_MATRIX.md` menentukan kebutuhan coverage NPC.

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

## 11. Current Phase

```text
GEOGRAPHY CANON: COMPLETE
POPULATION MODEL: ACTIVE
NPC ARCHITECTURE: COMPLETE
NPC COVERAGE MATRIX: COMPLETE
GOVERNANCE BASELINE: ESTABLISHED
FACTION FRAMEWORK: ESTABLISHED
SPECIFIC FACTION CANON: PENDING
INDIVIDUAL CANON NPC: NOT STARTED
```

---

## 12. Final Principle

> **Governance dan faction menyediakan konteks authority dan kepentingan; NPC dibangun dari konteks tersebut, bukan sebaliknya. `???` tidak boleh diisi hanya untuk membuat NPC terlihat lengkap.**
