# ELDORIA WORLD — REPUTATION

> **Module:** 20 — Reputation
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan reputation sebagai social/contextual state yang menggambarkan bagaimana suatu entity dipandang oleh target atau community tertentu.

Reputation bukan moral score universal.

## 2. Reputation Identity

Reputation record persisten dapat memiliki:

```text
REPUTATION_ID
SUBJECT_ID
TARGET_ID / COMMUNITY_ID
DIMENSION / CATEGORY
VALUE / STATUS
EVIDENCE
CURRENT_STATE
ORIGIN
HISTORY
STATE_VERSION
```

Field yang belum diketahui = `???`.

## 3. Contextual Nature

Reputation harus memiliki konteks.

Contoh konteks dapat berupa:

- individu,
- NPC group,
- faction,
- settlement,
- guild,
- profession,
- region,
- atau community lain.

Reputation di satu target tidak otomatis sama dengan reputation di target lain.

## 4. Dimensions

Dimension dapat merepresentasikan hal seperti:

- trust,
- reliability,
- competence,
- hostility,
- honor,
- notoriety,
- criminal suspicion,
- service record,
- atau kategori lain yang relevan.

Tidak ada daftar dimension universal yang wajib digunakan.

## 5. Evidence

Reputation harus memiliki dasar evidence atau source yang dapat ditelusuri.

Evidence dapat berasal dari:

- observed action,
- transaction,
- quest outcome,
- faction record,
- testimony,
- rumor,
- public event,
- combat,
- contract,
- atau mechanism lain yang sah.

Rumor tidak otomatis menjadi fact.

## 6. Information Boundary

Reputation yang dimiliki Player, Character, NPC, atau faction dapat berbeda.

Character tidak otomatis mengetahui reputation internal yang dimiliki pihak lain.

## 7. Change

Reputation dapat berubah akibat validated action/event.

Flow:

```text
EVIDENCE / ACTION / EVENT
↓
TARGET INTERPRETATION / RESOLUTION
↓
REPUTATION STATE DELTA
↓
VALIDATION
↓
ATOMIC PERSISTENCE
↓
HISTORY + ORIGIN
```

## 8. Magnitude & Scale

Module ini tidak menetapkan universal numerical scale, cap, decay rate, threshold, atau conversion formula.

Jika sebuah faction, settlement, atau system menggunakan skala tertentu, skala tersebut harus berasal dari source/state/module yang sah.

## 9. Decay & Persistence

Reputation dapat bertahan, berubah, atau berkurang jika mechanism yang berlaku mendefinisikannya.

Tidak boleh ada automatic decay hanya karena waktu berlalu tanpa rule yang sah.

## 10. Social Consequences

Reputation dapat memengaruhi:

- trust,
- prices,
- access,
- recruitment,
- quest availability,
- faction relations,
- security response,
- cooperation,
- hostility,
- atau social opportunities.

Pengaruh tidak otomatis; outcome tetap ditentukan oleh relevant resolution.

## 11. Multiple Perspectives

Dua faction dapat memiliki reputation berbeda terhadap subject yang sama.

Tidak ada kewajiban dunia memiliki satu reputation global untuk setiap character/NPC.

## 12. Manipulation & False Information

Reputation dapat dipengaruhi oleh informasi yang salah, propaganda, deception, forged records, atau mekanisme lain jika sistem mengizinkannya.

Namun perubahan tetap harus memiliki Cause + Origin + History.

## 13. Relationship Integration

Reputation dapat memengaruhi relationship tetapi tidak identik dengan relationship.

`04_FACTIONS.md` tetap menjadi authority untuk faction identity/relationship framework; module ini menyediakan social reputation state yang dapat menjadi input resolution.

## 14. Resolution Safety

AI GM dilarang menaikkan reputation hanya untuk memberi Player akses/reward.

Setiap material change harus berasal dari evidence/action/event yang valid dan dipersistenkan secara atomic.

## 15. Dependencies

`04_FACTIONS` + `05_CHARACTER_SYSTEM` + `16_NPC_SYSTEM`.

Integrasi: `11_ECONOMY`, `17_QUEST_SYSTEM`, `18_WORLD_EVENTS`, `19_FACTION_SYSTEM`, `25_WORLD_STATE`, `26_CHARACTER_STATE`, `27_NPC_STATE`, `30_HISTORY_SYSTEM`, `31_ORIGIN_LOG`, `33_ACTION_RESOLVER`, `34_STATE_VALIDATOR`, `35_SAVE_PIPELINE`.

## 16. Canon Safety

Tidak ada universal morality score.

Tidak ada universal reputation number.

Tidak ada universal decay.

Tidak ada universal social outcome.

## 17. Final Principle

> **Reputation adalah ingatan sosial yang kontekstual; ia dibentuk oleh evidence dan tindakan yang diketahui target, bukan oleh satu angka moral global.**
