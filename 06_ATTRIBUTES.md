# ELDORIA WORLD — ATTRIBUTES

> **Module:** 06 — Attributes
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan framework atribut karakter dan aturan perubahan atribut tanpa menetapkan angka statistik global yang belum ditentukan Canon.

## 2. Attribute Model

Attribute adalah nilai atau state yang merepresentasikan kemampuan karakter dalam domain tertentu.

Implementasi dapat menggunakan kategori seperti:

```text
PHYSICAL
MENTAL
SOCIAL
SENSORY
OTHER
```

Nama dan jumlah atribut aktual harus berasal dari schema yang ditetapkan implementasi atau sumber Canon yang sah.

## 3. Attribute State

Attribute persisten harus memiliki setidaknya:

```text
ATTRIBUTE_ID / NAME
VALUE
SOURCE / ORIGIN
CURRENT_STATE
HISTORY
```

Jika suatu atribut tidak tersedia atau belum diketahui, gunakan `???` sesuai Core Rules.

## 4. No Universal Default

Module ini tidak menetapkan nilai awal, cap, floor, growth rate, atau formula universal tanpa dasar Canon/module lanjutan.

`???` tidak boleh diganti dengan angka tebakan.

## 5. Derived Values

Nilai turunan dapat dihitung dari atribut dan state lain bila module terkait mendefinisikan formula.

Nilai turunan tidak boleh diperlakukan sebagai atribut independen kecuali schema menetapkannya demikian.

## 6. Modifiers

Modifier dapat berasal dari:

- equipment,
- condition,
- skill,
- class,
- magic,
- environment,
- injury,
- effect,
- atau source sah lainnya.

Modifier harus dapat ditelusuri ke Cause + Origin.

## 7. Attribute Change

Perubahan atribut harus mengikuti:

```text
CURRENT VALUE
↓
ACTION / EVENT / EFFECT
↓
RESOLUTION
↓
ATTRIBUTE DELTA
↓
VALIDATION
↓
ATOMIC PERSISTENCE
↓
HISTORY / ORIGIN
```

## 8. Temporary vs Persistent

Runtime harus membedakan modifier sementara dari perubahan permanen.

Temporary effect harus memiliki durasi atau termination condition jika relevan.

Permanent change harus memiliki resolution dan origin yang sah.

## 9. Dependency Integrity

Attribute tidak boleh berubah hanya karena narasi menyatakan karakter “menjadi lebih kuat”. Perubahan harus berasal dari sistem progression, training, effect, item, event, atau mekanisme lain yang valid.

## 10. Information Boundary

Nilai internal atribut tidak otomatis diketahui Character/NPC/Player. Disclosure mengikuti Information State.

## 11. Validation

Validator harus memeriksa:

- attribute dikenal oleh schema,
- value valid untuk domainnya,
- modifier memiliki source,
- prerequisite terpenuhi,
- tidak ada contradiction,
- state version valid,
- transaction belum committed.

## 12. Dependencies

`05_CHARACTER_SYSTEM` → module ini.

Integrasi utama: `07_CLASSES`, `08_SKILLS`, `09_MAGIC_SYSTEM`, `10_EQUIPMENT_SYSTEM`, `12_VITALITY_SURVIVAL`, `13_COMBAT`, `34_STATE_VALIDATOR`.

## 13. Canon Safety

Module ini mendefinisikan framework atribut, bukan menetapkan daftar statistik final atau angka balance yang belum dikunci.

## 14. Final Principle

> **Attribute adalah state terukur yang harus memiliki sumber, aturan perubahan, dan validasi; bukan angka bebas untuk memenuhi narasi.**
