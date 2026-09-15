# ELDORIA WORLD — STATE VALIDATOR

> **Module:** 34 — State Validator
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Hard validation gate before persistence

## 0. PURPOSE

State Validator memeriksa apakah hasil Action Resolver sah untuk diterapkan pada authoritative state.

Validator adalah gate, bukan resolver. Validator tidak boleh mengarang koreksi atau mengubah delta secara diam-diam.

## 1. INPUT

```text
TURN_ID
RESOLUTION RESULT
STATE DELTAS
AUTHORITATIVE CURRENT STATE
STATE_VERSION(S)
ROUTING PLAN
APPLICABLE MODULE RULES
CAUSES
ORIGIN PROPOSALS
```

## 2. VALIDATION ORDER

```text
IDENTITY
↓
RACE CANON IDENTITY
↓
TURN / IDEMPOTENCY
↓
STATE VERSION
↓
AUTHORITY
↓
PREREQUISITE / CAPABILITY
↓
RESOURCE / OWNERSHIP
↓
TARGET / LOCATION / TIME
↓
LIFECYCLE
↓
DELTA CONSISTENCY
↓
CROSS-ENTITY CONSISTENCY
↓
CAUSE / ORIGIN / HISTORY COMPLETENESS
↓
FINAL PASS / REJECT
```

## 3. IDENTITY VALIDATION

Periksa:

- entity ID valid dan stabil,
- actor/target benar,
- generated entity memiliki identity yang sah,
- tidak ada duplicate persistent identity,
- references menunjuk entity yang benar.

Untuk Player Character, `CHARACTER_ID` harus berasal dari Character Record/Player Registry resmi.

Untuk Canon NPC, `NPC_ID` harus cocok dengan Canon Registry/record bila entity tersebut adalah Canon NPC.

Untuk Monster Canon, `MONSTER_CANON_ID` harus cocok dengan Canon Registry bila species tersebut diklaim sebagai Canon.

## 4. RACE CANON ID VALIDATION

`RACE_CANON_ID` adalah identity reference Canon dan bukan free-form runtime label.

Jika Character, NPC, Monster, Population Model, atau entity lain memiliki field `RACE_CANON_ID`, Validator wajib memastikan:

```text
RACE_CANON_ID
↓
races/CANON_REGISTRY.md
↓
MATCHING ACTIVE CANON RACE
```

Hard rules:

- `RACE_CANON_ID` harus exact match dengan Race Canon Registry;
- Race yang tidak ada di registry = `REJECT` untuk state/identity yang mengharuskan Race Canon;
- `???` boleh dipertahankan sebagai Unknown hanya bila module/entity memang mengizinkan Race belum diketahui; `???` tidak dapat diperlakukan sebagai Race ID;
- nama ras, subrace, lineage, clan, ethnicity, culture, faction, class, atau appearance tidak boleh menggantikan `RACE_CANON_ID`;
- Dynamic NPC/entity yang menggunakan Race harus memilih Race dari registry, bukan membuat Race baru;
- `RACE_CANON_ID` tidak boleh berubah melalui narrative atau State Delta biasa tanpa mechanism perubahan identity yang sah;
- perubahan definisi, lore, biology, tier/classification, atau status Canon Race memerlukan Admin Canon update, bukan runtime state mutation;
- Race Canon tidak secara otomatis menentukan class, skill, magic, faction, personality, morality, atau outcome.

### Race Validation Matrix

| Kondisi | Hasil |
|---|---|
| `RACE_CANON_ID` valid dan registry match | PASS untuk race identity |
| `RACE_CANON_ID` tidak ditemukan | REJECT |
| Race name ada tetapi ID tidak ada | REJECT / unresolved sesuai entity contract |
| `RACE_CANON_ID = ???` dan Race wajib diketahui | REJECT |
| `RACE_CANON_ID = ???` dan Race boleh Unknown | PASS sebagai Unknown, tanpa substitusi |
| Runtime mencoba membuat Race Canon baru | REJECT |
| Runtime mencoba mengubah Canon Race definition | REJECT; Admin update required |

## 5. TURN & IDEMPOTENCY

Validator harus memastikan `TURN_ID` belum berhasil committed.

Jika transaction dengan `TURN_ID` yang sama telah committed:

```text
STATUS = ALREADY_COMMITTED
NO SECOND COMMIT
```

## 6. STATE VERSION

Setiap affected persistent state harus dibandingkan dengan version yang ditangkap saat load.

```text
LOADED VERSION == CURRENT VERSION → VALIDATION MAY CONTINUE
LOADED VERSION != CURRENT VERSION → REJECT STALE TRANSACTION
```

Transaction stale harus reload dan re-resolve melalui pipeline.

## 7. AUTHORITY

Validator memastikan perubahan berasal dari module yang memiliki kewenangan atas domain tersebut.

Authority dipisahkan sebagai berikut:

```text
CANON / REGISTRY
→ identity + official definition

CURRENT STATE
→ kondisi entity saat ini

HISTORY / ORIGIN
→ bukti perubahan dan provenance
```

AI GM runtime tidak boleh mengubah Canon Registry secara implisit.

Player submission tidak sama dengan Admin registration.

Narrative tidak pernah menjadi authority.

