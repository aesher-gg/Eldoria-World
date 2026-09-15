# ELDORIA WORLD — SKILLS

> **Module:** 08 — Skills
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan skill sebagai capability yang dapat dipelajari, digunakan, berkembang, dan memengaruhi resolution sesuai aturan yang sah.

## 2. Skill Identity

Skill persisten dapat memiliki:

```text
SKILL_ID
NAME
DOMAIN
PROFICIENCY
PREREQUISITES
EFFECTS / CAPABILITIES
ORIGIN
HISTORY
```

## 3. Skill State

Proficiency adalah state karakter, bukan sekadar label naratif.

Nilai, tier, rank, atau mastery tidak boleh diasumsikan bila belum didefinisikan oleh system yang berlaku.

## 4. Acquisition

Skill dapat diperoleh melalui mekanisme seperti:

- training,
- practice,
- teaching,
- class,
- faction,
- discovery,
- item,
- magic,
- atau generation yang sah.

Acquisition harus menghasilkan Cause + Origin + State Change + History bila menjadi perubahan persisten.

## 5. Use in Resolution

Skill dapat memengaruhi:

- available action,
- probability,
- difficulty,
- quality,
- efficiency,
- detection,
- crafting,
- combat,
- social interaction,
- atau domain lain.

Efek spesifik harus ditentukan oleh skill definition/module terkait.

## 6. Practice & Progression

Practice tidak menjamin peningkatan.

Progression harus menggunakan mekanisme yang sah dan mempertimbangkan action, difficulty, repetition, feedback, condition, dan rules yang berlaku.

Tidak ada free skill gain hanya karena Player meminta.

## 7. Temporary Effects

Skill dapat berinteraksi dengan temporary modifiers dari equipment, condition, environment, magic, atau effect lain.

Temporary modifier tidak boleh menjadi permanent skill progression tanpa resolution yang sah.

## 8. Knowledge Boundary

Memiliki skill tidak berarti otomatis memiliki seluruh pengetahuan terkait. Character Knowledge dan Information State tetap berlaku.

## 9. Dynamic Skills

Skill baru dapat dihasilkan bila system mengizinkannya. Jika menjadi material dan persisten, skill harus memperoleh stable identity/definition serta origin dan history yang diperlukan.

## 10. Validation

Validator harus memeriksa:

- skill identity,
- prerequisites,
- proficiency domain,
- legal acquisition,
- valid modifier,
- state version,
- Cause + Origin,
- `TURN_ID`.

## 11. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` → module ini.

Integrasi utama: `09_MAGIC_SYSTEM`, `10_EQUIPMENT_SYSTEM`, `13_COMBAT`, `16_NPC_SYSTEM`, `21_CRAFTING`, `22_ALCHEMY`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`.

## 12. Canon Safety

Module ini mendefinisikan framework skill, bukan katalog skill tetap atau formula progression universal.

## 13. Final Principle

> **Skill adalah capability yang diperoleh dan berkembang melalui proses yang valid; penggunaan skill memengaruhi resolution, bukan menjamin outcome.**
