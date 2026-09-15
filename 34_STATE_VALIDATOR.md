# ELDORIA WORLD — STATE VALIDATOR

> **Module:** 34 — State Validator
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Hard validation gate before persistence

## 0. PURPOSE

State Validator memeriksa apakah hasil Action Resolver sah untuk diterapkan pada authoritative state.

Validator adalah **gate**, bukan resolver. Validator tidak boleh mengarang koreksi atau mengubah delta secara diam-diam.

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

## 4. TURN & IDEMPOTENCY

Validator harus memastikan `TURN_ID` belum berhasil committed.

Jika transaction dengan `TURN_ID` yang sama telah committed:

```text
STATUS = ALREADY_COMMITTED
NO SECOND COMMIT
```

Jika belum committed, validation dapat dilanjutkan.

## 5. STATE VERSION

Setiap affected persistent state harus dibandingkan dengan version yang ditangkap saat load.

```text
LOADED VERSION == CURRENT VERSION → VALIDATION MAY CONTINUE
LOADED VERSION != CURRENT VERSION → REJECT STALE TRANSACTION
```

Transaction stale harus reload dan re-resolve melalui pipeline.

## 6. AUTHORITY

Validator memastikan perubahan berasal dari module yang memiliki kewenangan atas domain tersebut.

Module tidak boleh mengubah domain authoritative module lain tanpa mekanisme integrasi yang sah.

Narrative tidak pernah menjadi authority.

## 7. CAPABILITY & PREREQUISITE

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

## 8. RESOURCE / OWNERSHIP

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

## 9. TARGET / LOCATION / TIME

Validator memeriksa bahwa:

- target masih valid,
- target dapat dipengaruhi action,
- lokasi konsisten,
- action tidak melompati batas travel/time,
- World Time dan Local Environment tidak kontradiktif,
- time delta tidak diterapkan dua kali.

## 10. LIFECYCLE

Perubahan harus sesuai lifecycle entity.

Entity `DEAD`, `RETIRED`, `CANCELLED`, atau status terminal lain tidak boleh melakukan action yang dilarang oleh module.

Revival hanya valid melalui mechanism yang sah.

## 11. DELTA CONSISTENCY

Setiap State Delta harus:

- memiliki BEFORE yang sesuai authoritative state,
- memiliki perubahan eksplisit,
- menghasilkan AFTER yang dapat dihitung/ditentukan,
- tidak menciptakan contradiction,
- tidak menggunakan `???` sebagai angka tersembunyi,
- tidak mengubah field yang tidak disentuh resolution tanpa alasan.

`???` tetap Unknown/Unresolved dan bukan zero/empty/false.

## 12. CROSS-ENTITY CONSISTENCY

Untuk transaction multi-entity, semua perubahan yang secara logis saling bergantung harus hadir dalam atomic bundle.

Contoh:

```text
Buyer currency -X
Seller currency +X
Item ownership → Buyer
```

Jika salah satu required delta hilang, transaction ditolak.

## 13. CAUSE / ORIGIN / HISTORY

Setiap material state change harus memiliki:

```text
CAUSE
ORIGIN
STATE CHANGE
HISTORY RECORD PROPOSAL
```

Origin harus menunjuk sumber yang benar. Tidak boleh dibuat untuk membenarkan perubahan yang tidak terjadi.

## 14. DYNAMIC GENERATION

Generated entity hanya PASS jika memiliki, sesuai kebutuhan:

```text
STABLE ID
ORIGIN
GENERATION DATA
CURRENT STATE
HISTORY
```

Generator tidak boleh menggantikan entity persisten yang sudah ada.

## 15. NO SILENT CORRECTION

Jika delta invalid, Validator:

```text
REJECT
↓
REPORT ERROR
```

Validator tidak boleh diam-diam mengubah HP, gold, item, outcome, waktu, atau field lain untuk membuat transaction valid.

## 16. RESULT

Output minimal:

```text
TURN_ID
VALIDATION_STATUS = PASS | REJECT | ALREADY_COMMITTED
VALIDATED_ENTITY_IDS
VALIDATED_STATE_VERSIONS
ERRORS
WARNINGS
VALIDATED_DELTAS
VALIDATED_CAUSES
VALIDATED_ORIGINS
```

`WARNINGS` tidak boleh dipakai untuk melewati hard invariant.

## 17. NO MUTATION

State Validator tidak melakukan persistent mutation.

```text
RESOLVER → PROPOSE
VALIDATOR → CHECK
SAVE PIPELINE → COMMIT
```

## 18. FAILURE

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

> **Tidak ada State Delta yang sah hanya karena resolver mengusulkannya; Validator harus membuktikannya terhadap Canon, rules, dan authoritative state.**
