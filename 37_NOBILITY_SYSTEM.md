# ELDORIA WORLD — NOBILITY & TITLE SYSTEM

> **Module:** 37 — Nobility & Title System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Phase:** WORLD DEVELOPMENT

## 1. Purpose

Mendefinisikan struktur bangsawan Eldoria sebagai lapisan sosial, politik, teritorial, ekonomi, militer, dan magical yang terintegrasi dengan Empire, Kingdom, Faction, NPC, Law, Economy, Military, dan Magic.

Sistem ini menetapkan framework dan authority rules. Gelar, Noble House, domain, hubungan keluarga, hak istimewa, dan institusi spesifik harus Canonized secara terpisah sebelum menjadi fakta dunia.

## 2. Core Separation

Konsep berikut tidak boleh disamakan:

```text
NOBLE TITLE
≠ POLITICAL AUTHORITY
≠ TERRITORIAL CONTROL
≠ MILITARY POWER
≠ WEALTH
≠ MAGICAL POWER
≠ FACTION INFLUENCE
```

Memiliki gelar tidak otomatis memberikan seluruh bentuk kekuasaan tersebut. Authority harus berasal dari hukum, jabatan, domain, faction, kontrak, atau sumber sah lainnya.

## 3. Nobility Architecture

Baseline hierarchy Eldoria:

```text
EMPEROR / EMPRESS
    ↓
IMPERIAL NOBILITY
    ↓
KING / QUEEN
    ↓
DUKE / DUCHESS
    ↓
MARQUIS / MARCHIONESS
    ↓
COUNT / COUNTESS
    ↓
VISCOUNT / VISCOUNTESS
    ↓
BARON / BARONESS
    ↓
KNIGHT / LANDED KNIGHT (jika diakui oleh hukum setempat)
```

Hierarchy ini adalah baseline framework, bukan klaim bahwa setiap tingkat telah memiliki individu atau house tertentu.

Kerajaan dapat memiliki variasi gelar, nomenklatur, fungsi, atau jalur kenaikan sendiri selama tidak bertentangan dengan hukum kekaisaran yang berlaku.

## 4. Title Identity

Gelar persisten yang Canonized dapat memiliki:

```text
TITLE_ID
TITLE_NAME
TITLE_TIER
AUTHORITY_SCOPE
GRANTING_AUTHORITY
SUCCESSION_RULE
LAND_REQUIREMENT
LEGAL_PRIVILEGES
MILITARY_OBLIGATION
TAX_OBLIGATION
MAGICAL_PRIVILEGES_OR_RESTRICTIONS
CURRENT_HOLDER
CURRENT_STATE
ORIGIN
HISTORY
```

Title kosong atau jabatan tanpa holder tidak boleh menghasilkan NPC secara otomatis.

## 5. Title Rules

### 5.1 Grant

Gelar harus memiliki granting authority yang sah, misalnya Emperor, King/Queen, atau authority lain yang diizinkan hukum lokal.

### 5.2 Succession

Gelar dapat diwariskan hanya menurut succession law yang berlaku. Gelar tidak otomatis berpindah karena hubungan darah tanpa resolution dan dasar hukum.

### 5.3 Revocation

Gelar dapat dicabut, diturunkan, dibekukan, atau dialihkan bila hukum dan resolution yang relevan mengizinkannya.

### 5.4 Title vs Office

```text
TITLE = status/gelar legal atau sosial
OFFICE = jabatan/fungsi pemerintahan
```

Satu NPC dapat memiliki keduanya, tetapi keduanya bukan hal yang sama.

### 5.5 Title vs Land

Gelar tidak otomatis berarti memiliki domain tertentu. Domain ownership/control harus ditetapkan secara terpisah.

## 6. Noble House

Noble House adalah persistent social/political entity yang dapat menjadi Faction dengan `TYPE = NOBLE_HOUSE`.

Noble House dapat memiliki:

```text
HOUSE_ID
NAME
FOUNDER / ORIGIN
CURRENT_HEAD
TITLE(S)
DOMAIN(S)
LINEAGE / SUCCESSION CONTEXT
ALLIED HOUSES
RIVAL HOUSES
FACTION RELATIONS
WEALTH SOURCES
MILITARY RESOURCES
MAGICAL ASSETS (jika ada)
GOALS
INTERESTS
CURRENT_STATE
HISTORY
```

