---
title: Methodology and verification
description: How this KB was compiled — Cathay calculator API harvest, partner page scrapes, cross-checks, verification log, and known gaps.
tags: [meta, methodology]
sensitivity: internal
last_reviewed: '2026-07-14'
---

## Sources, in order of authority

1. **Cathay's Status Points & Asia Miles calculator API**
   (`api.cathaypacific.com/mpo-miles-services/v3/miles-calculator/calculates`) — the same
   backend the official calculator UI uses. POST with
   `{airlineDesignator, origin, destination, cabinClass}`; returns every booking class with
   `basicMiles` (Asia Miles), `basicClubPoints` (Status Points) and a `bookingClassGroup`
   tier letter. Discovered via the calculator page's AEM page model
   (`miles-and-points-calculator.model.json` → `configs.apis`).
2. cathaypacific.com pages: membership/status-points pages, partner pages
   (`our-partners/<airline>.html` — earn tables embedded as `propositionList` JSON),
   FAQ pages, and the official full-table PDF (archived at
   `sources/cx-status-points-asia-miles-full-table-2025-08-20.pdf`).

## Harvest method

- ~1,900 API queries across 29 airline codes × a distance-ladder of routes (~180mi to
  ~9,000mi, plus domestic probes where rates differ) × 4 cabins. Raw responses:
  `sources/api-raw/*.jsonl`.
- The universal SP matrix (tier × zone) in [[earning/partner-model]] was derived from
  these samples and validated across all oneworld airlines with **zero conflicts**.
- Zone boundaries bracketed empirically (e.g. 3,676mi → Medium-1 vs 3,751mi → Medium-2).
- Every partner page's published table was scraped and diffed against API-observed rates;
  discrepancies are flagged in the airline entries.

## Verification log

| Date | What | Result |
|---|---|---|
| 2026-07-14 | CX table, news-page HTML vs official PDF (5 languages) | Match, all cells |
| 2026-07-14 | Partner SP matrix consistency, 13 oneworld airlines, ~1,900 samples | Zero conflicts |
| 2026-07-14 | API rates vs published page tables, all airlines | Match, except QF discount economy and JL R (flagged in entries) |
| 2026-07-14 | Zone boundaries 750/2,750/3,750/5,000/7,500 | Confirmed |
| 2026-07-14 | NZ re-probed on HKG–AKL (earlier probe was invalid) | Priced: AM per published rates, 0 SP |
| 2026-07-14 | CX route discovery: HKG × all 383 calculator airports | API validates routes — only real CX sectors price |

## Route validation semantics

The calculator **validates routes per airline**: it only prices sectors the airline
actually *markets* (own flights + codeshares under its code). Tested with absurd pairs
(TPE–JNB, CPH–PER): every airline returns nothing — except **Japan Airlines, which prices
any city pair** (no validation; useful as a universal distance odometer, since JL Y = 100%
of ticketed miles). Consequences:

- A sector priced by the API is genuinely creditable for that marketing carrier.
- "All routes" per airline = its marketed-sector set, enumerable by probing its hubs
  against the airport list (the hub census below).
- CX prices codeshare feeder sectors beyond HKG (e.g. LHR–ABZ, SYD–MEL, PEK–PVG under CX
  codes) — these earn from the CX table like any CX-marketed sector.

## Route-level entries

The `routes/` entries were generated from dedicated harvests (2026-07-14):

- **CX from HKG**: HKG probed against all 383 calculator airports — 167 live CX-marketed
  sectors (including codeshare and intermodal points). Full 4-cabin detail per sector; a
  parallel BA probe supplies exact ticketed mileage (BA Y = 100% of miles flown) and the
  partner zone. Raw data: `sources/routes-raw/*.jsonl`.
- **CX codeshare feeders**: CX probed from 18 gateway hubs (LHR, CDG, FRA, ZRH, PEK, PVG,
  TPE, NRT, HND, KIX, SYD, MEL, AKL, YVR, LAX, JFK, BKK, SIN) × 383 airports — 266
  additional live CX-marketed sectors, all detailed across 4 cabins. Distances via a JL
  Y-cabin probe (JL prices any pair; Y = 100% of miles).
- 21 oneworld trunk sectors (LHR–JFK, SYD–MEL, DOH–LHR, …) from the airline-harvest samples.
- Route entries are per one-way sector; values are direction-symmetric.

## Partner sector registries (hub census)

Each SP-earning oneworld partner has an `airlines/<slug>-routes.md` registry: its live
marketed sectors found by probing the hubs below against all 383 calculator airports
(Y cabin; distance/zone from the response; other cabins resolved via the verified SP
matrix). Raw data: `sources/census-raw/*.jsonl` (~13,000 probes, 2026-07-14).

| Airline | Hubs probed | Live sectors |
|---|---|---|
| AA | DFW, ORD, LAX, JFK, MIA | 424 |
| BA | LHR, LGW | 332 |
| IB | MAD, BCN | 174 |
| QF | SYD, MEL, BNE, PER | 160 |
| QR | DOH | 155 |
| AS | SEA, PDX, LAX, ANC | 96 |
| AY | HEL | 83 |
| MH | KUL | 69 |
| AT | CMN | 54 |
| RJ | AMM | 51 |
| UL | CMB | 38 |
| FJ | NAN, SUV | 21 |

Scope caveat: sectors not touching the probed hubs (e.g. AA point-to-point flights
avoiding all five hubs, BA regional-to-regional) are not enumerated; they follow the same
verified model and can be priced via the airline entry + `earning/partner-model`. JL has
no registry because the calculator prices any JL city pair (no route validation).

## Known gaps / watch items

- Partner SP matrix tier C × Ultra-long unobservable (no such route exists).
- Oman Air (WY) SP earning unverified pending calculator support.
- The 2027 programme relaunch may change earning tables — see the open questions in
  [[programme/changes-2027]].
- Classes published on a partner page but never offered by the calculator on probed routes
  carry page rates only (noted per entry).

## Repo layout (machine layer)

The markdown entries in this repo are the KB; the machine-readable layer that generated
them is kept alongside:

- `data/*.yaml` — structured earning data (program, zones, partner model, per airline)
- `sources/` — archived official PDF + raw API samples

When updating: change `data/` first, regenerate/hand-sync the markdown entries, and record
the check here.
