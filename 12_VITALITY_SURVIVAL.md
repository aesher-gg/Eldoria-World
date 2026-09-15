# ELDORIA WORLD — VITALITY & SURVIVAL

> **Module:** 12 — Vitality & Survival
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan kondisi fisik dan kebutuhan survival karakter/creature sebagai state yang memengaruhi resolution.

## 2. Vitality State

Implementasi dapat menggunakan:

```text
HP / HEALTH
STAMINA / FATIGUE
HUNGER / SATIETY
THIRST
SLEEP / REST
INJURY
CONDITION
```

Nama field, unit, cap, floor, dan formula aktual harus berasal dari schema/module yang sah.

## 3. No Universal Numbers

Module ini tidak menetapkan angka default untuk HP, stamina, hunger, thirst, recovery, atau kebutuhan survival tanpa basis Canon.

`???` berarti Unknown/Unresolved dan tidak boleh diganti dengan tebakan.

## 4. Damage & Recovery

Perubahan vitality dapat berasal dari:

- combat,
- environment,
- disease/poison,
- exertion,
- hunger/thirst,
- rest,
- healing,
- magic,
- item,
- event,
- atau cause sah lainnya.

Semua perubahan material menghasilkan State Delta yang tervalidasi.

## 5. Conditions & Injuries

Condition dapat berupa temporary atau persistent.

Injury harus memiliki severity/status yang dapat dilacak bila material.

Condition tidak boleh hilang hanya karena narasi menyatakan karakter sudah pulih.

## 6. Survival Environment

Survival dipengaruhi context seperti:

- weather,
- temperature,
- terrain,
- shelter,
- food,
- water,
- equipment,
- exposure,
- travel,
- dan time.

Effects spesifik harus ditentukan oleh rules/resolution yang tersedia.

## 7. Rest & Recovery

Recovery membutuhkan kondisi dan waktu yang relevan bila rules mengharuskannya.

No free heal.

Rest tidak otomatis menyembuhkan semua injury atau condition.

## 8. Death Boundary

Jika vitality mencapai kondisi death sesuai rules yang berlaku, Character State harus berubah secara sah menjadi `DEAD` atau status equivalent.

Death adalah state persisten, bukan efek naratif sementara.

## 9. Resource Interaction

Vitality dapat berinteraksi dengan equipment, magic, skills, attributes, economy, crafting, alchemy, dan combat.

## 10. Information Boundary

Karakter/NPC tidak otomatis mengetahui angka atau severity internal entity lain. Observable condition dan hidden state harus dibedakan.

## 11. Validation

Validator memeriksa:

- valid domain/range,
- condition consistency,
- effect duration,
- Cause + Origin,
- state version,
- death/revival legality,
- `TURN_ID`.

## 12. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY` → module ini.

Integrasi: `09_MAGIC_SYSTEM`, `13_COMBAT`, `14_MONSTER_ECOSYSTEM`, `16_NPC_SYSTEM`, `22_ALCHEMY`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `34_STATE_VALIDATOR`.

## 13. Canon Safety

Tidak ada angka survival universal, healing rate, atau injury table tetap yang boleh diciptakan tanpa source yang sah.

## 14. Final Principle

> **Vitality dan survival adalah state nyata yang berubah karena sebab nyata, membutuhkan waktu/condition yang relevan, dan tidak boleh dipulihkan secara gratis.**