Tidak semua anggota House memiliki gelar yang sama. Tidak semua anggota House memiliki authority yang sama.

House membership tidak otomatis memberikan title, inheritance, political office, wealth access, military command, magical capability, atau privileged knowledge.

## 7. Domain & Vassalage

Domain adalah wilayah atau asset yang secara legal/operasional terkait dengan title atau House.

Bedakan:

```text
OWNERSHIP
CONTROL
CLAIM
ADMINISTRATION
INFLUENCE
OCCUPATION
```

Hubungan feodal seperti liege/vassal, tribute, military obligation, dan administrative delegation harus memiliki dasar hukum atau political arrangement yang sah.

Tidak ada NPC yang memperoleh sovereignty hanya karena memiliki title.

## 8. Noble Privileges & Obligations

Hak dan kewajiban dapat mencakup:

- court access,
- legal privileges,
- taxation privileges,
- land administration,
- military service,
- levies,
- infrastructure duties,
- protection obligations,
- diplomatic representation,
- resource management.

Daftar tersebut adalah framework; privilege aktual harus ditentukan oleh hukum dan Canon lokal.

## 9. Nobility & Magic Integration

Magic merupakan capability layer terpisah dari status bangsawan.

Noble House dapat memiliki hubungan dengan magic melalui:

```text
MAGICAL LINEAGE
MAGE MEMBERS
COURT MAGES
MAGIC ACADEMIES
MAGICAL GUILDS
ARCANE ORDERS
MAGICAL TERRITORY
MAGICAL RESOURCES
ARTIFACTS
PACT / SUPERNATURAL RELATIONS
```

Namun:

```text
NOBLE TITLE ≠ MAGIC POWER
RACE ≠ MAGIC POWER
HOUSE MEMBERSHIP ≠ MAGIC ACCESS
```

Akses magic tetap mengikuti `09_MAGIC_SYSTEM.md`: access, prerequisite, resource, effect, limitation, origin, dan history harus valid.

## 10. Magical Resources & Political Power

Wilayah atau House yang menguasai sumber daya magis dapat memiliki economic atau political importance. Pengaruh tersebut tidak otomatis menjadi sovereignty.

Contoh resource/context yang dapat relevan:

- mana-rich territory,
- magical minerals,
- enchanted forests,
- magical waterways,
- ancient ruins,
- magical artifacts,
- magical trade routes.

Keberadaan dan sifat spesifiknya harus Canonized atau generated secara sah; tidak boleh diasumsikan hanya karena genre fantasy.

## 11. Magic Institutions & Nobility

Magic institution dapat berhubungan dengan Crown, Empire, Noble House, Guild, atau berdiri independen.

Hubungan dapat berupa:

```text
PATRONAGE
LICENSE
ALLIANCE
SERVICE
CONTRACT
NEUTRALITY
CONFLICT
```

Hubungan tersebut tidak memberikan authority otomatis di luar scope yang disepakati.

## 12. Kingdom-Specific Variation

Baseline nobility berlaku lintas Eldoria, tetapi setiap Kingdom dapat mengembangkan karakteristik berbeda berdasarkan geography, economy, culture, military, magic, dan history.

```text
VALEDORN   → agrarian / riverine nobility
BRANNOR    → highland / mineral / frontier nobility
MARISELLE  → maritime / coastal nobility
SYLVARAN   → forest / river / frontier nobility
SAHRAD     → arid / caravan / pastoral nobility
```

Label di atas adalah worldbuilding direction, bukan daftar House yang telah Canonized.

Kingdom-specific rules wajib ditetapkan sebelum House atau NPC bangsawan yang bergantung pada aturan tersebut dibuat.

## 13. Marriage, Family & Succession

Hubungan pasangan, anak, saudara, heir, cadet branch, dan royal/noble family adalah identity facts yang harus Canonized secara eksplisit.

