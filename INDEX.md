# ELDORIA WORLD — INDEX

> **ELDORIA CANON v1.0 — LOCKED**
> 
> Official runtime navigation and module loading contract.

## 1. PURPOSE

`INDEX.md` adalah entry point runtime Eldoria. AI GM wajib menggunakannya untuk menentukan sumber Canon dan module yang relevan sebelum melakukan state/action resolution.

Repository adalah **official source of truth**.

## 2. AUTHORITY

### Rule Authority

```text
ELDORIA CANON
→ 00_CORE_RULES.md
→ SYSTEM MODULES
```

### Data Authority

```text
WORLD_STATE
CHARACTER_STATE
NPC_STATE
MONSTER_STATE
QUEST_STATE
EVENT_STATE
↓
HISTORY / ORIGIN
```

Narrative bukan authority layer.

## 3. RUNTIME CONTRACT

Setiap Player Message = satu **Turn Transaction**.

Runtime wajib:

1. Membuat `TURN_ID` unik.
2. Fetch/verify `INDEX.md` sebelum resolution.
3. Memuat state terbaru yang relevan.
4. Memeriksa `STATE_VERSION`.
5. Menentukan intent/action.
6. Memuat module melalui Module Router.
7. Menyelesaikan aksi melalui Action Resolver.
8. Menghasilkan State Delta.
9. Memvalidasi delta.
10. Menghasilkan History/Origin record.
11. Melakukan atomic commit + persistence.
12. Baru kemudian menghasilkan narrative output.

```text
PLAYER MESSAGE
↓
TURN_ID
↓
INDEX VERIFY
↓
CURRENT STATE
↓
STATE_VERSION CHECK
↓
INTENT
↓
MODULE ROUTER
↓
ACTION RESOLVER
↓
STATE DELTA
↓
STATE VALIDATOR
↓
HISTORY + ORIGIN
↓
ATOMIC PERSISTENCE
↓
NARRATIVE
```

## 4. CORE FILES

| File | Fungsi |
|---|---|
| `README.md` | Identitas dan gambaran repository |
| `INDEX.md` | Runtime entry point dan module routing |
| `00_CORE_RULES.md` | Aturan inti AI GM dan simulation contract |

## 5. CANON & WORLD

| Module | Scope |
|---|---|
| `01_WORLD_OVERVIEW.md` | Identitas dan fondasi dunia |
| `02_REALMS_AND_REGIONS.md` | Realm, wilayah, geografi |
| `03_CITIES_AND_SETTLEMENTS.md` | Kota dan settlement |
| `04_FACTIONS.md` | Faksi dan struktur kekuasaan |

## 6. CHARACTER & PROGRESSION

| Module | Scope |
|---|---|
| `05_CHARACTER_SYSTEM.md` | Struktur karakter |
| `06_ATTRIBUTES.md` | Atribut dan statistik |
| `07_CLASSES.md` | Class/profession/archetype |
| `08_SKILLS.md` | Skill dan proficiency |
| `09_MAGIC_SYSTEM.md` | Sistem magic |

## 7. PHYSICAL SYSTEMS

| Module | Scope |
|---|---|
| `10_EQUIPMENT_SYSTEM.md` | Equipment dan item state |
| `11_ECONOMY.md` | Mata uang, harga, transaksi |
| `12_VITALITY_SURVIVAL.md` | HP, stamina, hunger, survival |
| `13_COMBAT.md` | Combat resolution |

## 8. LIVING WORLD

| Module | Scope |
|---|---|
| `14_MONSTER_ECOSYSTEM.md` | Ekologi dan dynamic monster generation |
| `15_LOOT_GENERATION.md` | Dynamic loot generation |
| `16_NPC_SYSTEM.md` | NPC agency, identity, needs, behavior |
| `17_QUEST_SYSTEM.md` | Quest generation dan state |
| `18_WORLD_EVENTS.md` | World event dan konsekuensi |
| `19_FACTION_SYSTEM.md` | Faction behavior dan perubahan |
| `20_REPUTATION.md` | Reputation dan social consequences |

## 9. CREATION & SOCIAL SYSTEMS

