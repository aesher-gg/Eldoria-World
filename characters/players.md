# Eldoria World — Player Registry

> **File:** `characters/players.md`  
> **Version:** v0.1  
> **Authority:** Official Player/Character Registry

## 1. Purpose

File ini adalah registry resmi untuk menghubungkan Player dengan Character yang telah didaftarkan dan divalidasi oleh Admin.

Registry digunakan untuk identifikasi dan boot/lookup dasar. Registry **bukan gameplay save**.

## 2. Registration Rule

Karakter tidak dapat memasuki gameplay sebagai karakter resmi sebelum:

```text
PLAYER
↓
NAME + CONCEPT + BACKGROUND
↓
ADMIN VALIDATION
↓
PLAYER ID + CHARACTER ID
↓
CHARACTER FILE
↓
REGISTRY
↓
READY
```

## 3. Required Registry Fields

Setiap entry resmi minimal menggunakan:

| Field | Purpose |
|---|---|
| Player ID | Identitas unik Player |
| Character ID | Identitas unik Character |
| Character Name | Nama karakter |
| Status | Status registrasi/gameplay |
| Character File | Referensi file karakter utama |

## 4. Identity Rules

- `Player ID` dan `Character ID` adalah identifier yang berbeda.
- `Character ID` harus unik.
- Satu Character tidak boleh memiliki lebih dari satu Character ID aktif untuk identitas yang sama tanpa keputusan Admin yang eksplisit.
- Registry tidak menyimpan Current State lengkap.
- Perubahan gameplay tidak ditulis sebagai detail State di registry.

## 5. Character File

Detail karakter disimpan pada:

```text
characters/players/<CHARACTER_ID>.md
```

Character File dapat memuat Identity, Background, Origin, Physical Profile, Attributes, Abilities, Equipment, Possessions, Relationships, Starting State, Current State, Conditions, History Reference, dan Metadata sesuai Character Data Model.

## 6. Status Lifecycle

Lifecycle konseptual karakter:

```text
DRAFT
  ↓
PENDING VALIDATION
  ↓
APPROVED
  ↓
READY
  ↓
ACTIVE
  ↓
INACTIVE / RETIRED
```

Status final untuk kasus khusus dapat ditetapkan Admin jika diperlukan oleh sistem.

## 7. Empty Registry

Belum ada Player/Character yang terdaftar pada Repository ini.

| Player ID | Character ID | Character Name | Status | Character File |
|---|---|---|---|---|
| — | — | — | — | — |

## 8. Integrity

Entry registry harus menunjuk ke Character File yang benar dan tidak boleh menjadi sumber Current State gameplay.

Jika registry dan Character File tidak konsisten, kondisi tersebut harus dianggap sebagai masalah integritas data dan divalidasi sebelum gameplay dilanjutkan.
