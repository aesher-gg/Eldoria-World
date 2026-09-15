# ELDORIA WORLD — CANON NOBLE HOUSES

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0
> **Phase:** WORLD DEVELOPMENT
> **Dependencies:** `37_NOBILITY_SYSTEM.md` + `world/NOBILITY_KINGDOM_VARIATIONS.md` + Governance + Faction + Geography + Magic

## 1. Purpose

File ini menetapkan Noble House yang benar-benar dibutuhkan oleh struktur dunia saat ini. House tidak dibuat untuk memenuhi quota NPC atau memperbanyak lore.

Noble House Canon dipilih karena memiliki fungsi material dalam salah satu atau lebih bidang berikut:

- royal succession / Crown legitimacy,
- territorial administration,
- strategic economy,
- military defense,
- frontier management,
- maritime or trade infrastructure,
- stewardship sumber daya,
- atau hubungan penting dengan magic.

House-specific magic, artifact, bloodline, monopoly, dan supernatural claim **tidak otomatis ada** hanya karena House tercatat di sini. Semua capability harus memiliki source dan resolution basis sesuai `09_MAGIC_SYSTEM.md`.

---

## 2. Canon Rules

```text
NOBLE_HOUSE ≠ NPC
NOBLE_HOUSE ≠ TITLE
NOBLE_HOUSE ≠ SOVEREIGNTY
NOBLE_HOUSE ≠ AUTOMATIC_MAGIC_ACCESS
NOBLE_HOUSE ≠ AUTOMATIC_MILITARY_COMMAND
```

House membership tidak otomatis memberikan title, inheritance, office, wealth, command, magic, privileged knowledge, atau reputation.

Setiap House memiliki:

```text
HOUSE_ID
NAME
KINGDOM_ID
TYPE / ROLE
PRIMARY_SCOPE
LEADERSHIP MODEL
TITLES / DOMAIN CONTEXT
GOALS
INTERESTS
ECONOMIC BASE
MILITARY FUNCTION
MAGIC RELATION
CURRENT_STATE
ORIGIN
HISTORY
```

### House Count Policy

```text
KINGDOM-001 → 2 Canon Houses
KINGDOM-002 → 2 Canon Houses
KINGDOM-003 → 2 Canon Houses
KINGDOM-004 → 2 Canon Houses
KINGDOM-005 → 2 Canon Houses
TOTAL → 10 Canon Noble Houses
```

Sepuluh House ini adalah **initial strategic Canon**, bukan batas maksimal. House tambahan hanya dibuat jika ada kebutuhan dunia yang nyata.

---

# 3. KINGDOM-001 — VALEDORN

## HOUSE-001 — HOUSE VAREN

```text
HOUSE_ID: NOBLE-HOUSE-001
NAME: House Varen
KINGDOM_ID: KINGDOM-001
TYPE: ROYAL_HOUSE
PRIMARY_SCOPE: Crown of Valedorn
LEADERSHIP_MODEL: Hereditary Royal House
CURRENT_HEAD: NPC-CANON-012 — Cedric Varen
PRIMARY_TITLE_CONTEXT: King / Queen of Valedorn
DOMAIN_CONTEXT: Royal domain and Crown administration; exact territorial holdings follow Crown law
GOALS: Menjaga legitimasi Crown, kesinambungan kerajaan, stabilitas internal, dan kewajiban terhadap Kekaisaran Valthera
INTERESTS: Pemerintahan, pangan, sungai, keamanan, suksesi, hubungan dengan noble houses
ECONOMIC_BASE: Royal revenues and lawful Crown resources
MILITARY_FUNCTION: Crown defense and coordination under Valedorn law
MAGIC_RELATION: May patronize or employ lawful magical institutions/capabilities; no automatic House-wide magical trait
CURRENT_STATE: ACTIVE
ORIGIN: Royal foundation of Valedorn
HISTORY: Current royal house of Valedorn; detailed dynastic history to be expanded only when needed by Canon
CANON_STATUS: ACTIVE
```

