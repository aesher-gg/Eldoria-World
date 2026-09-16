# Eldoria World — History Directory

> **Purpose:** Persistent event and history records for Eldoria.

Directory ini disediakan untuk menyimpan **History Record** yang menjadi bagian dari persistent world ketika data gameplay mulai dibuat.

## Authority

History mengikuti:

- `core/CORE_RULES.md`
- `core/RUNTIME_TURN_MODEL.md`
- `state/STATE_AND_HISTORY_MODEL.md`
- sistem Canon yang relevan

History adalah rekam kejadian, perubahan, provenance, dan audit. History bukan pengganti Canon dan bukan pengganti Current State.

## Integrity

- Record historis tidak boleh dihapus atau ditimpa secara diam-diam untuk menghilangkan kejadian.
- Koreksi menggunakan Correction Record yang tetap merujuk pada record asli.
- Perubahan penting harus dapat ditelusuri melalui Origin / Source.
- Narrative response bukan bukti persistence.
- Record yang belum tersedia tidak boleh dianggap ada.

## Status

Directory ini adalah **struktur persistence**, bukan kumpulan History Record gameplay yang sudah terisi.

History Record aktual hanya dibuat ketika terdapat event atau perubahan persisten yang sah dan telah melalui validation serta persistence process yang relevan.
