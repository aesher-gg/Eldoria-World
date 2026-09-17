# Eldoria World — Items / Equipment System v0.1

> **Module:** Items / Equipment  
> **Version:** v0.1  
> **Authority:** Official Canon  
> **Role:** World System

## 1. Purpose

Items / Equipment adalah canonical owner untuk entitas benda yang dapat memiliki identitas, State, hubungan possession/ownership, digunakan, dikenakan, dipasang, dipindahkan, disimpan, berubah kondisi, hilang, dihancurkan, atau menjalani lifecycle lain yang sah menurut Canon.

Modul ini mengisi kebutuhan Item dan Equipment yang sudah dirujuk oleh Character Data Model tanpa mengambil alih domain Combat, Economy, Travel, Health, Supernatural / Magic, State & History, atau Persistence.

Modul ini mendefinisikan **framework dan semantics inti**, bukan katalog item, stat universal, formula, loot table, crafting recipe, atau mekanik ekonomi universal.

## 2. Canonical Boundary

Items / Equipment adalah canonical owner untuk:

- Item identity;
- Item classification framework;
- Item properties framework;
- Item State yang spesifik terhadap keberadaan dan penggunaan Item;
- Equipment Context;
- possession / availability / location references yang diperlukan untuk merepresentasikan Item;
- condition concept;
- Item lifecycle;
- Item-related action semantics pada level domain;
- integrasi Item dengan domain lain;
- provenance dan History references yang relevan terhadap Item.

Items / Equipment bukan owner untuk:

- Character data structure secara keseluruhan;
- economic value, pricing, transaction, atau economic ownership rules;
- combat resolution;
- travel resolution;
- health resolution;
- supernatural / magic resolution;
- State & History semantics;
- State Validation;
- Persistence;
- generic Action identity atau generic Resolution architecture;
- crafting system;
- loot generation system;
- property / settlement management.

## 3. Core Distinctions

```text
ITEM
= entitas benda yang dapat memiliki identity dan State

EQUIPMENT
= context / State penggunaan Item sebagai perlengkapan

POSSESSION
= hubungan bahwa Item berada dalam penguasaan/possession suatu actor atau konteks

OWNERSHIP
= hubungan kepemilikan yang harus dibedakan dari possession dan control

LOCATION / STORAGE
= konteks keberadaan Item
```

```text
ITEM
≠ EQUIPMENT
≠ POSSESSION
≠ OWNERSHIP
≠ LOCATION
```

Equipment tidak otomatis menjadi entity terpisah dari Item. Pada v0.1, Equipment diperlakukan sebagai context / State penggunaan Item kecuali Canon lanjutan secara eksplisit membutuhkan model berbeda.

## 4. Item Identity

Item yang membutuhkan tracking atau persistence harus dapat dibedakan secara konsisten melalui identity yang sah.

Model konseptual:

```text
ITEM
├── Item ID
├── Identity
└── Metadata
```

Item ID adalah identity dan bukan penentu harga, kekuatan, kualitas, rarity, level, atau hasil gameplay.

Format Item ID belum dikunci oleh v0.1.

## 5. Item Classification

Item dapat memiliki classification sesuai kebutuhan dunia dan domain.

Framework konseptual dapat mencakup:

```text
ITEM
├── Weapon
├── Armor
├── Clothing
├── Tool
├── Consumable
├── Material
├── Document
├── Container
├── Magical / Supernatural Item
└── Other Canon-defined Type
```

Daftar tersebut bersifat framework, bukan exhaustive universal catalog. Item tidak boleh dipaksa masuk ke kategori yang tidak sesuai.

## 6. Item Properties

Item dapat memiliki properties yang relevan terhadap keberadaan atau penggunaannya.

```text
ITEM PROPERTIES
├── Physical Properties
├── Functional Properties
├── Usage Properties
├── Material Context
└── Other Canon-defined Properties
```

Properties yang belum didefinisikan oleh Canon harus tetap Unknown / Undefined.