**Why needed:** House Varen is the minimum dynastic anchor for the existing King of Valedorn and future succession architecture.

## HOUSE-002 — HOUSE GOLDRIVER

```text
HOUSE_ID: NOBLE-HOUSE-002
NAME: House Goldriver
KINGDOM_ID: KINGDOM-001
TYPE: MAJOR_NOBLE_HOUSE
PRIMARY_SCOPE: Agrarian and riverine domains
LEADERSHIP_MODEL: Hereditary noble house
CURRENT_HEAD: Hereditary head of House Goldriver
PRIMARY_TITLE_CONTEXT: Count / Countess or higher title if separately granted by Crown
DOMAIN_CONTEXT: Productive farmland, river transport, irrigation, and associated estates where legally granted
GOALS: Maintain productive land, water infrastructure, food supply, and lawful regional influence
INTERESTS: Agriculture, mills, irrigation, river transport, markets, estate security
ECONOMIC_BASE: Agriculture, milling, river commerce, estate production
MILITARY_FUNCTION: Local levy, road/bridge security, river and estate defense when legally obligated
MAGIC_RELATION: May employ agricultural, water, or utility magic when separately acquired and validated
CURRENT_STATE: ACTIVE
ORIGIN: Established as a major agrarian-riverine noble house
HISTORY: Canon foundation; detailed lineage remains outside current minimum scope
CANON_STATUS: ACTIVE
```

**Why needed:** Provides the agrarian-riverine noble function that cannot be represented by the Crown alone.

---

# 4. KINGDOM-002 — BRANNOR

## HOUSE-003 — HOUSE BRANN

```text
HOUSE_ID: NOBLE-HOUSE-003
NAME: House Brann
KINGDOM_ID: KINGDOM-002
TYPE: ROYAL_HOUSE
PRIMARY_SCOPE: Crown of Brannor
LEADERSHIP_MODEL: Hereditary Royal House
CURRENT_HEAD: NPC-CANON-013 — Tharok Brann
PRIMARY_TITLE_CONTEXT: King / Queen of Brannor
DOMAIN_CONTEXT: Royal domain and Crown administration; exact territorial holdings follow Crown law
GOALS: Menjaga Crown, keamanan pegunungan, stabilitas kerajaan, dan hubungan dengan Kekaisaran
INTERESTS: Defense, mining policy, mountain routes, succession, resource security
ECONOMIC_BASE: Royal revenues and lawful Crown resources
MILITARY_FUNCTION: Crown defense and mountain security coordination
MAGIC_RELATION: May patronize defensive, crafting, or magical-resource institutions; no automatic magical bloodline
CURRENT_STATE: ACTIVE
ORIGIN: Royal foundation of Brannor
HISTORY: Current royal house of Brannor
CANON_STATUS: ACTIVE
```

**Why needed:** Dynastic anchor for the existing King of Brannor and succession structure.

## HOUSE-004 — HOUSE IRONVEIN

```text
HOUSE_ID: NOBLE-HOUSE-004
NAME: House Ironvein
KINGDOM_ID: KINGDOM-002
TYPE: MAJOR_NOBLE_HOUSE
PRIMARY_SCOPE: Highland mineral and fortified-route domains
LEADERSHIP_MODEL: Hereditary noble house
CURRENT_HEAD: Hereditary head of House Ironvein
PRIMARY_TITLE_CONTEXT: Count / Countess or equivalent higher noble title when lawfully granted
DOMAIN_CONTEXT: Mining districts, mountain routes, fortified holdings, or resource estates where legally granted
GOALS: Protect lawful resource operations, mountain infrastructure, and strategic routes
INTERESTS: Mining, metalworking, engineering, trade routes, fortifications
ECONOMIC_BASE: Mineral extraction, metalworking, quarrying, mountain trade
MILITARY_FUNCTION: Pass defense, convoy security, fortified holding defense when obligated
MAGIC_RELATION: May interact with magical minerals, enchanted forging, wards, or mage-artisans only where individually established
CURRENT_STATE: ACTIVE
ORIGIN: Highland resource stewardship tradition
HISTORY: Canon foundation; detailed mineral assets are not predetermined
CANON_STATUS: ACTIVE
```

