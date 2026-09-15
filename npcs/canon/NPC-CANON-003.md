# ELDORIA WORLD — CANON NPC

> **Authority:** Admin
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Active Canon NPC

## Identity

```text
NPC_ID: NPC-CANON-003
NPC_CLASS: CANON
NAME: Corvin Hale
RACE_CANON_ID: RACE-003
ROLE / TYPE: Koordinator Administrasi Perdagangan Kekaisaran — Penghubung Jalur Antar-Kerajaan
SETTLEMENT_ID: ???
CITY_ID: ???
REGION_ID: ???
KINGDOM_ID: ???
EMPIRE_ID: EMPIRE-001
FACTION: FACTION-003 — Administrasi Perdagangan Kekaisaran
CANON_ORIGIN: Admin Canon
CANON_STATUS: ACTIVE
```

## Background

Corvin Hale works within the existing imperial trade-administration context, helping coordinate commercial information and administrative communication across the five kingdoms. His role supports inter-kingdom trade coordination without assuming ownership of local markets, merchant guilds, or kingdom economies.

## Origin

Created to give the existing `FACTION-003` a concrete Canon individual whose function is inter-kingdom commercial coordination, while leaving unresolved economic institutions and detailed imperial policy untouched.

## Goals

- maintain accurate communication concerning inter-kingdom trade administration;
- identify inconsistencies in commercial records that require clarification;
- facilitate lawful communication between relevant authorities and trade organizations.

## Core Relationships

```text
FACTION-003 → Canon-established organizational relationship
KINGDOM-001..005 → inter-kingdom trade coordination context; personal relationship = ???
Merchant organizations → contact when legitimately required; specific relationships = ???
OTHER NPCs → ???
```

## Capabilities

- commercial record coordination;
- document comparison and administrative verification;
- trade-related correspondence;
- procedural negotiation within established authority.

He does not automatically control prices, local markets, merchant guilds, taxation, tariffs, or kingdom economic policy.

## Knowledge Boundary

He knows trade information legitimately obtained through his duties. Private merchant agreements, local economic conditions not reported to him, confidential contracts, and kingdom-specific economic decisions outside his access remain `???`.

## Canon Safety

- Identity, race, role, faction, goals, capabilities, and origin are Canon.
- Specific location, rank, personal relationships, and detailed economic authority remain `???`.
- This record does not create new ministries, trade laws, taxes, tariffs, or economic institutions.
- Runtime state changes require the NPC State, History, Origin Log, validation, and atomic persistence pipeline.