Modul ini tidak menetapkan universal:

- damage value;
- armor value;
- weight;
- durability formula;
- rarity;
- quality tier;
- magical power;
- level requirement;
- item bonus formula.

## 7. Item State

Item yang relevan terhadap persistent simulation dapat memiliki Current State.

Model konseptual:

```text
ITEM STATE
├── Item Reference
├── Current Holder / Possession Reference (if applicable)
├── Current Location / Storage Reference (if applicable)
├── Equipment Status (if applicable)
├── Usage Status (if applicable)
├── Condition (if applicable)
├── Availability (if applicable)
└── Other Relevant State
```

Tidak semua Item wajib memiliki seluruh field tersebut.

Item State harus merepresentasikan keadaan yang benar-benar diketahui dan sah menurut Canon/State.

## 8. Equipment Context

Equipment merepresentasikan penggunaan Item sebagai perlengkapan.

```text
ITEM AVAILABLE
↓
EQUIP ACTION
↓
VALIDATION
↓
EQUIPMENT CONTEXT / STATE
```

Equipment Context dapat secara konseptual memuat:

```text
EQUIPMENT
├── Item Reference
├── Equipped By / User Reference
├── Placement / Position Context (if applicable)
├── Equipment Status
└── Relevant Usage Context
```

V0.1 tidak menetapkan universal equipment slot seperti Head, Chest, Main Hand, atau Off Hand.

## 9. Possession, Ownership, Control, and Location

Hubungan berikut harus dibedakan:

```text
OWNERSHIP
≠ POSSESSION
≠ CONTROL
≠ LOCATION
≠ EQUIPMENT
```

Item dapat berada dalam possession suatu actor tanpa sedang equipped. Ownership, possession, dan control dapat berbeda sesuai State dan domain yang relevan.

Economic ownership dan transaksi mengikuti Economy ketika aspek tersebut merupakan bagian dari proses ekonomi.

Items / Equipment menyediakan representasi Item dan reference hubungan yang diperlukan; modul lain tetap memiliki authority atas semantics domain masing-masing.

## 10. Item Condition

Condition adalah aspek State Item yang dapat berubah selama lifecycle.

```text
ITEM
↓
CONDITION CHANGE
↓
NEW ITEM STATE
```

Condition tidak menggunakan universal scale atau formula pada v0.1.

Contoh seperti damaged, broken, repaired, atau kondisi lain hanya dapat digunakan bila didukung oleh State/Canon yang relevan dan tidak menjadi exhaustive enum tanpa desain lebih lanjut.

## 11. Item Lifecycle

Lifecycle konseptual:

```text
CREATION / EXISTENCE
        ↓
ACQUISITION
        ↓
POSSESSION / STORAGE
        ↓
USE / EQUIP
        ↓
STATE CHANGE
        ↓
TRANSFER / STORE / DROP
        ↓
LOSS / DESTRUCTION / RETIREMENT
```

Lifecycle tidak harus melewati seluruh tahap. Urutan aktual ditentukan oleh action, event, domain rules, dan State yang berlaku.

## 12. Item-Related Actions

Item-related actions diproses melalui Action Model dan Resolution Architecture.

Contoh domain action secara konseptual:

```text
EQUIP
UNEQUIP
USE
TRANSFER
DROP
PICK UP
STORE
RETRIEVE
REPAIR
DISCARD
```

Daftar tersebut bukan universal action list yang memaksa semua Item mendukung semua operasi.

Boundary runtime:

```text
INTENT
↓
ACTION MODEL
↓
ITEM ACTION VALIDATION
↓
RESOLUTION ARCHITECTURE
↓
ITEM / RELEVANT DOMAIN RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
```

## 13. Use Item

Penggunaan Item tidak otomatis menghasilkan satu jenis consequence universal.

```text
USE ITEM
↓
VALIDATION
↓
RESOLUTION
↓
RESULT
↓
RELEVANT DOMAIN CONSEQUENCE
```