| Module | Scope |
|---|---|
| `21_CRAFTING.md` | Crafting |
| `22_ALCHEMY.md` | Alchemy |
| `23_PARTY_SYSTEM.md` | Party dan group dynamics |
| `24_PETS_AND_COMPANIONS.md` | Pets dan companions |

## 10. STATE & PERSISTENCE

| Module | Scope |
|---|---|
| `25_WORLD_STATE.md` | Persistent shared world state |
| `26_CHARACTER_STATE.md` | Persistent character state |
| `27_NPC_STATE.md` | Persistent NPC state |
| `28_MONSTER_STATE.md` | Persistent monster state |
| `29_EVENT_STATE.md` | Persistent event state |
| `30_HISTORY_SYSTEM.md` | Append-only historical record |
| `31_ORIGIN_LOG.md` | Source/cause/origin tracking |

## 11. RUNTIME ENGINE

| Module | Scope |
|---|---|
| `32_MODULE_ROUTER.md` | Menentukan module yang wajib dimuat |
| `33_ACTION_RESOLVER.md` | Resolve action → outcome → State Delta |
| `34_STATE_VALIDATOR.md` | Memeriksa validitas State Delta |
| `35_SAVE_PIPELINE.md` | Atomic persistence, versioning, recovery |

## 12. STATE RULES

### `???`

`???` berarti **Unknown / Unresolved**.

`???` bukan:

- zero
- empty
- false
- N/A
- error
- izin untuk menebak

### State Version

Setiap persistent state harus memiliki `STATE_VERSION` atau mekanisme ekuivalen.

### Turn ID

Setiap transaction harus memiliki `TURN_ID` unik dan idempotent.

### State Delta

Perubahan harus direpresentasikan sebagai delta yang dapat divalidasi sebelum commit.

## 13. DYNAMIC ENTITY RULE

Monster, NPC, loot, quest, event, dan entitas lain boleh dihasilkan secara dinamis jika diizinkan module terkait.

Jika hasil generation menjadi material bagi gameplay, entitas harus memperoleh identity/state yang persisten sehingga runtime tidak membuat entitas baru untuk menggantikan entitas lama.

Generation harus memiliki Origin dan informasi deterministik yang memadai untuk menjaga continuity.

## 14. INFORMATION STATE

Runtime harus membedakan:

- World Knowledge
- Character Knowledge
- NPC Knowledge
- Player Knowledge

Apa yang diketahui Player tidak otomatis menjadi fakta yang diketahui Character atau NPC.

## 15. TIME

World Time adalah data terstruktur dan harus dibedakan dari Local Environment.

```text
Era
Year
Season
Date
Day
Weather
Hour
```

Travel/action yang menghabiskan waktu harus menghasilkan time delta sebelum state waktu berikutnya digunakan untuk resolution lanjutan.

## 16. FAILURE / RECOVERY

Atomic persistence wajib menjaga konsistensi State + History + Origin.

Jika resolution, validation, persistence, atau version check gagal:

```text
REJECT / ROLLBACK
↓
NO PARTIAL STATE
↓
NO FALSE HISTORY
↓
NO FALSE ORIGIN
↓
RELOAD LATEST STATE IF REQUIRED
↓
RETRY / RE-RESOLVE / ABORT
```

Transaction lama tidak boleh menimpa state yang lebih baru.

## 17. NARRATIVE RULE

AI GM wajib mengikuti:

> **Simulate Before Narrate.**

Narrative hanya boleh menyatakan hasil yang telah:

- resolved,
- validated,
- committed,
- dan dipersistenkan.

## 18. REQUIRED LOADING BEHAVIOR

Pada setiap turn, AI GM harus memuat `INDEX.md` terlebih dahulu, kemudian hanya module/state/history yang relevan terhadap aksi dan konsekuensinya.

Jangan menganggap module telah dimuat hanya karena pernah digunakan pada turn sebelumnya.

## 19. CANON VERSIONING

Fondasi saat ini:

**ELDORIA CANON v1.0 — LOCKED**

Perubahan prinsip fundamental harus menghasilkan versi Canon baru. Module tidak boleh diam-diam mengubah prinsip Canon.
