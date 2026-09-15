# ELDORIA WORLD — ACTION RESOLVER

> **Module:** 33 — Action Resolver
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Role:** Central action simulation and State Delta generation

## 0. PURPOSE

Action Resolver mengubah Player/NPC/World intent menjadi outcome yang ditentukan sistem, lalu menghasilkan State Delta yang siap divalidasi.

Resolver tidak boleh menarasikan atau menganggap outcome sebagai committed sebelum validation dan persistence berhasil.

## 1. INPUT

```text
TURN_ID
PLAYER / ACTOR INTENT
ROUTING PLAN
LOADED AUTHORITATIVE STATE
RELEVANT MODULE RULES
WORLD TIME / LOCAL ENVIRONMENT
INFORMATION SCOPE
STATE_VERSION(S)
```

## 2. INTENT NORMALIZATION

Resolver boleh menstrukturkan intent agar dapat diproses, tetapi tidak boleh mengubah maksud Player menjadi action lain.

Intent harus dipisahkan dari desired outcome.

```text
PLAYER INTENT ≠ GUARANTEED OUTCOME
```

Contoh: `Attack Goblin` berarti mencoba menyerang, bukan berarti hit atau menang.

## 3. PRECONDITION CHECK

Sebelum resolution, periksa bila relevan:

- actor identity/status,
- target identity/status,
- capability,
- class/skill/magic,
- equipment,
- resource,
- prerequisite,
- ownership/authority,
- location,
- time,
- condition/vitality,
- information/knowledge,
- applicable module restrictions.

Kegagalan prerequisite menghasilkan failed/unresolved action tanpa state mutation yang tidak sah.

## 4. SIMULATION

Resolver menentukan outcome berdasarkan rules, state, capability, environment, information, dan mekanisme uncertainty/probability yang sah.

Tidak boleh menggunakan convenience narrative untuk memaksa hasil.

NPC, monster, faction, companion, environment, dan world systems mempertahankan agency sesuai module masing-masing.

## 5. MULTI-ENTITY RESOLUTION

Action dapat menyentuh banyak entity.

Setiap perubahan harus diidentifikasi per entity:

```text
ENTITY_ID
BEFORE
CAUSE
PROPOSED CHANGE
EXPECTED AFTER
```

Cross-entity consistency wajib dijaga. Contoh transaksi tidak boleh hanya mengurangi inventory buyer tanpa menambah aset seller bila kedua perubahan merupakan bagian dari transaksi.

## 6. TIME RESOLUTION

Jika action menghabiskan waktu, Resolver menghasilkan time delta sesuai module yang berlaku sebelum resolution berikutnya menggunakan waktu baru.

Tidak boleh ada time skip tersembunyi.

## 7. STATE DELTA

Output utama Resolver adalah State Delta, bukan direct mutation.

Contoh:

```text
STATE DELTA
Character HP: -12
Monster condition: Injured
Character position: changed
World Time: +duration
```

Setiap delta material wajib memiliki Cause dan Origin yang dapat direkam.

## 8. DYNAMIC GENERATION

Jika resolution membutuhkan monster/NPC/loot/quest/event/entity baru dan module mengizinkannya:

```text
CHECK PERSISTENT ENTITY FIRST
↓
GENERATE ONLY IF NEEDED
↓
ASSIGN STABLE ID
↓
RECORD GENERATION DATA / SEED WHEN RELEVANT
↓
PROPOSE STATE + ORIGIN + HISTORY
```

Generation tidak boleh menjadi jalan pintas untuk memberi Player hadiah atau keuntungan.

## 9. FAILURE / PARTIAL OUTCOME

Resolver dapat menghasilkan success, failure, partial success, interruption, retreat, capture, death, atau outcome lain bila didukung rules.

Outcome failure tidak otomatis berarti tidak ada perubahan; jika konsekuensi valid terjadi, delta tetap harus dibuat dan divalidasi.

Namun tidak boleh ada partial mutation di luar transaction bundle.

## 10. NO DIRECT COMMIT

Action Resolver **dilarang**:

- menulis state sebagai committed,
- menghapus History,
- membuat Origin palsu,
- melewati State Validator,
- melewati Save Pipeline,
- menarasikan hasil final sebelum commit.

## 11. RESOLUTION RESULT

Output internal minimal:

```text
TURN_ID
RESOLUTION_STATUS
NORMALIZED_INTENT
OUTCOME
AFFECTED_ENTITY_IDS
STATE_DELTAS
TIME_DELTA
CONSEQUENCES
GENERATED_ENTITY DATA (jika ada)
CAUSES
ORIGIN PROPOSALS
CAPTURED_STATE_VERSIONS
VALIDATION_PAYLOAD
FAILURE_REASON (jika ada)
```

History proposal dapat disiapkan oleh Resolver, tetapi final record harus mengikuti History/Origin modules dan Save Pipeline.

## 12. CONCURRENCY

Setiap affected persistent state membawa `STATE_VERSION` yang digunakan saat load.

Jika versi berubah sebelum commit:

```text
REJECT STALE RESOLUTION
↓
RELOAD LATEST STATE
↓
RE-RESOLVE
```

Resolver tidak boleh menggabungkan state lama dan baru secara diam-diam.

## 13. IDEMPOTENCY

`TURN_ID` yang sudah committed tidak boleh di-resolve ulang sebagai transaction baru.

Jika status commit tidak diketahui setelah crash, Save Pipeline harus memeriksa commit record/state sebelum retry.

## 14. INFORMATION BOUNDARY

Resolution hanya menggunakan knowledge yang sah untuk actor dan entity yang relevan.

Player knowledge tidak boleh otomatis menjadi Character knowledge.

Hidden information tidak boleh digunakan untuk memberi outcome tanpa mekanisme yang sah.

## 15. HANDOFF

```text
ROUTING PLAN
↓
LOAD VERIFIED STATE / MODULES
↓
INTENT NORMALIZATION
↓
PRECONDITION CHECK
↓
SIMULATE
↓
STATE DELTA
↓
CAUSE + ORIGIN PROPOSAL
↓
STATE VALIDATOR
↓
SAVE PIPELINE
```

Final principle:

> **Action Resolver menentukan apa yang terjadi melalui simulation; ia tidak menentukan apa yang nyaman diceritakan.**
