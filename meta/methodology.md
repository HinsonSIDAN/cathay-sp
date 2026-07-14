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
