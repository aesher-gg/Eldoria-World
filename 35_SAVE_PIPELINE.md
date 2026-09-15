# ELDORIA WORLD — SAVE PIPELINE

> **Module:** 35 — Save Pipeline
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Transaction preparation, atomic persistence, concurrency, and recovery

## 0. PURPOSE

Save Pipeline adalah gerbang persistence terakhir. Pipeline memastikan satu Turn Transaction diterapkan secara atomik dan dapat dipulihkan tanpa partial state, false History, atau false Origin.

## 1. TRANSACTION MODEL

Setiap Player Message membuat satu transaction:

```text
TURN_ID
TRANSACTION_ID
ACTOR_ID
LOADED STATE VERSION(S)
```

`TURN_ID` harus unik dan idempotent.

## 2. COMPLETE PIPELINE

```text
PLAYER MESSAGE
↓
CREATE TURN_ID
↓
FETCH / VERIFY INDEX
↓
LOAD STATE + MODULES
↓
CHECK STATE_VERSION
↓
ROUTE
↓
RESOLVE
↓
STATE DELTA
↓
VALIDATE
↓
GENERATE HISTORY + ORIGIN
↓
PREPARE ATOMIC BUNDLE
↓
FINAL CONFLICT CHECK
↓
ATOMIC COMMIT
↓
COMMIT ACK / RECEIPT
↓
NARRATE
```

## 3. ATOMIC BUNDLE

Semua perubahan yang merupakan satu transaction harus dipersiapkan sebagai satu bundle, termasuk bila relevan:

```text
WORLD STATE CHANGES
CHARACTER STATE CHANGES
NPC STATE CHANGES
MONSTER STATE CHANGES
EVENT / QUEST STATE CHANGES
ITEM / ECONOMY CHANGES
PARTY / COMPANION CHANGES
HISTORY RECORDS
ORIGIN RECORDS
COMMIT METADATA
```

Bundle harus konsisten dan dapat divalidasi sebagai satu kesatuan.

## 4. FINAL CONFLICT CHECK

Sebelum commit, current persistent version harus masih sama dengan version yang digunakan saat resolution.

```text
EXPECTED VERSION == CURRENT VERSION
→ COMMIT ALLOWED

EXPECTED VERSION != CURRENT VERSION
→ COMMIT REJECTED
```

Jangan pernah melakukan silent overwrite terhadap state yang lebih baru.

## 5. ATOMIC COMMIT

Commit harus memperlakukan seluruh bundle sebagai satu transaction:

```text
STATE
+
HISTORY
+
ORIGIN
+
RELATED STATE CHANGES
+
COMMIT RECORD
```

Semua berhasil atau tidak ada perubahan persistent yang dianggap terjadi.

Jika storage tidak mampu menjamin atomicity yang dibutuhkan, transaction harus di-abort daripada mengklaim success.

## 6. STATE VERSION UPDATE

Setiap affected persistent state harus memperoleh version baru sesuai mekanisme state module.

Konsep:

```text
v17
↓
validated delta
↓
commit
↓
v18
```

Version update tidak boleh dilewati atau dilakukan dua kali untuk transaction yang sama.

## 7. COMMIT RECORD & IDEMPOTENCY

Setelah successful commit, sistem harus dapat mengenali bahwa `TURN_ID` telah committed.

Commit metadata minimal:

```text
TURN_ID
TRANSACTION_ID
COMMIT_STATUS
AFFECTED_ENTITY_IDS
RESULTING STATE VERSION(S)
COMMIT TIMESTAMP
```

Retry dengan TURN_ID yang sudah committed tidak boleh membuat duplicate state change, History, Origin, loot, reward, atau entity.

## 8. HISTORY & ORIGIN INTEGRITY

History dan Origin yang menyertai State Change harus menjadi bagian dari transaction yang sama.

Tidak sah:

```text
STATE COMMITTED
↓
HISTORY FAILED
```

atau:

```text
HISTORY COMMITTED
↓
STATE FAILED
```

Tidak boleh ada Origin yang menunjukkan transaction berhasil jika atomic commit tidak berhasil.

## 9. FAILURE & ROLLBACK

Jika validation, conflict check, atau commit gagal:

```text
REJECT / ROLLBACK
↓
NO PARTIAL COMMITTED STATE
↓
NO FALSE HISTORY
↓
NO FALSE ORIGIN
```

Transaction yang gagal dapat di-re-resolve setelah reload state terbaru jika penyebabnya stale state atau transient conflict.

## 10. CRASH RECOVERY

### Crash sebelum commit

Transaction dianggap belum terjadi kecuali commit record membuktikan sebaliknya.

### Crash setelah commit tetapi sebelum narrative

Runtime harus membaca commit record/current state dan menghasilkan narrative dari committed result tanpa mengulang transaction.

### Commit status tidak diketahui

Jangan langsung retry. Periksa commit record dan authoritative state terlebih dahulu.

## 11. RETRY RULE

Retry hanya sah setelah:

```text
CHECK COMMIT STATUS
↓
RELOAD LATEST STATE IF NEEDED
↓
RECHECK STATE VERSION
↓
RE-RESOLVE IF REQUIRED
↓
RE-VALIDATE
↓
NEW ATOMIC COMMIT ATTEMPT
```

Transaction lama tidak boleh dipaksa terhadap state baru.

## 12. PERSISTENCE ORDER

Urutan konseptual internal:

```text
PREPARE
↓
VALIDATE BUNDLE
↓
CONFLICT CHECK
↓
ATOMIC COMMIT
↓
ACK
```

History dan Origin tidak dianggap committed sebelum atomic commit berhasil.

## 13. NARRATIVE GATE

Narrative final hanya boleh dibuat setelah:

```text
RESOLUTION = SUCCESS / VALID OUTCOME
VALIDATION = PASS
PERSISTENCE = COMMITTED
```

Narrative harus berasal dari committed result dan tidak boleh menambahkan state yang tidak ada di commit.

## 14. AUDITABILITY

Setiap successful transaction harus dapat ditelusuri melalui:

```text
TURN_ID
→ TRANSACTION_ID
→ STATE DELTA
→ HISTORY_ID(S)
→ ORIGIN_ID(S)
→ COMMIT RECORD
```

Koreksi dilakukan melalui record koreksi sesuai History/Origin rules, bukan silent deletion.

## 15. TRANSIENT VS PERSISTENT DATA

Data sementara yang tidak memenuhi persistence threshold boleh tetap transient.

Begitu entity atau perubahan menjadi material/persistent, identity, state, History, dan Origin harus mengikuti aturan persistent system yang relevan.

## 16. SAVE INVARIANTS

Save Pipeline wajib menjamin:

- no partial transaction,
- no stale overwrite,
- no duplicate TURN_ID commit,
- no false History,
- no false Origin,
- no silent state loss,
- atomic multi-entity consistency,
- version integrity,
- deterministic retry behavior,
- narrative hanya setelah commit.

Final principle:

> **Continuity Eldoria berasal dari transaction yang benar-benar committed, bukan dari narasi yang diklaim telah terjadi.**
