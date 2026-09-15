# ELDORIA WORLD — CLASSES

> **Module:** 07 — Classes
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan framework class, profession, archetype, atau role karakter tanpa memaksa satu sistem class tertentu ke seluruh dunia.

## 2. Class Identity

Class persisten dapat memiliki:

```text
CLASS_ID
NAME
TYPE
DESCRIPTION
PREREQUISITES
CAPABILITIES
RESTRICTIONS
ORIGIN
HISTORY
```

Field yang belum diketahui = `???`.

## 3. Flexible Model

Eldoria dapat menggunakan class formal, profession, archetype, vocation, atau kombinasi yang sah.

Character dapat memiliki satu atau lebih role hanya jika rules terkait mengizinkannya.

## 4. Acquisition

Class/profession harus diperoleh melalui mekanisme yang sah, misalnya:

- creation,
- training,
- apprenticeship,
- faction admission,
- quest,
- achievement,
- atau mekanisme lain yang ditentukan system.

Player tidak dapat menetapkan class sebagai fakta tanpa resolution.

## 5. Prerequisites

Prerequisite dapat mencakup:

- attributes,
- skills,
- level/progression,
- training,
- faction status,
- equipment,
- knowledge,
- atau kondisi lain.

Prerequisite aktual ditentukan oleh class definition yang sah.

## 6. Capabilities

Class dapat membuka akses terhadap skill, equipment, magic, training, service, atau opsi action tertentu.

Class tidak menjamin outcome action.

## 7. Restrictions

Class dapat memiliki batasan atau incompatibility.

Restriction harus berasal dari definition atau module terkait dan tidak boleh diciptakan secara convenience narrative.

## 8. Progression

Perubahan class, advancement, specialization, atau abandonment harus menghasilkan State Delta dan mengikuti progression rules yang relevan.

Tidak ada free promotion.

## 9. Multi-Class / Role Changes

Multi-class atau pergantian role hanya sah jika system mendukungnya.

Perubahan tidak menghapus History sebelumnya.

## 10. Dynamic Generation

Class/profession baru dapat dihasilkan secara dinamis bila generator mengizinkannya. Jika menjadi material, identity, origin, definition, dan state yang diperlukan harus dipersistenkan.

## 11. Information Boundary

Character/NPC tidak otomatis mengetahui seluruh class capabilities entity lain. Information State berlaku.

## 12. Validation

Validator harus memeriksa identity, prerequisites, incompatibilities, progression rules, state version, Cause, Origin, dan `TURN_ID`.

## 13. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` → module ini.

Integrasi utama: `08_SKILLS`, `09_MAGIC_SYSTEM`, `10_EQUIPMENT_SYSTEM`, `16_NPC_SYSTEM`, `19_FACTION_SYSTEM`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`.

## 14. Canon Safety

Module ini tidak membuat katalog class final. Class spesifik hanya authoritative jika tersedia melalui source yang sah atau generation yang dipersistenkan.

## 15. Final Principle

> **Class memberi struktur capability dan identity; ia tidak memberi kemenangan atau progression gratis.**
