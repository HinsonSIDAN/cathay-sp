# Cathay Status Points (SP) Knowledge Base

A structured knowledge base on **Cathay (Cathay Pacific) Status Points calculation** — how many
Status Points a member earns per flight, by airline, cabin, fare class / fare type, and distance
zone. Covers Cathay Pacific, HK Express, and oneworld® / other partner airlines.

> Program: **Cathay membership programme** (formerly Marco Polo Club, relaunched 2023).
> Currency: **Status Points (SP)** determine membership status; **Asia Miles** are the spendable
> reward currency and are tracked here alongside SP where the source publishes both.

## Membership status thresholds

Status is earned within a **membership year**, and requires **at least one eligible sector flown
on Cathay Pacific** in addition to the points:

| Status | Status Points to upgrade / renew (within a membership year) |
|--------|-----|
| Green | — (joining tier, lifetime) |
| Silver | 300 |
| Gold | 600 |
| Diamond | 1,200 |

Upgrades happen as soon as the threshold is reached; only one status level can be progressed at a
time.

⚠️ **Programme change effective 1 January 2027**: Cathay has announced an enhanced membership
programme ("A Smoother, Simpler and Better Cathay Membership Programme") effective 1 Jan 2027,
with 2026 as a transition year (renewal/upgrade/downgrade during 2026 resets Status Points to
zero and memberships end 31 Dec 2026). See [docs/2027-programme-changes.md](docs/2027-programme-changes.md).

## How Status Points are calculated

Two distinct models, both table lookups on distance zone + booking class:

**1. Cathay Pacific-marketed flights** ([data/airlines/cathay-pacific.yaml](data/airlines/cathay-pacific.yaml)):

```
SP = cx_table[ distance zone (6 zones, post-2025-08-20) ][ cabin ][ fare classes × fare type (Flex/Essential/Light) ]
Asia Miles = SP × 100   (exact, every cell)
```

**2. Partner-marketed flights** ([data/partner-earning-model.yaml](data/partner-earning-model.yaml)):

```
Asia Miles    = rate% × actual miles flown        (rate% per airline + booking class)
Status Points = sp_matrix[ tier ][ distance zone ] (tier per airline + booking class;
                                                    legacy 6-zone scheme incl. Medium-1/Medium-2)
```

- **Status Points are earned only on Cathay Pacific and oneworld member airlines.**
  Non-oneworld partners (Air Canada, Air China, Air NZ, Austrian, Bangkok Airways, LATAM,
  Lufthansa, SWISS, Shenzhen) earn Asia Miles but **zero** Status Points.
- HK Express earns nothing (redemption partner only).
- The partner SP matrix was extracted from Cathay's own calculator API and verified
  conflict-free across all oneworld partners — see
  [docs/methodology.md](docs/methodology.md).

## Repository layout

```
README.md                     ← you are here
data/
  program.yaml                ← tiers, thresholds, program-level rules
  zones.yaml                  ← CX distance zones (post-2025-08-20)
  partner-earning-model.yaml  ← partner zones + universal SP matrix + airline index
  airlines/
    cathay-pacific.yaml       ← CX-marketed flights earning table
    hk-express.yaml           ← UO (no earning)
    <partner>.yaml            ← one file per partner airline (25 airlines)
docs/
  methodology.md              ← sources, harvest method, verification log
  2027-programme-changes.md   ← announced programme changes (eff. 2027-01-01)
sources/
  *.pdf                       ← archived official PDFs
  api-raw/*.jsonl             ← raw calculator API samples (~1,900 queries)
```

## Status of coverage

**Complete** for all 14 current oneworld partners + 11 non-alliance partners + CX + HK
Express, as of 2026-07-14. See [docs/methodology.md](docs/methodology.md) for the checklist,
verification log, and known gaps (Oman Air SP pending calculator support).

## Disclaimer

This is an unofficial knowledge base compiled from Cathay's published materials for research
purposes. Earning rates change (most recently 20 Aug 2025); always confirm against
[cathaypacific.com](https://www.cathaypacific.com) and its Status Points & Asia Miles calculator
before relying on a number.
