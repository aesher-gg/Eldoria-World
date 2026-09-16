# Eldoria World — Character Data Model v0.1

> **Module:** Character Data Model  
> **Version:** v0.1  
> **Authority:** Official Canon

## 1. Purpose

Character Data Model mendefinisikan struktur data minimum dan konseptual yang harus tersedia untuk karakter Eldoria.

Modul ini mendefinisikan **struktur data**, bukan daftar race, atribut numerik, skill, class, magic, combat formula, atau progression system tertentu.

## 2. Character Structure

Struktur konseptual karakter:

```text
CHARACTER
│
├── Identity
├── Background
├── Origin
├── Physical Profile
├── Attributes
├── Abilities
├── Equipment
├── Possessions
├── Relationships
├── Starting State
├── Current State
├── Conditions
├── History Reference
└── Metadata
```

Field dapat berkembang ketika sistem Canon baru membutuhkan data tambahan.

## 3. Identity

Identity berisi identitas dasar karakter:

- Character ID
- Player ID
- Name
- Gender
- Age
- Status

`Character ID` harus unik. `Player ID` mengidentifikasi Player dan berbeda dari Character ID.

## 4. Background

Background menjelaskan informasi yang diberikan dan disetujui sebagai latar karakter.

Dapat mencakup:

- Player Concept
- Character Background
- Known History

Background tidak boleh digunakan untuk menyelundupkan kemampuan, aset, hubungan, atau fakta besar yang belum divalidasi.

## 5. Origin

Origin menjelaskan asal-usul karakter yang relevan terhadap Canon dan gameplay.

Origin dapat mencakup lokasi asal, latar sosial, budaya, keluarga, atau sumber lain yang memang telah ditetapkan untuk karakter.

Detail spesifik hanya menjadi Canon setelah divalidasi Admin.

## 6. Physical Profile

Physical Profile menyimpan karakteristik fisik yang relevan terhadap simulasi.

Contoh kategori konseptual:

- tubuh/fisik;
- penampilan;
- ciri khas;
- keterbatasan fisik;
- karakteristik lain yang relevan.

Tidak ada nilai numerik universal yang ditetapkan dalam modul ini.

## 7. Attributes

Attributes adalah data kemampuan atau karakteristik yang dapat digunakan sistem untuk resolusi action.

Core Rules v0.1 sengaja tidak menetapkan daftar atribut maupun formula nilainya.

Setiap atribut yang nantinya dibuat harus memiliki definisi, rentang/format, sumber, dan aturan penggunaannya dalam sistem yang relevan.

## 8. Abilities

Abilities berisi kemampuan yang dimiliki karakter.

Kemampuan dapat berasal dari pengalaman, pelatihan, bakat, pengetahuan, kondisi, atau sistem lain yang sah.

Kemampuan harus memiliki dasar yang dapat ditelusuri bila diperoleh atau berubah melalui gameplay.

Tidak ada class atau skill tree global yang diwajibkan oleh Character Data Model.

## 9. Equipment

Equipment berisi perlengkapan yang sedang dikenakan atau digunakan karakter.

Equipment berbeda dari seluruh Possessions.

Contoh kategori konseptual:

- pakaian;
- armor;
- senjata;
- alat;
- perlengkapan khusus.

Detail item ditentukan oleh sistem equipment/item yang akan dibuat kemudian.

## 10. Possessions

Possessions berisi kepemilikan karakter yang tidak sedang direpresentasikan sebagai Equipment aktif.

Dapat mencakup barang, uang, dokumen, bahan, properti, atau kepemilikan lain sesuai sistem yang relevan.

Kepemilikan yang berubah selama gameplay harus mengikuti State dan History.

## 11. Relationships

Relationships berisi hubungan karakter dengan NPC, kelompok, organisasi, masyarakat, atau entitas lain yang relevan.

Hubungan bukan sekadar label naratif. Jika suatu hubungan memengaruhi gameplay, kondisinya harus dapat direpresentasikan sebagai State dan memiliki dasar History bila diperlukan.

Detail relationship state, lifecycle, formation, change, dan consequence mengikuti canonical `systems/RELATIONSHIPS.md`.

## 12. Starting State

Starting State adalah snapshot resmi kondisi karakter ketika karakter memasuki gameplay.

Starting State menjadi baseline dan tidak boleh ditimpa oleh perubahan gameplay.

Starting State harus dapat dibedakan dari Current State.

## 13. Current State

Current State adalah snapshot kondisi karakter yang berlaku saat ini.

Current State menjadi sumber utama untuk Turn berikutnya setelah divalidasi.

Contoh kategori:

- lokasi;
- kondisi fisik;
- resources;
- equipment aktif;
- possessions;
- relationships aktif;
- effects/conditions;
- status gameplay.

Daftar field final akan mengikuti sistem State yang didefinisikan kemudian.

## 14. Conditions

Conditions mencatat kondisi sementara atau berkelanjutan yang relevan terhadap karakter.

Sebuah condition yang memengaruhi resolusi action harus memiliki definisi dan sumber yang dapat ditelusuri.

Condition tidak boleh diperlakukan sebagai fakta permanen hanya karena pernah muncul dalam narasi.

## 15. History Reference

Character File menyimpan referensi terhadap History yang relevan, bukan harus menyalin seluruh History karakter.

History tetap menjadi sumber kronologis untuk kejadian dan perubahan penting.

## 16. Metadata

Metadata dapat menyimpan informasi administratif seperti:

- versi data;
- waktu pembuatan;
- waktu perubahan;
- status validasi;
- referensi sumber.

Metadata tidak menggantikan State atau History.

## 17. Required Before Gameplay

Secara konseptual, sebelum karakter dapat menjadi `READY`, minimal tersedia:

- Player ID;
- Character ID;
- Character Name;
- Status;
- Character Background;
- Character File;
- validasi Admin.

Field lain dapat bersifat conditional sesuai konsep karakter dan sistem dunia.

## 18. Conditional Data

Tidak semua karakter harus memiliki semua jenis data pada awal permainan.

Contoh data conditional:

- Origin detail;
- Equipment tertentu;
- Abilities tertentu;
- Relationships;
- Property;
- kondisi khusus.

Ketiadaan data tidak boleh otomatis diisi dengan asumsi Canon.

## 19. Data Authority

```text
PLAYER
└── Character decisions / intent

ADMIN
└── Character registration / Canon validation

AI GM
└── Simulation / validated runtime changes

CHARACTER FILE
└── Official character data

STATE
└── Current condition

HISTORY
└── Provenance of significant changes
```

## 20. Integrity Rules

- Character ID harus unik.
- Player ID dan Character ID tidak boleh dipertukarkan.
- Starting State tidak boleh ditimpa oleh Current State.
- Current State harus konsisten dengan perubahan yang telah tervalidasi.
- Perubahan penting harus memiliki Origin/Source yang dapat ditelusuri.
- Character File tidak boleh bertentangan dengan registry.
- Data yang belum didefinisikan tetap Unknown/Undefined.
- Narasi tidak menjadi sumber data karakter hanya karena disebutkan dalam response.

## 21. Future Extensions

Modul ini dapat diperluas ketika sistem berikut dibuat, tanpa memasukkan mekanik tersebut sekarang:

```text
Attributes
Abilities / Skills
Items / Equipment
Economy / Currency
Health / Conditions
Supernatural / Magic
Progression
Organizations / Property
Other Character Systems
```

Relationships sudah menjadi canonical system #06 dan bukan lagi future extension dari Character Data Model.

Setiap ekstensi harus memiliki aturan Canon sendiri dan tetap kompatibel dengan Core Rules, State, History, dan Runtime.
