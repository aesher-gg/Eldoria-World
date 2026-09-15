# ELDORIA WORLD — CANON NPC REGISTRY

> **Authority:** Admin
> **Status:** Admin Canon v1.0
> **Purpose:** Registry dan index NPC penting yang ditetapkan sebagai Canon resmi Eldoria.

## 1. Scope

Registry ini hanya mencatat **NPC Canon penting**, bukan seluruh populasi dunia.

Populasi biasa tetap ditangani oleh Population Model + Dynamic NPC Generation.

## 2. Minimum Canon NPC Coverage

```text
DESA       → ≥ 3 Canon NPC
KOTA       → ≥ 5 Canon NPC
KERAJAAN   → ≥ 10 Canon NPC
KEKAISARAN → ≥ 25 Canon NPC
```

Angka tersebut adalah minimum. Wilayah dapat memiliki lebih banyak NPC Canon sesuai kepentingan dunia.

## 3. Canon NPC Authority

Setiap Canon NPC wajib memiliki stable `NPC_ID` dan record resmi.

Minimal record:

```text
NPC_ID
NPC_CLASS: CANON
NAME
ROLE
SETTLEMENT / REGION
FACTION
BACKGROUND
GOALS
CORE_RELATIONSHIPS
CAPABILITIES
KNOWLEDGE_BOUNDARY
CANON_ORIGIN
```

Current condition/state berada pada NPC State layer yang relevan.

## 4. Runtime Rule

Jika Player berinteraksi dengan tokoh Canon, AI GM wajib mencari dan menggunakan record Canon yang sesuai sebelum melakukan generation.

Canon NPC tidak boleh digantikan Dynamic NPC dengan identity berbeda hanya karena record Canon belum dimuat.

## 5. Registered Canon NPC

Belum ada Canon NPC individual yang didaftarkan.

```text
REGISTRY_STATUS: READY
```

## 6. Registration Template

```text
NPC_ID: NPC-CANON-???
NPC_CLASS: CANON
NAME: ???
ROLE: ???
SETTLEMENT / REGION: ???
FACTION: ???
BACKGROUND: ???
GOALS: ???
CORE_RELATIONSHIPS: ???
CAPABILITIES: ???
KNOWLEDGE_BOUNDARY: ???
CANON_ORIGIN: Admin Canon
```

`???` berarti belum ditentukan.