Contoh integrasi konseptual:

```text
Potion
↓
Use Item
↓
Health consequence
↓
Health & Injury
```

```text
Tool
↓
Use Item
↓
Crafting process
↓
Crafting system (future)
```

```text
Magical Item
↓
Use Item
↓
Supernatural consequence
↓
Supernatural / Magic
```

Items / Equipment tidak mengambil alih resolution domain tersebut.

## 14. Combat Integration

Combat dapat menggunakan Item / Equipment sebagai bagian dari Combat Context.

```text
ITEMS / EQUIPMENT
↓
COMBAT CONTEXT
↓
COMBAT RESOLUTION
↓
CONSEQUENCE
```

Items / Equipment menyediakan fakta Item yang relevan. Combat menentukan outcome combat sesuai Combat Canon.

Penggunaan suatu Item tidak otomatis berarti success, damage tertentu, atau combat advantage tertentu.

## 15. Travel Integration

Travel dapat menggunakan Item, equipment, transport, atau resource sebagai bagian dari Travel Context bila relevan.

```text
ITEM / EQUIPMENT
↓
TRAVEL CONTEXT
↓
TRAVEL RESOLUTION
```

Travel & Movement tetap menjadi authority untuk movement resolution dan temporal/travel consequences yang relevan.

## 16. Health Integration

Item dapat menjadi sarana tindakan yang memiliki consequence terhadap Health.

```text
ITEM USE
↓
ITEM / RELEVANT RESOLUTION
↓
HEALTH CONSEQUENCE
↓
HEALTH & INJURY
```

Items / Equipment tidak menetapkan universal healing amount, injury formula, atau health duration.

## 17. Economy Integration

Item dapat menjadi subject atau object dalam proses ekonomi.

```text
ITEM
↓
ECONOMIC CONTEXT
↓
TRANSACTION / VALUE / OWNERSHIP PROCESS
↓
ECONOMY
```

Items / Equipment tidak menetapkan harga atau economic value universal.

Economy tetap memiliki authority atas transaction dan economic rules.

## 18. Supernatural / Magic Integration

Item dapat memiliki properties atau capabilities supernatural apabila didefinisikan oleh Canon Magic.

```text
ITEM
↓
SUPERNATURAL CONTEXT
↓
SUPERNATURAL / MAGIC RESOLUTION
```

Items / Equipment tidak membuat universal mana, spell, magical tier, magical power, atau magic cost.

## 19. Character Integration

Character Data Model menggunakan Item melalui:

```text
CHARACTER
├── Equipment
└── Possessions
```

Items / Equipment menyediakan semantics untuk Item/Equipment tersebut, sedangkan Character Data Model tetap menjadi owner struktur data Character secara keseluruhan.

Perubahan Character equipment/possession dan Item State harus dapat direkonsiliasi sebagai State Changes yang konsisten.

## 20. State & History Integration

Perubahan Item adalah State Change bila perubahan tersebut mengubah persistent State.

```text
ITEM ACTION / EVENT
↓
RESULT
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY
↓
PERSISTENCE
↓
VERIFY
```

Item-related State Changes harus mengikuti State & History Model untuk:

- Previous Value;
- New Value;
- Origin;
- Source;
- World Time;
- Validation Status;
- History reference bila relevan.

Items / Equipment tidak mengambil alih semantics State atau History.

## 21. Multi-Entity Changes

Satu Item operation dapat menghasilkan perubahan pada lebih dari satu entity.

Contoh transfer:

```text
TRANSFER ITEM X
↓
RESULT
↓
CHANGE A
Holder / possession of Character A → changed

CHANGE B
Holder / possession of Character B → changed
↓
VALIDATE CHANGE SET
↓
PERSIST
↓
VERIFY
```

Perubahan yang saling bergantung harus diperlakukan sebagai Change Set yang konsisten sesuai State Validation dan Persistence.