**Why needed:** Represents the mineral/industrial and mountain-defense aristocracy without assuming a specific magical ore.

---

# 5. KINGDOM-003 — MARISELLE

## HOUSE-005 — HOUSE AUREON

```text
HOUSE_ID: NOBLE-HOUSE-005
NAME: House Aureon
KINGDOM_ID: KINGDOM-003
TYPE: ROYAL_HOUSE
PRIMARY_SCOPE: Crown of Mariselle
LEADERSHIP_MODEL: Hereditary Royal House
CURRENT_HEAD: NPC-CANON-014 — Celestine Aureon
PRIMARY_TITLE_CONTEXT: Queen / King of Mariselle
DOMAIN_CONTEXT: Royal domain and Crown administration; exact territorial holdings follow Crown law
GOALS: Maintain Crown legitimacy, maritime stability, trade continuity, and lawful royal succession
INTERESTS: Ports, maritime security, diplomacy, trade, shipbuilding, succession
ECONOMIC_BASE: Royal revenues and lawful Crown resources
MILITARY_FUNCTION: Crown coordination for coastal and maritime defense
MAGIC_RELATION: May patronize navigation, maritime, or other lawful magical capabilities; no automatic magical lineage
CURRENT_STATE: ACTIVE
ORIGIN: Royal foundation of Mariselle
HISTORY: Current royal house of Mariselle
CANON_STATUS: ACTIVE
```

**Why needed:** Dynastic anchor for the existing Queen of Mariselle and maritime Crown authority.

## HOUSE-006 — HOUSE TIDEWARD

```text
HOUSE_ID: NOBLE-HOUSE-006
NAME: House Tideward
KINGDOM_ID: KINGDOM-003
TYPE: MAJOR_NOBLE_HOUSE
PRIMARY_SCOPE: Maritime and coastal domains
LEADERSHIP_MODEL: Hereditary noble house
CURRENT_HEAD: Hereditary head of House Tideward
PRIMARY_TITLE_CONTEXT: Count / Countess, Marquis / Marchioness, or other lawful title depending on domain
DOMAIN_CONTEXT: Port districts, island holdings, coastal estates, or maritime approaches where legally granted
GOALS: Maintain maritime infrastructure, lawful trade, coastal security, and port continuity
INTERESTS: Shipping, fisheries, shipbuilding, ports, island routes, maritime trade
ECONOMIC_BASE: Shipping interests, fisheries, shipbuilding, lawful port-related revenue
MILITARY_FUNCTION: Coastal watch, convoy protection, island defense when legally obligated
MAGIC_RELATION: May employ enchanted vessels/equipment or navigation capabilities if separately acquired and validated
CURRENT_STATE: ACTIVE
ORIGIN: Maritime noble tradition of Mariselle
HISTORY: Canon foundation; specific fleet or magical assets are not assumed
CANON_STATUS: ACTIVE
```

**Why needed:** Provides a noble institution for maritime infrastructure and coastal defense without making every port function royal.

---

# 6. KINGDOM-004 — SYLVARAN

## HOUSE-007 — HOUSE SYLVAR

```text
HOUSE_ID: NOBLE-HOUSE-007
NAME: House Sylvar
KINGDOM_ID: KINGDOM-004
TYPE: ROYAL_HOUSE
PRIMARY_SCOPE: Crown of Sylvaran
LEADERSHIP_MODEL: Hereditary Royal House
CURRENT_HEAD: NPC-CANON-015 — Edrien Sylvar
PRIMARY_TITLE_CONTEXT: King / Queen of Sylvaran
DOMAIN_CONTEXT: Royal domain and Crown administration; exact territorial holdings follow Crown law
GOALS: Maintain Crown legitimacy, forest and river stewardship, frontier stability, and lawful succession
INTERESTS: Forestry, rivers, frontier, agriculture, security, succession
ECONOMIC_BASE: Royal revenues and lawful Crown resources
MILITARY_FUNCTION: Crown coordination for frontier and territorial defense
MAGIC_RELATION: May maintain lawful relations with magical institutions or capabilities associated with forest/river environments; no automatic magical bloodline
CURRENT_STATE: ACTIVE
ORIGIN: Royal foundation of Sylvaran
HISTORY: Current royal house of Sylvaran
CANON_STATUS: ACTIVE
```

