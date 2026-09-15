# ELDORIA WORLD — REALMS & REGIONS

> **Module:** 02 — Realms and Regions
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan struktur geografis dan administratif Eldoria dari tingkat Realm hingga Region tanpa mengarang data lokasi yang belum ditetapkan.

## 2. Hierarchy

```text
WORLD
└── REALM
    └── REGION
        └── SUB-REGION / TERRITORY
            └── LOCATION
```

Tidak semua dunia harus menggunakan seluruh tingkat. Struktur aktual mengikuti data yang tersedia.

## 3. Realm

`REALM` adalah wilayah geografis/politis skala besar yang memiliki batas atau identitas yang bermakna bagi sistem.

Field minimum:

```text
REALM_ID
NAME
TYPE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

Jika field belum diketahui: `???`.

## 4. Region

`REGION` adalah bagian dari Realm yang memiliki karakter geografis, ekologis, administratif, atau sosial yang relevan.

Field minimum:

```text
REGION_ID
REALM_ID
NAME
TYPE
TERRAIN
CLIMATE
BOUNDARY
CURRENT_STATE
ORIGIN
HISTORY
```

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

Feature tidak otomatis memiliki nama atau ukuran sebelum ditentukan oleh sumber yang sah.

## 6. Boundaries

Batas wilayah dapat berupa:

- batas geografis,
- administratif,
- politik,
- budaya,
- militer,
- atau batas lain yang ditetapkan module/faction.

Batas yang tidak diketahui = `???`.

## 7. Environment

Region menyediakan konteks untuk Local Environment. Kondisi aktual seperti cuaca, visibilitas, medan, dan kondisi jalan harus berasal dari state/resolution yang relevan, bukan dianggap tetap dari deskripsi region.

## 8. Travel Relation

Jarak dan waktu perjalanan tidak boleh ditebak ketika data authoritative tersedia.

Travel resolution menggunakan lokasi, rute, jarak, mode perjalanan, kondisi karakter, dan lingkungan sesuai `00_CORE_RULES.md` serta module travel/action yang relevan.

## 9. Dynamic Discovery

Region atau sub-region dapat ditemukan/dihasilkan secara dinamis jika sistem mengizinkannya.

Jika menjadi material bagi gameplay, hasil tersebut memperoleh identity persisten dan Origin serta mengikuti aturan generation determinism.

## 10. Location Identity

Setiap location persisten yang dirujuk lintas turn harus memiliki stable ID atau identifier ekuivalen.

Perpindahan entity tidak mengubah identity location.

## 11. Regional Context

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

## 12. State Boundary

Module ini mendefinisikan struktur wilayah, bukan current political control, population, economy, monster population, atau event aktif kecuali data tersebut memang tersimpan di state yang relevan.

## 13. Dependencies

`01_WORLD_OVERVIEW` → module ini.

Module yang bergantung padanya antara lain `03_CITIES_AND_SETTLEMENTS`, `04_FACTIONS`, `14_MONSTER_ECOSYSTEM`, `18_WORLD_EVENTS`, `25_WORLD_STATE`, dan `35_SAVE_PIPELINE`.

## 14. Canon Safety

Module ini tidak boleh menciptakan kerajaan, region, kota, batas, atau landmark spesifik sebagai fakta Canon hanya karena runtime membutuhkan jawaban. Jika belum tersedia, gunakan `???` atau jalankan generation yang sah.

## 15. Final Principle

> **Geografi menyediakan konteks; State menentukan kondisi saat ini; Resolution menentukan perubahan.**
