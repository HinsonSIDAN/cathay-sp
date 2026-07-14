---
title: American Airlines (AA)
description: American Airlines (AA) earning when crediting to Cathay — Asia Miles rate and Status Points per booking class and distance zone (oneworld member).
tags: [reference, airline, earning, oneworld]
sensitivity: public
related:
  - earning/partner-model
iata: AA
alliance: oneworld
earns_status_points: true
last_reviewed: '2026-07-14'
source_url: https://www.cathaypacific.com/cx/en_HK/our-partners/american-airlines.html
---

> **Source:** [American Airlines partner page (cathaypacific.com)](https://www.cathaypacific.com/cx/en_HK/our-partners/american-airlines.html) and the official Cathay Status Points & Asia Miles calculator (API-observed, 2026-07-14).

American Airlines is a oneworld member: flights marketed by AA earn **Asia Miles** (rate % × actual miles flown) **and Status Points** (zone lookup by SP tier) when credited to Cathay. Zones and the SP tier matrix are defined in [[earning/partner-model]].

## Earning by booking class

| Cabin | Fare classes | Scope | Asia Miles | SP tier | SP Ultra-short | SP Short | SP Medium-1 | SP Medium-2 | SP Long | SP Ultra-long |
|---|---|---|---|---|---|---|---|---|---|---|
| First | A, F | all | 150% | A | 15 | 25 | 50 | 70 | 90 | 100 |
| Business | C, D, I, J, R | domestic | 150% | B | 15 | 25 | 45 | 60 | 75 | 85 |
| Business | C, D, I, J, R | international | 125% | B | 15 | 25 | 45 | 60 | 75 | 85 |
| Premium Economy | W | all | 110% | D | 10 | 15 | 25 | 30 | 40 | 45 |
| Premium Economy | P | all | 100% | E | 5 | 10 | 20 | 25 | 35 | 40 |
| Economy | Y | all | 100% | F | 5 | 10 | 20 | 25 | 35 | 40 |
| Economy | H, K, L, M, V | all | 75% | G | 5 | 10 | 15 | 20 | 25 | 30 |
| Economy | G, N, Q, S | all | 25% | J | 5 | 5 | 5 | 10 | 10 | 10 |

## Eligibility

Asia Miles can be earned on eligible fares classes of: - Flights marketed and operated by American Airlines; - Flights marketed by American Airlines and operated by one world® carriers; - Flights marketed by American Airlines and operated by its affiliates (American Eagle); - Codeshare flights operated by Alaska Airlines.

---

Machine-readable source of this entry: `data/airlines/american-airlines.yaml` in this repo (raw calculator API samples under `sources/api-raw/`).
