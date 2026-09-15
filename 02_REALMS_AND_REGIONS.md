# ELDORIA WORLD — REALMS & REGIONS

> **Module:** 02 — Realms and Regions
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.1

## 1. Purpose

Mendefinisikan struktur geografis dan administratif Eldoria serta hubungan hierarchy yang dipakai oleh settlement, faction, NPC, monster ecology, travel, dan world state.

Module ini menetapkan **struktur**, bukan mengarang nama atau jumlah wilayah yang belum ditetapkan.

## 2. Canon Administrative-Geographic Hierarchy

Struktur makro Eldoria adalah:

```text
WORLD
└── 1 KEKAISARAN
    └── BEBERAPA KERAJAAN
        └── BEBERAPA KOTA
            └── BEBERAPA DESA / SETTLEMENT TERKAIT
```

Aturan struktural:

- Eldoria memiliki tepat satu Kekaisaran utama.
- Kekaisaran terdiri dari beberapa Kerajaan.
- Setiap Kerajaan dapat memiliki beberapa Kota.
- Setiap Kota dapat memiliki beberapa Desa besar/kecil atau settlement terkait.
- Jumlah aktual dan nama setiap entitas belum ditentukan = `???`.
- Tidak boleh membuat nama/angka geografis sebagai Canon hanya untuk memenuhi struktur.

## 3. Administrative Levels

### 3.1 Kekaisaran

Unit politik tertinggi dalam struktur makro Eldoria.

Minimum identity:

```text
EMPIRE_ID
NAME
TYPE
BOUNDARY
CAPITAL
CURRENT_STATE
ORIGIN
HISTORY
```

### 3.2 Kerajaan

Unit politik yang berada di bawah Kekaisaran.

Minimum identity:

```text
KINGDOM_ID
EMPIRE_ID
NAME
TYPE
BOUNDARY
CAPITAL
CURRENT_STATE
ORIGIN
HISTORY
```

### 3.3 Kota

Settlement utama yang berada dalam wilayah administratif Kerajaan.

Minimum identity:

```text
CITY_ID
KINGDOM_ID
REGION_ID
NAME
TYPE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

### 3.4 Desa / Settlement

Settlement yang berada dalam wilayah sebuah Kota atau struktur administratif lokal yang sah.

Minimum identity:

```text
SETTLEMENT_ID
CITY_ID
REGION_ID
NAME
TYPE
CURRENT_STATE
ORIGIN
HISTORY
```

Jika sebuah settlement secara Canon berada di luar struktur Kota, hubungan administratifnya harus ditentukan secara eksplisit dan tidak boleh ditebak.

## 4. Realm & Region

`REALM` adalah wilayah geografis/politis skala besar. Dalam Eldoria, istilah Realm tidak boleh menggantikan hierarchy Kekaisaran → Kerajaan tanpa definisi Canon yang eksplisit.

`REGION` adalah bagian geografis/ekologis/administratif yang membantu menjelaskan terrain, climate, ecology, travel, resources, dan pengaruh faction.

Field minimum Region:

```text
REGION_ID
PARENT_ID
NAME
TYPE
TERRAIN
CLIMATE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

`PARENT_ID` harus menunjuk pada entitas geografis/administratif yang benar-benar ada di Canon atau State.

## 5. Geography

Geographic features dapat meliputi:

- pegunungan,
- hutan,
- sungai,
- danau,
- dataran,
- rawa,
- gurun,
- pesisir,
- lembah,
- jalan,
- dan landmark.

Feature tidak otomatis memiliki nama, ukuran, atau posisi sebelum ditentukan oleh sumber yang sah.

## 6. Boundaries

Batas wilayah dapat berupa:

- geografis,
- administratif,
- politik,
- budaya,
- militer,
- atau batas lain yang ditetapkan module/faction.

Batas yang tidak diketahui = `???`.

## 7. Population Structure

Struktur geografis tidak berarti semua penduduk harus memiliki record individual.

Setiap level dapat memiliki Population Model agregat yang mencakup karakteristik umum seperti populasi, kepadatan, pekerjaan, demografi, keamanan, dan distribusi settlement bila data tersebut diperlukan dan tersedia.

Angka aktual yang belum ditentukan tetap `???`.

Population Model adalah dasar untuk Dynamic NPC Generation dan tidak menggantikan Canon NPC Registry.

## 8. Canon NPC Coverage Dependency

Struktur wilayah menjadi dasar pembuatan Canon NPC sistematis:

```text
KEKAISARAN → minimal 25 Canon NPC
KERAJAAN   → minimal 10 Canon NPC per kerajaan
KOTA       → minimal 5 Canon NPC per kota
DESA       → minimal 3 Canon NPC per desa
```

Minimum tersebut berarti **tokoh Canon penting**, bukan jumlah seluruh penduduk.

Canon NPC harus dibuat setelah parent geography/settlement memiliki identity yang jelas. Jangan membuat Canon NPC yang menunjuk pada wilayah `???` seolah-olah wilayah tersebut sudah Canon.

## 9. Environment

Region menyediakan konteks untuk Local Environment. Kondisi aktual seperti cuaca, visibilitas, medan, dan kondisi jalan harus berasal dari state/resolution yang relevan, bukan dianggap tetap dari deskripsi region.

## 10. Travel Relation

Jarak dan waktu perjalanan tidak boleh ditebak ketika data authoritative tersedia.

Travel resolution menggunakan lokasi, rute, jarak, mode perjalanan, kondisi karakter, dan lingkungan sesuai `00_CORE_RULES.md` serta module action yang relevan.

## 11. Dynamic Discovery

Region, sub-region, atau settlement dapat ditemukan/dihasilkan secara dinamis jika sistem mengizinkannya.

Jika menjadi material bagi gameplay, hasil tersebut memperoleh identity persisten, Origin, generation data, state, dan history sesuai rules.

Dynamic discovery tidak otomatis mengubah hasil menjadi World Canon.

## 12. Location Identity

Setiap location persisten yang dirujuk lintas turn harus memiliki stable ID atau identifier ekuivalen.

Perpindahan entity tidak mengubah identity location.

## 13. Regional Context

Region dapat memengaruhi:

- encounter pool,
- monster ecosystem,
- resources,
- economy,
- faction influence,
- travel difficulty,
- climate/environment,
- quest/event availability.

Pengaruh tersebut hanya sah jika didefinisikan module terkait atau berasal dari state.

## 14. State Boundary

Module ini mendefinisikan struktur wilayah dan hubungan parent-child, bukan current political control, population aktual, economy, monster population, atau event aktif kecuali data tersebut memang tersimpan di state yang relevan.

## 15. Dependencies

`01_WORLD_OVERVIEW` → module ini.

Module yang bergantung padanya antara lain `03_CITIES_AND_SETTLEMENTS`, `04_FACTIONS`, `14_MONSTER_ECOSYSTEM`, `16_NPC_SYSTEM`, `18_WORLD_EVENTS`, `25_WORLD_STATE`, dan `35_SAVE_PIPELINE`.

## 16. Canon Safety

Module ini tidak boleh menciptakan kerajaan, region, kota, desa, batas, atau landmark spesifik sebagai fakta Canon hanya karena runtime membutuhkan jawaban. Jika belum tersedia, gunakan `???` atau jalankan generation yang sah.

## 17. Final Principle

> **Struktur geografis menentukan hubungan wilayah; Population Model menentukan skala; Canon Registry menentukan tokoh resmi; State menentukan kondisi saat ini; Resolution menentukan perubahan.**
