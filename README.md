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

There is **no single formula** — SP earnings are looked up from published tables, keyed by:

```
SP = table[ airline ][ distance zone or route ][ cabin ][ fare class / fare type ]
```

- **Airline** — Cathay Pacific-marketed flights use one table; HK Express and each partner
  airline have their own tables.
- **Distance zone** — based on miles flown between origin and destination (see
  [data/zones.yaml](data/zones.yaml)).
- **Cabin & fare class / fare type** — the booking class letter (e.g. Y, B, H, K) and, on
  Cathay Pacific, the fare type (Flex / Essential / Light).
- On Cathay Pacific-marketed flights, **Asia Miles = Status Points × 100** in every published
  cell of the current table.

## Repository layout

```
README.md                     ← you are here
data/
  program.yaml                ← tiers, thresholds, program-level rules
  zones.yaml                  ← distance zone definitions
  airlines/
    cathay-pacific.yaml       ← CX-marketed flights earning table
    hk-express.yaml           ← UO earning table
    <partner>.yaml            ← one file per partner airline
docs/
  methodology.md              ← sources, retrieval dates, verification notes
  2027-programme-changes.md   ← announced programme changes
sources/                      ← archived source documents (PDFs)
```

## Status of coverage

See [docs/methodology.md](docs/methodology.md) for the live coverage checklist.

## Disclaimer

This is an unofficial knowledge base compiled from Cathay's published materials for research
purposes. Earning rates change (most recently 20 Aug 2025); always confirm against
[cathaypacific.com](https://www.cathaypacific.com) and its Status Points & Asia Miles calculator
before relying on a number.