**Why needed:** Dynastic anchor for the existing King of Sylvaran.

## HOUSE-008 — HOUSE THORNWARD

```text
HOUSE_ID: NOBLE-HOUSE-008
NAME: House Thornward
KINGDOM_ID: KINGDOM-004
TYPE: MAJOR_NOBLE_HOUSE
PRIMARY_SCOPE: Forest frontier and river-route domains
LEADERSHIP_MODEL: Hereditary noble house
CURRENT_HEAD: Hereditary head of House Thornward
PRIMARY_TITLE_CONTEXT: Marquis / Marchioness or Count / Countess depending on lawful grant
DOMAIN_CONTEXT: Frontier estates, forest routes, river crossings, or fortified holdings where legally granted
GOALS: Maintain frontier security, route continuity, and sustainable resource stewardship
INTERESTS: Forest resources, hunting regulation, river crossings, reconnaissance, frontier logistics
ECONOMIC_BASE: Forestry, controlled resource extraction, river transport, crafts
MILITARY_FUNCTION: Frontier patrol, route security, reconnaissance, settlement defense when obligated
MAGIC_RELATION: May interact with warding, enchanted flora, river magic, or magical creatures only when separately Canonized
CURRENT_STATE: ACTIVE
ORIGIN: Frontier stewardship tradition of Sylvaran
HISTORY: Canon foundation; no specific magical forest or creature bond is assumed
CANON_STATUS: ACTIVE
```

**Why needed:** Supplies a dedicated frontier/stewardship noble institution for Wildmere and related routes.

---

# 7. KINGDOM-005 — SAHRAD

## HOUSE-009 — HOUSE QASRANE

```text
HOUSE_ID: NOBLE-HOUSE-009
NAME: House Qasrane
KINGDOM_ID: KINGDOM-005
TYPE: ROYAL_HOUSE
PRIMARY_SCOPE: Crown of Sahrad
LEADERSHIP_MODEL: Hereditary Royal House
CURRENT_HEAD: Reigning Sovereign of Sahrad — office identity; individual Canon NPC to be established in the Noble NPC stage
PRIMARY_TITLE_CONTEXT: King / Queen of Sahrad
DOMAIN_CONTEXT: Royal oasis and Crown administration; exact territorial holdings follow Crown law
GOALS: Maintain Crown legitimacy, water security, caravan continuity, frontier stability, and lawful succession
INTERESTS: Oasis administration, water infrastructure, caravan routes, pastoral stability, diplomacy, succession
ECONOMIC_BASE: Royal revenues and lawful Crown resources
MILITARY_FUNCTION: Crown coordination for oasis, route, and frontier defense
MAGIC_RELATION: May patronize water, navigation, environmental, or other lawful magical capabilities; no automatic magical lineage
CURRENT_STATE: ACTIVE
ORIGIN: Royal foundation of Sahrad
HISTORY: Current royal house of Sahrad; reigning sovereign identity is intentionally a separate NPC-layer dependency
CANON_STATUS: ACTIVE
```

**Why needed:** Establishes the dynastic anchor required by Sahrad governance without prematurely creating the sovereign NPC.

## HOUSE-010 — HOUSE DUSTVEIL