## 22. Knowledge Boundary

Item information harus mengikuti knowledge boundary Eldoria.

```text
CANON ITEM DATA
≠ CHARACTER KNOWLEDGE
≠ PLAYER KNOWLEDGE
≠ NPC KNOWLEDGE
```

Keberadaan Item tidak berarti actor otomatis mengetahui seluruh properties, condition, origin, atau capabilities Item tersebut.

## 23. Unknown / Undefined

Informasi Item yang belum tersedia harus dipertahankan sebagai:

```text
UNKNOWN / UNDEFINED
```

Tidak boleh diganti secara otomatis dengan:

```text
ZERO
DEFAULT
NONE
AVERAGE
ASSUMED VALUE
```

Contoh:

```text
Weight = UNKNOWN
Durability = UNDEFINED
Economic Value = UNKNOWN
Magical Effect = UNKNOWN
```

Status tersebut hanya dapat berubah ketika sumber Canon, State, Resolution, atau informasi sah lainnya tersedia.

## 24. Provenance

Perubahan penting terhadap Item harus dapat ditelusuri melalui Origin / Source yang sesuai.

Contoh sumber konseptual:

```text
ACQUISITION
TRANSFER
CRAFTING
REPAIR
COMBAT
ENVIRONMENTAL EVENT
MAGICAL EVENT
OTHER VALID PROCESS
```

Daftar tersebut bukan exhaustive source catalog.

Item provenance tidak menggantikan State Change provenance atau History semantics.

## 25. Autonomous / World Changes

Item State dapat berubah akibat autonomous world process atau event jika proses tersebut mempunyai basis yang sah.

```text
WORLD / EVENT PROCESS
↓
ITEM CONSEQUENCE
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY
↓
PERSISTENCE
```

Item State tidak boleh berubah hanya untuk memajukan plot atau menghukum Player.

## 26. No Forced Outcome

Item action mengikuti prinsip umum:

```text
INTENT
≠ ACTION
≠ RESULT
≠ STATE CHANGE
```

Memiliki atau menggunakan Item tidak menjamin hasil tertentu.

Validasi Item hanya menentukan apakah proses dapat diproses berdasarkan kondisi yang tersedia; validasi tidak menjamin resolution success.

## 27. Error, Failure, and Unresolved

Item action harus mempertahankan perbedaan antara:

```text
INVALID ACTION
≠ GAMEPLAY FAILURE
≠ RESOLUTION UNRESOLVED
```

Failure adalah outcome gameplay yang sah.

Unresolved menunjukkan rule/data/engine yang diperlukan belum tersedia atau tidak dapat diproses, bukan otomatis berarti Item atau actor gagal.

## 28. Future Systems

Items / Equipment v0.1 menjadi fondasi untuk kemungkinan sistem berikutnya:

```text
CRAFTING
LOOT
INVENTORY MECHANICS
PROPERTY / STORAGE
ADVANCED EQUIPMENT
ITEM GENERATION
ITEM ECONOMY EXTENSIONS
MAGICAL ITEM EXTENSIONS
```

Sistem-sistem tersebut tidak menjadi bagian v0.1 kecuali telah memiliki Canon tersendiri.

## 29. Explicit Non-Goals v0.1

Modul ini tidak menetapkan:

- universal item damage;
- universal armor value;
- universal weight;
- universal durability formula;
- universal inventory slot;
- universal carrying capacity formula;
- universal rarity;
- universal quality tier;
- universal item price;
- universal item bonus;
- universal magical power;
- universal level requirement;
- loot tables;
- crafting recipes;
- merchant catalogs;
- fixed item catalog.

## 30. Runtime Integration

```text
PLAYER / NPC / WORLD INPUT
↓
INTENT
↓
ACTION MODEL
↓
ITEM ACTION VALIDATION
↓
RESOLUTION ARCHITECTURE
↓
ITEM / RELEVANT DOMAIN RESOLUTION
↓
RESULT
↓
CONSEQUENCES
↓
STATE CHANGE
↓
STATE VALIDATION
↓
HISTORY
↓
PERSISTENCE
↓
VERIFY
↓
RESPONSE
```

