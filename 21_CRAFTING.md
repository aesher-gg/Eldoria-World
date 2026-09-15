# ELDORIA WORLD — CRAFTING

> **Module:** 21 — Crafting
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan crafting sebagai proses mengubah material, recipe/knowledge, tools, skill, waktu, dan kondisi menjadi item atau hasil lain melalui resolution.

Module ini menetapkan framework, bukan daftar recipe, stat, durasi, atau hasil universal.

## 2. Crafting Identity

Crafting operation yang material bagi gameplay dapat memiliki:

```text
CRAFT_ID
ACTOR_ID
RECIPE_ID / METHOD_ID
INPUTS
TOOLS
LOCATION
REQUIREMENTS
OUTPUTS
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Valid Inputs

Input dapat berupa material, component, item, resource, knowledge, tool, workstation, atau input lain yang diizinkan oleh method.

Input harus benar-benar tersedia dan tidak boleh digunakan dua kali melalui duplicate resolution.

## 4. Recipe & Method

Recipe/method dapat berasal dari:

- learned knowledge,
- training,
- discovery,
- blueprint,
- faction/guild teaching,
- experimentation,
- existing item analysis,
- atau generation yang sah.

Tidak ada recipe universal yang dianggap diketahui tanpa source.

## 5. Requirements

Crafting dapat memerlukan:

- skill/proficiency,
- tools,
- workstation,
- materials,
- magic,
- time,
- location,
- knowledge,
- class/faction access,
- atau condition lain yang relevan.

Requirement aktual mengikuti source dan state.

## 6. Resolution

```text
CRAFT INTENT
↓
LOAD RECIPE / METHOD
↓
CHECK INPUTS + REQUIREMENTS
↓
CHECK TOOLS + CONDITIONS
↓
RESOLVE QUALITY / SUCCESS / FAILURE
↓
GENERATE STATE DELTA
↓
VALIDATE
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

Player memilih tindakan crafting, bukan menjamin kualitas atau keberhasilan.

## 7. Inputs & Outputs

Crafting dapat mengonsumsi, mengubah, mempertahankan, merusak, atau menghasilkan input/output sesuai resolution.

Output material harus mengikuti `10_EQUIPMENT_SYSTEM` atau module domain lain yang relevan.

## 8. Quality & Failure

Quality, efficiency, defects, waste, partial success, atau failure hanya berlaku jika method/system menyediakan mekanismenya.

Tidak ada automatic perfect craft.

## 9. Time & Environment

Crafting yang membutuhkan waktu harus menghasilkan time delta.

Environment, workstation, safety, temperature, tools, dan location dapat memengaruhi resolution bila relevan.

## 10. Ownership & Economy

Crafting dapat mengubah ownership, inventory, currency, contracts, market supply, atau faction resources.

Konsekuensi ekonomi mengikuti `11_ECONOMY.md`.

## 11. Dynamic Generation

Recipe, method, material, atau output dapat digenerate secara dinamis jika mekanisme mengizinkan.

Generated material yang menjadi persistent wajib memiliki stable identity, origin, generation data, current state, dan history.

## 12. Information Boundary

Character hanya dapat menggunakan recipe/knowledge yang benar-benar diketahui atau dapat diaksesnya.

Player knowledge tidak otomatis menjadi crafting knowledge Character.

## 13. Anti-Duplicate & Idempotency

Crafting transaction dengan `TURN_ID` yang telah committed tidak boleh dijalankan ulang.

Generated output yang telah persisted tidak boleh dibuat sebagai replacement hanya karena runtime mengulang generation.

## 14. Cross-System Integration

Crafting dapat berinteraksi dengan:

- equipment,
- economy,
- skills,
- magic,
- alchemy,
- quests,
- factions,
- world state,
- dan character state.

Module terkait wajib dimuat jika konsekuensi menyentuh domain tersebut.

## 15. Canon Safety

Module ini tidak menetapkan fixed recipe catalog, material table, success rate, quality scale, universal crafting time, atau item stats.

## 16. Dependencies

`06_ATTRIBUTES` + `08_SKILLS` + `10_EQUIPMENT_SYSTEM` + `11_ECONOMY`.

Integrasi: `09_MAGIC_SYSTEM`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `22_ALCHEMY`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 17. Final Principle

> **Crafting adalah proses resource-to-result yang di-resolve berdasarkan knowledge, capability, inputs, tools, dan kondisi nyata; hasil tidak dijamin hanya karena Player menginginkannya.**
