# ELDORIA WORLD — PLAYER REGISTRY

> **Authority:** Admin
> **Status:** Admin Registry v1.0
> **Purpose:** Registry resmi Player dan Player Character Eldoria.

## 1. Authority

Player Character (PC) tidak dibuat atau ditentukan oleh AI GM.

Player memberikan nama, latar belakang, dan detail karakter yang diinginkan. Admin memvalidasi dan memasukkan karakter ke repository sesuai template/schema Eldoria.

Setelah terdaftar, Character Record dan Current Character State menjadi sumber resmi bagi AI GM sesuai authority hierarchy.

## 2. Registry Schema

Setiap entry minimal memiliki:

```text
PLAYER_ID
CHARACTER_ID
CHARACTER_NAME
STATUS
CHARACTER_RECORD
REGISTRATION_ORIGIN
```

Detail gameplay terkini disimpan pada Current Character State yang dirujuk oleh `CHARACTER_ID`.

## 3. Rules

- `PLAYER_ID` unik untuk Player.
- `CHARACTER_ID` unik untuk setiap karakter.
- AI GM tidak boleh membuat duplicate Player Character.
- AI GM tidak boleh mengganti identity/background dasar karakter resmi secara diam-diam.
- Character baru harus melalui Admin Registration.
- State gameplay dapat berubah melalui Action Resolver + State Validator + Save Pipeline.
- Perubahan Canon/identity dasar memerlukan kewenangan Admin.

## 4. Registered Players

Belum ada Player Character yang didaftarkan.

```text
REGISTRY_STATUS: READY
```

## 5. Registration Template

Gunakan format konseptual berikut ketika Admin mendaftarkan karakter:

```text
PLAYER_ID: PLAYER-???
CHARACTER_ID: CHAR-???
CHARACTER_NAME: ???
STATUS: CREATED
CHARACTER_RECORD: characters/<character-record>.md
REGISTRATION_ORIGIN: Admin Registration from Player submission
```

`???` berarti data belum ditentukan; bukan nilai default.