Item operations generated by Events or autonomous processes may enter melalui Event Processor / NPC-Faction Simulation / relevant autonomous process before mengikuti domain resolution dan State pipeline.

## 31. Canonical Ownership Matrix

| Concept | Canonical Owner |
|---|---|
| Item identity | Items / Equipment |
| Item classification | Items / Equipment |
| Item properties framework | Items / Equipment |
| Item State | Items / Equipment |
| Equipment Context | Items / Equipment |
| Item condition concept | Items / Equipment |
| Item lifecycle | Items / Equipment |
| Possession representation | Items / Equipment |
| Economic value | Economy |
| Economic transaction | Economy |
| Combat outcome | Combat |
| Health consequence | Health & Injury |
| Travel outcome | Travel & Movement |
| Supernatural mechanism | Supernatural / Magic |
| Character structure | Character Data Model |
| State semantics | State & History |
| State validation | State Validation |
| Persistence | Persistence |
| Action representation | Action Model |
| Generic resolution contract | Resolution Architecture |

## 32. Integrity Rules

- Item identity tidak menentukan gameplay outcome.
- Item ≠ Equipment ≠ Possession ≠ Ownership ≠ Location.
- Equipment v0.1 adalah context / State penggunaan Item, bukan entity terpisah secara default.
- Character Data Model tetap menjadi owner struktur Character.
- Economy tetap menjadi owner economic value dan transaction.
- Combat tetap menjadi owner combat resolution.
- Travel tetap menjadi owner travel resolution.
- Health & Injury tetap menjadi owner health resolution.
- Supernatural / Magic tetap menjadi owner supernatural resolution.
- Action Model tetap menjadi owner generic Action representation.
- Resolution Architecture tetap menjadi generic resolution contract.
- State & History tetap menjadi owner State/History semantics.
- State Validation tetap menjadi validation gate.
- Persistence tetap menjadi persistence layer.
- Unknown / Undefined tidak boleh diisi dengan fallback.
- Tidak ada universal item formula pada v0.1.
- Item action tidak menjamin success.
- Narrative tidak otomatis menjadi Item State.
- Autonomous Item State changes harus memiliki basis yang sah.
- Item-related State Changes harus memiliki provenance yang dapat ditelusuri ketika relevan.
- Multi-entity Item changes harus tetap konsisten setelah validation dan persistence.

## 33. Dependencies

Items / Equipment menggunakan atau berintegrasi dengan:

```text
core/CORE_RULES.md
core/ACTION_MODEL.md
core/RESOLUTION_ARCHITECTURE.md
core/WORLD_EVENT_PROCESSOR.md
core/NPC_FACTION_SIMULATION.md
characters/CHARACTER_DATA_MODEL.md
state/STATE_AND_HISTORY_MODEL.md
core/STATE_VALIDATION.md
core/PERSISTENCE.md
systems/TIME_AND_CALENDAR.md
systems/COMBAT.md
systems/TRAVEL_AND_MOVEMENT.md
systems/HEALTH_AND_INJURY.md
world/ECONOMY.md
world/SUPERNATURAL_MAGIC.md
```

Dependency tidak berarti Items / Equipment mengambil alih semantics domain-domain tersebut.

## 34. Future Extensions

```text
INVENTORY MODEL
ITEM GENERATION
DURABILITY / REPAIR MECHANICS
QUALITY MODEL
RARITY MODEL
CONTAINER / STORAGE MODEL
EQUIPMENT SLOT MODEL
CRAFTING INTEGRATION
LOOT INTEGRATION
ITEM SERIALIZATION
ADVANCED ITEM EFFECTS
```

Ekstensi tersebut harus melalui audit dependency dan ownership sebelum menjadi Canon.
