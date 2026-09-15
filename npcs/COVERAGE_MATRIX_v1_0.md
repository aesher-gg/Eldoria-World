# ELDORIA WORLD — CANON NPC COVERAGE MATRIX v1.0

## Scope Targets

| Scope | Units | Minimum each | Minimum coverage |
|---|---:|---:|---:|
| Empire | 1 | ≥25 | ≥25 |
| Kingdom | 5 | ≥10 | ≥50 |
| City | 20 | ≥5 | ≥100 |
| Settlement | 40 | ≥3 | ≥120 |
| **Total** | **66** | — | **≥295 scope coverage** |

This is a planning matrix. It creates **zero individual NPCs**. The 295 figure is scope coverage, not 295 unique NPCs.

## Authority Chain

```text
CANON GEOGRAPHY
↓
POPULATION MODEL
↓
GOVERNANCE / FACTION CONTEXT
↓
FACTION CANON REGISTRY
↓
NPC COVERAGE MATRIX
↓
INDIVIDUAL CANON NPC
```

## Empire

`EMPIRE-001 Valthera` → target ≥25.

Faction context: `FACTION-001`, `FACTION-002`, `FACTION-003`.

Planning bands: Government/Administration ≥8; Security/Defense ≥6; Inter-kingdom Trade ≥4; Strategic ≥3; Specialist ≥4.

Current Canon coverage is 6 individual NPCs. They occupy real functions across head-of-state, government administration, defense coordination, and trade administration. Remaining planning bands are needs to evaluate, not automatic creation orders.

## Kingdoms

| Kingdom | Target | Faction context | Coverage bands |
|---|---:|---|---|
| KINGDOM-001 Valedorn | ≥10 | 101/102/103/104 | governance, security, river trade, agriculture, specialist |
| KINGDOM-002 Brannor | ≥10 | 111/112/113/114 | governance, security, mining, mountain transport, specialist |
| KINGDOM-003 Mariselle | ≥10 | 121/122/123/124 | governance, security, maritime trade, seafaring/shipbuilding, specialist |
| KINGDOM-004 Sylvaran | ≥10 | 131/132/133/134 | governance, frontier, forestry, craft, specialist |
| KINGDOM-005 Sahrad | ≥10 | 141/142/143/144 | governance, security, caravan trade, pastoral, specialist |

Current individual Kingdom coverage: Valedorn 2, Brannor 2, Mariselle 2, Sylvaran 2, Sahrad 1. Each listed band is a planning target, not automatic NPC creation.

## Cities

Every city requires ≥5 Canon NPC. City administration faction is primary context; kingdom faction context may be used when materially justified.

| City IDs | Cities | Target each | Primary faction IDs |
|---|---|---:|---|
| CITY-001–004 | Varenhold, Averen, Goldmere, Thornwick | ≥5 | FACTION-201–204 |
| CITY-005–008 | Durnhaven, Kharhold, Ferren, Frostwatch | ≥5 | FACTION-205–208 |
| CITY-009–012 | Port Aureon, Southport, Azurehold, Westhaven | ≥5 | FACTION-209–212 |
| CITY-013–016 | Elaris, Sylford, Riverwyn, Wildmere | ≥5 | FACTION-213–216 |
| CITY-017–020 | Qasrane, Sarakh, Caravanser, Sunscar | ≥5 | FACTION-217–220 |

## Settlements

Every settlement requires ≥3 Canon NPC. There is no settlement-specific Canon faction in v1.0. City/Kingdom faction context may be used only when materially justified.

| Settlement IDs | City | Target each | Context |
|---|---|---:|---|
| SETTLEMENT-001–008 | Varenhold / Averen / Goldmere / Thornwick | ≥3 | city faction + relevant K-001 faction |
| SETTLEMENT-009–016 | Durnhaven / Kharhold / Ferren / Frostwatch | ≥3 | city faction + relevant K-002 faction |
| SETTLEMENT-017–024 | Port Aureon / Southport / Azurehold / Westhaven | ≥3 | city faction + relevant K-003 faction |
| SETTLEMENT-025–032 | Elaris / Sylford / Riverwyn / Wildmere | ≥3 | city faction + relevant K-004 faction |
| SETTLEMENT-033–040 | Qasrane / Sarakh / Caravanser / Sunscar | ≥3 | city faction + relevant K-005 faction |

## Faction Assignment

Faction references are context only. They do not create membership, rank, authority, access, reputation, resources, knowledge, or loyalty. If no Canon faction is materially appropriate, use `???` or an allowed Dynamic Faction. Never create a Canon faction to fill a quota.

## Role Integrity

Roles must be justified by established geography, population, governance, economy, faction, or other Canon context. Suitable bands include governance, administration, security, military, trade, agriculture, mining, transport, logistics, maritime, shipbuilding, forestry, craft, pastoral, caravan, frontier, services, specialist, and community.

Unsupported religious, noble-house, academic, criminal, adventuring, or other institutional roles remain `???` until valid Canon context exists.

## Overlap Rules

**Allowed:** genuine cross-scope officials, faction leaders, regional specialists, and settlement figures with real wider influence.

**Forbidden:** reuse solely to reach quota, artificial authority, or automatic scope relevance from geographic containment.

## Anti-Filler / Anti-Duplicate

Reject candidates created only for quota, without material function/agency, with unsupported location/background, with template duplication, or with unverifiable Origin/knowledge boundary/Race.

Before creation:

```text
CANON NPC REGISTRY
↓
EXISTING CANON NPC RECORDS
↓
PERSISTENT DYNAMIC NPCS
↓
IDENTITY / ROLE / LOCATION / FACTION COLLISION CHECK
↓
RELATIONSHIP / BACKGROUND COLLISION CHECK
↓
CANONIZATION
```

## Race Safety

Every Canon NPC must use an active `RACE_CANON_ID` from `races/CANON_REGISTRY.md`. Race must not be inferred from name, location, role, faction, appearance stereotype, or profession.

## Canonization Gate

```text
[ ] Coverage need valid
[ ] Geography verified
[ ] Population context verified
[ ] Governance context verified
[ ] Faction context verified
[ ] Race Canon available
[ ] No duplicate
[ ] Role materially justified
[ ] Agency justified
[ ] Knowledge boundary defined
[ ] Origin traceable
[ ] Identity schema complete
```

## Status

```text
EMPIRE TARGET: ≥25
KINGDOM TARGET: ≥10 × 5 = ≥50
CITY TARGET: ≥5 × 20 = ≥100
SETTLEMENT TARGET: ≥3 × 40 = ≥120
TOTAL SCOPE COVERAGE TARGET: ≥295

INDIVIDUAL CANON NPC CREATED: 15
INDIVIDUAL CANON NPC REGISTERED: 15
```

> Coverage Matrix mengatur pemerataan kebutuhan Canon NPC; bukan alasan untuk membuat NPC filler.
