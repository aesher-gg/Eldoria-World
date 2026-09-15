# ELDORIA WORLD — CANON NPC

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **NPC Class:** CANON
> **Status:** ACTIVE

## Identity

```text
NPC_ID: NPC-CANON-001
NPC_CLASS: CANON
NAME: Alaric Veyn
RACE_CANON_ID: RACE-001
ROLE / TYPE: Pejabat Administrasi Kekaisaran — Pengawas Koordinasi Antar-Kerajaan
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-001
CANON_ORIGIN: Admin Canon
CANON_STATUS: ACTIVE
```

## Background

Alaric Veyn adalah pejabat administratif Kekaisaran Valthera yang menangani koordinasi administratif lintas kerajaan dalam urusan yang berada di bawah lingkup pemerintahan kekaisaran. Perannya bersifat koordinatif dan administratif; ia tidak otomatis memiliki kewenangan atas urusan internal kerajaan yang berada di luar ruang lingkup kekaisaran yang telah ditetapkan Canon.

## Origin

Ditetapkan sebagai Canon NPC pertama pada Tahap 5 — Canon NPC Creation untuk menyediakan representasi individu pada lapisan administrasi Empire tanpa mengisi jabatan atau struktur kekaisaran yang masih berstatus `???`.

## Goals

- Menjaga kelancaran koordinasi administratif yang memang berada dalam lingkup kekaisaran.
- Mengidentifikasi ketidaksesuaian administratif yang memerlukan klarifikasi antar-otoritas.
- Menyampaikan informasi kepada pihak yang memiliki kewenangan sesuai rantai pemerintahan yang berlaku.

## Core Relationships

```text
FACTION-001 Pemerintahan Kekaisaran Valthera → anggota / pejabat terkait
KINGDOM-001..005 → hubungan administratif sesuai kewenangan; hubungan personal spesifik = ???
NPC lain → ???
```

## Capabilities

- Administrasi dan pencatatan dokumen.
- Koordinasi komunikasi antar-otoritas.
- Evaluasi administratif terhadap informasi yang tersedia baginya.
- Negosiasi prosedural dalam batas kewenangan yang sah.
- Tidak memiliki kekuasaan otomatis atas kerajaan, kota, settlement, faction, atau NPC lain hanya berdasarkan jabatan.

## Knowledge Boundary

Alaric mengetahui informasi administratif yang secara sah diterima atau diperolehnya melalui tugas dan interaksi. Ia tidak otomatis mengetahui rahasia kerajaan, informasi militer, rencana faction, kondisi settlement, atau kejadian pribadi yang belum sampai kepadanya. Informasi spesifik di luar boundary ini = `???`.

## Faction Boundary

```text
FACTION_ID: FACTION-001
FACTION_NAME: Pemerintahan Kekaisaran Valthera
MEMBERSHIP: Canon-established
RANK: ???
SPECIFIC_AUTHORITY: Terbatas pada fungsi administratif yang sah; detail jabatan/rank = ???
ACCESS: Tidak otomatis mencakup seluruh data atau sumber daya kekaisaran
```

## Canon Safety

- Nama, race, role, faction, goals, capabilities, dan origin di atas adalah Canon Admin.
- Lokasi spesifik belum ditetapkan dan tetap `???`.
- Nama Kaisar Valthera tidak disimpulkan dari NPC ini.
- NPC ini tidak menciptakan hukum, kementerian, struktur militer, atau kewenangan kekaisaran baru.
- Current State terpisah dari Canon Identity dan harus dipersistenkan melalui NPC State + History + Origin bila berubah.