```text
HOUSE_ID: NOBLE-HOUSE-010
NAME: House Dustveil
KINGDOM_ID: KINGDOM-005
TYPE: MAJOR_NOBLE_HOUSE
PRIMARY_SCOPE: Caravan and arid frontier domains
LEADERSHIP_MODEL: Hereditary noble house
CURRENT_HEAD: Hereditary head of House Dustveil
PRIMARY_TITLE_CONTEXT: Marquis / Marchioness or Count / Countess depending on lawful grant
DOMAIN_CONTEXT: Caravan corridors, route stations, water points, or frontier holdings where legally granted
GOALS: Maintain route security, water access, caravan continuity, and frontier logistics
INTERESTS: Caravan trade, water points, livestock, route services, escorts, frontier watch
ECONOMIC_BASE: Caravan services, livestock, lawful route fees, oasis-linked commerce
MILITARY_FUNCTION: Caravan escort, route patrol, water-point defense, frontier protection when obligated
MAGIC_RELATION: May employ magical navigation, water-related capabilities, or environmental tools if separately acquired and validated
CURRENT_STATE: ACTIVE
ORIGIN: Caravan-route and frontier stewardship tradition of Sahrad
HISTORY: Canon foundation; no specific magical oasis or artifact is assumed
CANON_STATUS: ACTIVE
```

**Why needed:** Represents Sahrad's caravan-route and frontier aristocracy independently from the Crown.

---

# 8. House-to-Kingdom Functional Matrix

| Kingdom | Royal House | Strategic Major House | Primary Noble Function |
|---|---|---|---|
| Valedorn | House Varen | House Goldriver | Crown + agrarian/river stewardship |
| Brannor | House Brann | House Ironvein | Crown + mineral/mountain defense |
| Mariselle | House Aureon | House Tideward | Crown + maritime infrastructure |
| Sylvaran | House Sylvar | House Thornward | Crown + forest/frontier stewardship |
| Sahrad | House Qasrane | House Dustveil | Crown + caravan/frontier stewardship |

## 9. Deliberate Non-Canonization

Belum dibuat sebagai Canon Noble House:

```text
ADDITIONAL DUcal Houses: NONE YET
ADDITIONAL MARQUIS HOUSES: NONE YET
ADDITIONAL COUNT HOUSES: NONE YET
CITY-SPECIFIC NOBLE HOUSES: NONE YET
MAGICAL DYNASTIES: NONE YET
ANCIENT BLOODLINE HOUSES: NONE YET
RELIGIOUS NOBLE HOUSES: NONE YET
```

Kategori tersebut baru dibuat jika ada kebutuhan governance, economy, military, magic, history, atau gameplay yang nyata.

## 10. NPC Dependency

```text
CANON NOBLE HOUSE
↓
NOBLE TITLE / DOMAIN CONTEXT
↓
NOBLE NPC
↓
INDIVIDUAL RELATIONSHIPS / SUCCESSION / CAPABILITIES
```

House record tidak mengarang spouse, child, sibling, heir, personal magic, personal wealth, atau personal military strength NPC.

Untuk `House Qasrane`, office of the reigning Sovereign sudah Canon sebagai leadership context; identitas personal sovereign dibuat pada tahap **Noble NPC**.

## 11. Canon Safety

- Noble House tidak otomatis memiliki sovereignty atas domain yang disebutkan.
- `DOMAIN_CONTEXT` tidak sama dengan ownership; legal grant, control, administration, claim, influence, dan occupation tetap berbeda.
- House tidak otomatis memiliki monopoly atas resource atau trade.
- House tidak otomatis memiliki magic.
- House tidak otomatis memiliki standing army.
- House membership tidak menentukan race, class, skill, morality, personality, atau capability.
- Magic-specific claims harus kembali ke `09_MAGIC_SYSTEM.md`.
- Political relations antar-House belum dibuat hanya berdasarkan nama atau fungsi.
- Semua future House changes wajib melalui resolution, state validation, origin, dan history.

## 12. Final Principle

> **Canon Noble House dibuat untuk memberi struktur nyata pada kerajaan. Jumlahnya sengaja kecil: cukup untuk membentuk Crown, ekonomi strategis, militer, frontier, dan magic context tanpa mengubah dunia menjadi katalog keluarga bangsawan.**
