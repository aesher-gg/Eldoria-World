# ELDORIA WORLD — MAGIC SYSTEM

> **Module:** 09 — Magic System
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan framework magic Eldoria sebagai sistem capability dan resolution tanpa menetapkan satu daftar spell, resource, atau power scale universal yang belum dikunci Canon.

## 2. Magic Model

Magic dapat menggunakan satu atau lebih model yang sah, seperti:

- spell,
- ritual,
- innate ability,
- enchantment,
- magical item,
- pact,
- divine/supernatural power,
- atau model lain yang ditetapkan dunia.

Model aktual harus berasal dari source yang sah.

## 3. Magic Identity

Magic capability persisten dapat memiliki:

```text
MAGIC_ID
NAME
TYPE
DOMAIN
PREREQUISITES
RESOURCE_REQUIREMENTS
EFFECT
LIMITATIONS
ORIGIN
HISTORY
```

Field yang belum diketahui = `???`.

## 4. Access

Akses terhadap magic harus memiliki dasar yang sah, misalnya:

- innate trait,
- learning,
- teacher,
- discovery,
- pact,
- faction,
- artifact,
- ritual,
- atau system generation.

Player tidak dapat menyatakan magic telah dikuasai tanpa resolution.

## 5. Resources & Costs

Magic dapat menggunakan resource seperti mana, stamina, material, focus, cooldown, health, time, risk, atau resource lain bila didefinisikan system.

Tidak ada resource cost universal yang boleh ditebak jika belum ditetapkan.

## 6. Resolution

Magic action harus melalui:

```text
INTENT
↓
CHECK ACCESS / PREREQUISITE
↓
CHECK RESOURCE / CONDITION
↓
RESOLVE EFFECT
↓
STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
```

Effect tidak boleh otomatis berhasil hanya karena spell/capability tersedia.

## 7. Failure & Risk

Magic dapat gagal, memiliki biaya, menghasilkan side effect, atau menimbulkan konsekuensi jika rules terkait mengizinkannya.

Outcome ditentukan resolution, bukan kebutuhan narasi.

## 8. Environment Interaction

Magic dapat berinteraksi dengan:

- terrain,
- weather,
- objects,
- creatures,
- barriers,
- other magic,
- time,
- atau world state.

Interaksi spesifik harus memiliki rule atau resolution basis.

## 9. Magic Items

Magical equipment mengikuti `10_EQUIPMENT_SYSTEM.md` dan tetap tunduk pada identity, state, origin, dan history.

## 10. Progression

Penguasaan magic dapat berkembang melalui training, practice, discovery, teacher, progression system, atau mekanisme sah lainnya.

Tidak ada free spell, free mastery, atau free power-up.

## 11. Information Boundary

Magic yang tersembunyi, ritual, weakness, atau capability tidak otomatis diketahui Player/Character/NPC lain.

Information State berlaku.

## 12. Dynamic Magic

Magic capability baru dapat dihasilkan secara dinamis jika system mengizinkannya. Jika menjadi material, definition, identity, origin, dan state yang diperlukan harus dipersistenkan.

## 13. Validation

Validator harus memeriksa:

- magic identity,
- access,
- prerequisites,
- resources,
- target validity,
- environmental requirements,
- state version,
- Cause + Origin,
- `TURN_ID`.

## 14. Dependencies

`05_CHARACTER_SYSTEM` + `06_ATTRIBUTES` + `07_CLASSES` + `08_SKILLS` → module ini.

Integrasi utama: `10_EQUIPMENT_SYSTEM`, `12_VITALITY_SURVIVAL`, `13_COMBAT`, `14_MONSTER_ECOSYSTEM`, `21_CRAFTING`, `22_ALCHEMY`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`.

## 15. Canon Safety

Module ini tidak menetapkan spell list, magic school, mana formula, atau power tier universal sebagai fakta Canon tanpa sumber yang sah.

## 16. Final Principle

> **Magic adalah sistem capability dengan aturan, biaya, batasan, dan konsekuensi; kekuatan magic tidak menghapus prinsip resolution dan persistence.**
