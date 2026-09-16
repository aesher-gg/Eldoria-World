# ELDORIA WORLD — NPC COVERAGE GAP MATRIX

> **Authority:** Admin
> **Status:** Deprecated Alias
> **Canonical Source:** `npcs/COVERAGE_GAP_MATRIX_v1_1.md`
> **Reason:** Coverage model was corrected from hierarchical assignment counting to `PRIMARY_SCOPE` counting.

## Canonical Rule

Setiap Canon NPC memiliki tepat satu `PRIMARY_SCOPE`:

```text
EMPIRE | KINGDOM | CITY | SETTLEMENT
```

`EMPIRE_ID`, `KINGDOM_ID`, `CITY_ID`, dan `SETTLEMENT_ID` hanya merupakan **hierarchical context** dan tidak otomatis menjadi coverage Primary Base.

## Current Canon Audit

Gunakan `npcs/COVERAGE_GAP_MATRIX_v1_1.md` sebagai sumber angka coverage resmi.

Current Primary Base Coverage:

```text
Empire     6 / 25   → gap 19
Kingdom   15 / 50   → gap 35
City       0 / 100  → gap 100
Settlement 5 / 120  → gap 115
TOTAL     26 / 295  → gap 269
```

Hierarchical context aktual:

```text
EMPIRE_ID     = 26
KINGDOM_ID    = 20
CITY_ID       = 15
SETTLEMENT_ID = 5
```

Dokumen ini dipertahankan sebagai alias kompatibilitas agar referensi lama tidak menunjuk pada angka coverage yang sudah tidak berlaku. Dokumen ini tidak boleh digunakan sebagai sumber angka coverage baru.