```text
TITLE → tidak otomatis menciptakan spouse
TITLE → tidak otomatis menciptakan heir
HOUSE → tidak otomatis menentukan seluruh family tree
ROYAL STATUS → tidak otomatis berarti spouse/children exist
```

Selama WORLD DEVELOPMENT, Admin harus menyelesaikan hubungan keluarga yang diperlukan untuk membuat struktur Canon lengkap. Setelah `READY FOR GAMEPLAY`, fakta keluarga yang masih Unknown tidak boleh ditebak oleh AI GM.

## 14. Noble Faction Behavior

Jika Noble House menjadi faction, operational behavior mengikuti `19_FACTION_SYSTEM.md`.

House dapat:

- bernegosiasi,
- berdagang,
- merekrut,
- membentuk alliance,
- bersaing,
- mendukung claimant,
- mengelola domain,
- menggunakan military resources,
- mendukung atau membatasi magic institutions,
- merespons events.

Outcome tidak otomatis mengikuti kebutuhan Player atau narasi.

## 15. Canonization Gate

Noble Title atau Noble House yang akan menjadi Canon wajib memiliki authority yang jelas.

### Title

```text
TITLE_ID
NAME
TIER
GRANTING_AUTHORITY
AUTHORITY_SCOPE
SUCCESSION / REVOCATION BASIS
CURRENT_STATE
ORIGIN
HISTORY
```

### Noble House

```text
HOUSE_ID / FACTION_ID
NAME
TYPE = NOBLE_HOUSE
KINGDOM / EMPIRE SCOPE
CURRENT_HEAD
TITLE(S)
DOMAIN / INFLUENCE
GOALS
INTERESTS
CORE MEMBERSHIP CONTEXT
MAGICAL CONTEXT (jika relevan)
CURRENT_STATE
ORIGIN
HISTORY
```

## 16. Dynamic Nobility

Bangsawan yang belum Canon dapat muncul sebagai Dynamic NPC bila generation diizinkan dan konteks authority tersedia.

Dynamic NPC tidak menjadi Canon hanya karena muncul, dan tidak boleh contradict Canon Noble House, title, succession, law, atau governance.

Jika menjadi material, persistence mengikuti `16_NPC_SYSTEM.md` dan state pipeline.

## 17. Resolution & Persistence

Perubahan title, succession, domain, House leadership, noble relationship, privilege, atau political authority harus melalui:

```text
INTENT / TRIGGER
↓
LOAD GOVERNANCE + NOBILITY + FACTION + MAGIC CONTEXT
↓
CHECK LAW / AUTHORITY / CAPABILITY / KNOWLEDGE
↓
RESOLVE
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 18. Dependencies

Core:

`01_WORLD_OVERVIEW` + `02_REALMS_AND_REGIONS` + `03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS` + `09_MAGIC_SYSTEM` + `11_ECONOMY` + `13_COMBAT` + `16_NPC_SYSTEM` + `19_FACTION_SYSTEM` + `20_REPUTATION` + `25_WORLD_STATE` + `26_CHARACTER_STATE` + `27_NPC_STATE` + `30_HISTORY_SYSTEM` + `31_ORIGIN_LOG` + `32_MODULE_ROUTER` + `33_ACTION_RESOLVER` + `34_STATE_VALIDATOR` + `35_SAVE_PIPELINE` + `36_RACE_SYSTEM`.

## 19. Development Gate

Selama `WORLD DEVELOPMENT`:

- Admin wajib menyelesaikan unresolved Canon yang diperlukan untuk struktur dunia.
- `???` tidak boleh digunakan sebagai pengganti keputusan worldbuilding yang memang dibutuhkan.
- Canonization harus menghindari filler dan kontradiksi.

Sebelum `READY FOR GAMEPLAY`, audit wajib memastikan governance, nobility, magic integration, faction context, law, economy, military, history, dan entity references yang diperlukan telah memiliki dasar Canon yang memadai.

## 20. Final Principle

> **Bangsawan Eldoria adalah sistem sosial-politik yang berinteraksi dengan tanah, hukum, ekonomi, militer, faction, dan magic; gelar memberi status menurut hukum, bukan kekuatan otomatis.**
