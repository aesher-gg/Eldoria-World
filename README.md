# Eldoria World

> **A Living Medieval Fantasy World**

**Eldoria World** adalah World Bible dan persistent-world framework untuk roleplay **Medieval Fantasy berbasis AI Game Master**.

Eldoria dirancang sebagai dunia terbuka yang hidup, konsisten, dinamis, dan memiliki konsekuensi nyata. Repository ini adalah **official canon/source of truth** untuk aturan, struktur dunia, serta data persisten yang telah disimpan.

## Identitas

- **World:** Eldoria
- **Genre:** Medieval Fantasy · Dark Fantasy · High Fantasy
- **Mode:** Hardcore Roleplay · Open World · Living World
- **Arsitektur:** Modular · Persistent · Dynamic · State-Driven
- **Canon:** ELDORIA CANON v1.0 — LOCKED
- **AI GM:** menjalankan simulasi berdasarkan Canon dan state yang tersedia, bukan menulis cerita sesuka hati.

## Prinsip Utama

Eldoria bukan cerita yang sudah ditentukan. Eldoria adalah dunia yang **disimulasikan**.

- Player mengendalikan tindakan, bukan hasil.
- NPC, monster, faksi, dan dunia memiliki agency sendiri.
- Tidak ada plot armor, free progression, free item, free heal, teleport, atau time skip tanpa dasar sistem.
- Setiap perubahan material harus memiliki **Cause + Origin + State Change + History**.
- State adalah sumber kebenaran untuk kondisi saat ini; History menyimpan kejadian masa lalu.
- Data yang belum diketahui atau belum dapat diselesaikan ditandai `???` dan tidak boleh ditebak sebagai fakta.
- Dynamic generation harus dapat dipertahankan secara persisten ketika entitas hasil generasi sudah material bagi gameplay.
- Narasi hanya boleh menggambarkan hasil simulasi yang telah divalidasi dan berhasil dipersistenkan.

## Arsitektur Runtime

```text
PLAYER MESSAGE
↓
CREATE TURN_ID
↓
FETCH / VERIFY INDEX
↓
LOAD CURRENT STATE
↓
CHECK STATE_VERSION
↓
IDENTIFY INTENT
↓
MODULE ROUTER
↓
ACTION RESOLVER
↓
PROPOSE STATE DELTA
↓
STATE VALIDATOR
↓
GENERATE HISTORY / ORIGIN
↓
ATOMIC COMMIT + PERSISTENCE
↓
NARRATIVE OUTPUT
```

Setiap Player Message diperlakukan sebagai **satu Turn Transaction**. Transaction memiliki `TURN_ID`, bekerja terhadap `STATE_VERSION` yang dimuat, dan tidak boleh di-commit dua kali.

## Lapisan Kebenaran

### Rule Authority

```text
ELDORIA CANON
→ CORE RULES
→ SYSTEM MODULES
```

### Data Authority

```text
WORLD_STATE / CHARACTER_STATE / NPC_STATE / MONSTER_STATE
/ QUEST_STATE / EVENT_STATE
→ HISTORY / ORIGIN
```

### Narrative

Narasi adalah lapisan presentasi. Narasi tidak memiliki kewenangan untuk mengubah Canon atau state secara sepihak.

## Persistence & Recovery

State, History, dan Origin yang menyertai satu perubahan persisten harus menjadi bagian dari **atomic persistence transaction**. Jika salah satu gagal, seluruh transaction dianggap gagal dan tidak boleh meninggalkan perubahan parsial atau History palsu.

State conflict menggunakan optimistic concurrency melalui `STATE_VERSION`. Transaction terhadap versi lama harus ditolak dan state terbaru dimuat sebelum resolution ulang.

`TURN_ID` menyediakan idempotency sehingga crash/retry tidak menyebabkan satu turn diproses dua kali.

## Struktur Sistem

Fondasi utama Eldoria mencakup:

- World & Regions
- Cities & Settlements
- Factions
- Characters
- Attributes & Classes
- Skills & Magic
- Equipment
- Economy
- Vitality & Survival
- Combat
- Monster Ecosystem
- Dynamic Loot Generation
- NPC System
- Quest System
- World Events
- Reputation
- Crafting & Alchemy
- Parties, Pets & Companions
- World / Character / NPC / Monster / Event State
- History & Origin Log
- Module Router
- Action Resolver
- State Validator
- Save Pipeline

## Canon Authority

**ELDORIA CANON v1.0 — LOCKED** adalah fondasi normatif repository ini. README, INDEX, Core Rules, dan module lain harus merupakan turunan yang konsisten dari Canon tersebut.

Perubahan terhadap prinsip Canon harus diperlakukan sebagai perubahan versi Canon, bukan perubahan diam-diam pada module.

---

**Eldoria World — Persistent Medieval Fantasy for AI-Driven Roleplay.**