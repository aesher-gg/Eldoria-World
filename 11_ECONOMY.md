# ELDORIA WORLD — ECONOMY

> **Module:** 11 — Economy
> **Canon:** ELDORIA CANON v1.0 — LOCKED
> **Status:** Admin Canon v1.0

## 1. Purpose

Mendefinisikan framework ekonomi Eldoria: currency, value, market, trade, transaction, supply/demand, dan economic state.

## 2. Currency

Currency adalah resource ekonomi yang harus memiliki identity/unit yang jelas bila digunakan secara persisten.

```text
CURRENCY_ID
NAME
DENOMINATION
EXCHANGE_RULE
ORIGIN
```

Tidak ada mata uang atau nilai tukar global yang boleh ditebak jika belum ditetapkan data Canon/world.

## 3. Economic State

Settlement, faction, character, merchant, dan entity lain dapat memiliki economic state yang berbeda.

Economic state dapat mencakup:

```text
BALANCE
ASSETS
DEBTS
PRICES
SUPPLY
DEMAND
MARKET_ACCESS
```

## 4. Value vs Price

Value adalah penilaian relatif terhadap item/resource.

Price adalah hasil transaksi atau harga yang berlaku pada context tertentu.

Keduanya tidak otomatis sama.

## 5. Dynamic Pricing

Harga dapat dipengaruhi oleh:

- supply,
- demand,
- scarcity,
- location,
- season,
- security,
- merchant policy,
- faction influence,
- reputation,
- event,
- dan kondisi pasar.

Formula aktual hanya berlaku jika didefinisikan oleh implementation.

## 6. Transactions

Transaksi minimal memiliki:

```text
BUYER
SELLER
ITEM / SERVICE
QUANTITY
PRICE
CURRENCY
TERMS
CAUSE
ORIGIN
```

Transaction harus atomik: asset buyer dan seller tidak boleh menghasilkan keadaan parsial.

## 7. Ownership & Fraud

Theft, debt, counterfeit, fraud, confiscation, tax, reward, dan transfer dapat memengaruhi economic state sesuai resolution.

Possession tidak otomatis membuktikan ownership.

## 8. Services & Labor

Jasa, upah, pekerjaan, kontrak, dan pembayaran mengikuti economic context dan terms yang sah.

No free service/resource.

## 9. Faction & Settlement Economy

Economy settlement/faction dapat memengaruhi availability dan pricing, tetapi tidak menggantikan state aktual.

## 10. Information Boundary

Harga atau kondisi ekonomi yang diketahui Player tidak otomatis diketahui Character/NPC. Information State berlaku.

## 11. Validation

Validator memeriksa balance, quantity, ownership, price/terms, currency validity, transaction legality, state version, Cause, Origin, dan `TURN_ID`.

## 12. Dependencies

`03_CITIES_AND_SETTLEMENTS` + `04_FACTIONS` + `05_CHARACTER_SYSTEM` + `10_EQUIPMENT_SYSTEM` → module ini.

Integrasi: `15_LOOT_GENERATION`, `17_QUEST_SYSTEM`, `19_FACTION_SYSTEM`, `20_REPUTATION`, `21_CRAFTING`, `22_ALCHEMY`, `34_STATE_VALIDATOR`.

## 13. Canon Safety

Module ini tidak menetapkan harga tetap, inflasi, mata uang spesifik, atau exchange rate tanpa source yang sah.

## 14. Final Principle

> **Ekonomi adalah state kontekstual; setiap transaksi harus memiliki counterpart, terms, sumber, dan konsekuensi yang konsisten.**
