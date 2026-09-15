# ELDORIA WORLD — EQUIPMENT SYSTEM

> **Module:** 10 — Equipment System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan equipment, item identity, ownership/possession, condition, durability, effects, dan perubahan item sebagai state persisten.

## 2. Item Identity

Item yang material dan persisten wajib memiliki:

```text
ITEM_ID
NAME
TYPE
QUALITY / TIER
CURRENT_STATE
ORIGIN
HISTORY
```

Item generik yang belum material dapat direpresentasikan secara non-persisten sesuai kebutuhan runtime.

## 3. Equipment State

State dapat mencakup:

```text
OWNER / POSSESSOR
LOCATION
EQUIPPED_BY
CONDITION
DURABILITY
EFFECTS
RESTRICTIONS
CHARGES
```

Field yang belum diketahui = `???`.

## 4. Possession vs Ownership

Possession tidak otomatis berarti legal ownership.

Ownership, possession, storage, lending, theft, confiscation, dan transfer adalah relationship/state yang dapat berbeda.

## 5. Equipment Slots

Slot equipment bersifat schema-driven. Tidak ada daftar slot universal yang dipaksakan jika belum didefinisikan oleh implementation.

## 6. Requirements & Restrictions

Equipment dapat memiliki requirement seperti attribute, class, skill, magic access, size, faction, compatibility, atau kondisi lain.

Requirement harus diperiksa sebelum equipment digunakan bila relevan.

## 7. Durability & Condition

Durability/condition dapat berubah karena:

- combat,
- usage,
- environment,
- crafting,
- repair,
- magic,
- damage,
- atau event lain.

Perubahan harus melalui resolution dan State Delta.

## 8. Item Effects

Effect item dapat memengaruhi character atau world sesuai definition.

Effect tidak boleh dibuat melebihi capability item yang authoritative.

## 9. Creation & Modification

Crafting, repair, enchantment, alchemy, destruction, atau modification mengikuti module terkait dan menghasilkan Origin + History bila material.

## 10. Loot Integration

Item yang diperoleh dari loot harus memiliki hubungan logis dengan source dan mengikuti `15_LOOT_GENERATION.md`.

## 11. Information Boundary

Character tidak otomatis mengetahui kualitas, efek tersembunyi, ownership, atau nilai item tanpa basis pengetahuan yang sah.

## 12. Validation

Validator memeriksa identity, ownership/possession consistency, requirements, condition, location/equipment consistency, state version, Cause, Origin, dan `TURN_ID`.

## 13. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` + `09_MAGIC_SYSTEM` → module ini.

Integrasi: `11_ECONOMY`, `12_VITALITY_SURVIVAL`, `13_COMBAT`, `15_LOOT_GENERATION`, `21_CRAFTING`, `22_ALCHEMY`, `34_STATE_VALIDATOR`.

## 14. Canon Safety

Module ini tidak menetapkan katalog senjata, armor, item magic, harga, atau statistik item tertentu sebagai fakta.

## 15. Final Principle

> **Item adalah entitas yang memiliki identity dan state; memperoleh, menggunakan, merusak, atau memindahkannya selalu memiliki konsekuensi yang dapat ditelusuri.**
