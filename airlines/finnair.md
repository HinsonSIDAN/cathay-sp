---
title: Finnair (AY)
description: Finnair (AY) earning when crediting to Cathay — Asia Miles rate and Status Points per booking class and distance zone (oneworld member).
tags: [reference, airline, earning, oneworld]
sensitivity: public
related:
  - earning/partner-model
iata: AY
alliance: oneworld
earns_status_points: true
last_reviewed: '2026-07-14'
source_url: https://www.cathaypacific.com/cx/en_HK/our-partners/finnair.html
---

> **Source:** [Finnair partner page (cathaypacific.com)](https://www.cathaypacific.com/cx/en_HK/our-partners/finnair.html) and the official Cathay Status Points & Asia Miles calculator (API-observed, 2026-07-14).

Finnair is a oneworld member: flights marketed by AY earn **Asia Miles** (rate % × actual miles flown) **and Status Points** (zone lookup by SP tier) when credited to Cathay. Zones and the SP tier matrix are defined in [[earning/partner-model]].

## Earning by booking class

| Cabin | Fare classes | Scope | Asia Miles | SP tier | SP Ultra-short | SP Short | SP Medium-1 | SP Medium-2 | SP Long | SP Ultra-long |
|---|---|---|---|---|---|---|---|---|---|---|
| Business | C, D, J | all | 125% | B | 15 | 25 | 45 | 60 | 75 | 85 |
| Business | I, R | all | 100% | C | 10 | 20 | 35 | 50 | 65 | n/a |
| Premium Economy | E, P, T, W | all | 100% | E | 5 | 10 | 20 | 25 | 35 | 40 |
| Economy | B, H, K, M, Y | all | 100% | F | 5 | 10 | 20 | 25 | 35 | 40 |
| Economy | L, V | all | 50% | H | 5 | 10 | 15 | 15 | 20 | 25 |

## Eligibility

Asia Miles accrual does not apply to: - Flights operated by Flybe, except flight ranges from AY2100 – AY2999; - Flights marketed by Finnair, operated by another airline except one world® airlines.

---

Machine-readable source of this entry: `data/airlines/finnair.yaml` in this repo (raw calculator API samples under `sources/api-raw/`).
