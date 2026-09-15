# ELDORIA WORLD — CANON MONSTER REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Registry resmi spesies/jenis Monster Canon Eldoria.

## 1. Canon Limit

```text
MAXIMUM CANON MONSTER TYPES / SPECIES = 150
```

Batas 150 berlaku untuk **jenis/spesies Canon**, bukan jumlah individu monster yang hidup di dunia.

## 2. Tier Structure

Monster Canon akan dibagi berdasarkan tingkat kekuatan/ancaman yang ditetapkan Admin.

```text
TINGKAT RENDAH
TINGKAT MENENGAH
TINGKAT TINGGI
TINGKAT PUNCAK
```

Distribusi jumlah tiap tingkat belum ditentukan dan tidak boleh ditebak AI GM.

## 3. Canon Monster Authority

Setiap species/type Canon wajib memiliki stable `MONSTER_CANON_ID`.

Minimal definition:

```text
MONSTER_CANON_ID
NAME
SPECIES / TYPE
CANON_TIER
DESCRIPTION
HABITAT / ECOLOGY
BASE CAPABILITY
LIFECYCLE
CANON_ORIGIN
```

Individual monster tetap menggunakan `MONSTER_ID` dan Monster State bila menjadi material/persistent.

## 4. Runtime Rule

AI GM boleh menghasilkan individu dari Monster Canon bila ecology/context mengizinkan.

AI GM juga dapat menghasilkan creature dynamic yang diizinkan oleh Canon rules, tetapi tidak boleh otomatis memasukkannya sebagai spesies Canon baru.

Menambah, menghapus, atau mengubah definisi Monster Canon membutuhkan Admin Canon update.

## 5. Registered Canon Monster Types

Belum ada species Monster Canon individual yang didaftarkan.

```text
REGISTRY_STATUS: READY
CANON_COUNT: 0 / 150
```

## 6. Registration Template

```text
MONSTER_CANON_ID: MON-CANON-???
NAME: ???
SPECIES / TYPE: ???
CANON_TIER: ???
DESCRIPTION: ???
HABITAT / ECOLOGY: ???
BASE CAPABILITY: ???
LIFECYCLE: ???
CANON_ORIGIN: Admin Canon
```

`???` berarti belum ditentukan.