## 8. PLAYER CHARACTER VALIDATION

Player Character hanya valid sebagai PC resmi jika:

```text
PLAYER_ID
+
CHARACTER_ID
+
CHARACTER RECORD
+
ADMIN REGISTRATION
```

terverifikasi.

AI GM tidak boleh menciptakan atau mengganti identity dasar PC melalui state delta biasa.

Jika PC memiliki `RACE_CANON_ID`, Race tersebut harus lolos Section 4 sebelum identity/state dianggap valid.

## 9. CANON ENTITY VALIDATION

Untuk Canon NPC dan Monster Canon:

- identity Canon harus berasal dari registry/record resmi;
- generation tidak boleh menciptakan duplicate Canon identity;
- runtime state boleh berubah melalui resolution yang sah;
- perubahan terhadap Canon definition/lore/tier tidak boleh disamarkan sebagai state change biasa;
- perubahan Canon membutuhkan Admin Canon update.

## 10. CAPABILITY & PREREQUISITE

Periksa action terhadap:

- class,
- skill,
- magic access,
- equipment,
- condition,
- location,
- faction access,
- quest/event requirements,
- dan prerequisite lain yang didefinisikan module.

Tidak boleh ada free capability atau progression.

## 11. RESOURCE / OWNERSHIP

Periksa konsistensi:

- currency,
- inventory,
- item ownership/possession,
- charges,
- durability,
- crafting/alchemy inputs,
- magic resources,
- vitality/survival resources,
- party/companion resources jika relevan.

Tidak boleh mengurangi resource yang tidak tersedia.

## 12. TARGET / LOCATION / TIME

Validator memeriksa bahwa:

- target masih valid,
- target dapat dipengaruhi action,
- lokasi konsisten,
- action tidak melompati batas travel/time,
- World Time dan Local Environment tidak kontradiktif,
- time delta tidak diterapkan dua kali.

## 13. LIFECYCLE

Perubahan harus sesuai lifecycle entity.

Entity `DEAD`, `RETIRED`, `CANCELLED`, atau status terminal lain tidak boleh melakukan action yang dilarang oleh module.

Revival hanya valid melalui mechanism yang sah.

## 14. DELTA CONSISTENCY

Setiap State Delta harus:

- memiliki BEFORE yang sesuai authoritative state,
- memiliki perubahan eksplisit,
- menghasilkan AFTER yang dapat dihitung/ditentukan,
- tidak menciptakan contradiction,
- tidak menggunakan `???` sebagai angka tersembunyi,
- tidak mengubah field yang tidak disentuh resolution tanpa alasan.

`???` tetap Unknown/Unresolved dan bukan zero/empty/false.

## 15. CROSS-ENTITY CONSISTENCY

Untuk transaction multi-entity, semua perubahan yang secara logis saling bergantung harus hadir dalam atomic bundle.

Contoh:

```text
Buyer currency -X
Seller currency +X
Item ownership → Buyer
```

Jika salah satu required delta hilang, transaction ditolak.

## 16. CAUSE / ORIGIN / HISTORY

Setiap material state change harus memiliki:

```text
CAUSE
ORIGIN
STATE CHANGE
HISTORY RECORD PROPOSAL
```

Origin harus menunjuk sumber yang benar. Tidak boleh dibuat untuk membenarkan perubahan yang tidak terjadi.

## 17. DYNAMIC GENERATION

Generated entity hanya PASS jika memiliki, sesuai kebutuhan:

```text
STABLE ID
ORIGIN
GENERATION DATA
CURRENT STATE
HISTORY
```

Generator tidak boleh menggantikan entity persisten yang sudah ada.

Untuk generated entity yang memiliki `RACE_CANON_ID`, registry match wajib dilakukan sebelum PASS.

## 18. NO SILENT CORRECTION

Jika delta invalid, Validator:

```text
REJECT
↓
REPORT ERROR
```

Validator tidak boleh diam-diam mengubah HP, gold, item, outcome, waktu, Race ID, atau field lain untuk membuat transaction valid.

## 19. RESULT

Output minimal:

```text
TURN_ID
VALIDATION_STATUS = PASS | REJECT | ALREADY_COMMITTED
VALIDATED_ENTITY_IDS
VALIDATED_STATE_VERSIONS
VALIDATED_RACE_CANON_IDS
ERRORS
WARNINGS
VALIDATED_DELTAS
VALIDATED_CAUSES
VALIDATED_ORIGINS
```

`WARNINGS` tidak boleh dipakai untuk melewati hard invariant.

## 20. NO MUTATION

State Validator tidak melakukan persistent mutation.

```text
RESOLVER → PROPOSE
VALIDATOR → CHECK
SAVE PIPELINE → COMMIT
```

## 21. FAILURE

Jika validation gagal:

```text
REJECT
↓
NO STATE CHANGE
↓
NO FALSE HISTORY
↓
NO FALSE ORIGIN
↓
RELOAD / RE-RESOLVE / ABORT
```

Final principle:

> **Tidak ada State Delta yang sah hanya karena resolver mengusulkannya; Validator harus membuktikannya terhadap Canon, registry, rules, dan authoritative state — termasuk `RACE_CANON_ID` bila Race relevan.**
