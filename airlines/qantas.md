---
title: Qantas (QF)
description: Qantas (QF) earning when crediting to Cathay — Asia Miles rate and Status Points per booking class and distance zone (oneworld member).
tags: [reference, airline, earning, oneworld]
sensitivity: public
related:
  - earning/partner-model
iata: QF
alliance: oneworld
earns_status_points: true
last_reviewed: '2026-07-14'
source_url: https://www.cathaypacific.com/cx/en_HK/our-partners/qantas.html
---

> **Source:** [Qantas partner page (cathaypacific.com)](https://www.cathaypacific.com/cx/en_HK/our-partners/qantas.html) and the official Cathay Status Points & Asia Miles calculator (API-observed, 2026-07-14).

Qantas is a oneworld member: flights marketed by QF earn **Asia Miles** (rate % × actual miles flown) **and Status Points** (zone lookup by SP tier) when credited to Cathay. Zones and the SP tier matrix are defined in [[earning/partner-model]].

## Earning by booking class

| Cabin | Fare classes | Scope | Asia Miles | SP tier | SP Ultra-short | SP Short | SP Medium-1 | SP Medium-2 | SP Long | SP Ultra-long |
|---|---|---|---|---|---|---|---|---|---|---|
| First | A, F | all | 150% | A | 15 | 25 | 50 | 70 | 90 | 100 |
| Business | C, D, I, J | all | 125% | B | 15 | 25 | 45 | 60 | 75 | 85 |
| Premium Economy | R, T, W | all | 110% | D | 10 | 15 | 25 | 30 | 40 | 45 |
| Economy | Y | all | 100% | F | 5 | 10 | 20 | 25 | 35 | 40 |
| Economy | B, H, K, L, M, V | all | 50% | H | 5 | 10 | 15 | 15 | 20 | 25 |

## Eligibility

Asia Miles can be earned only in eligible fare classes on: - Flights marketed and operated Qantas , codeshare flights marketed by Qantas and operated by QantasLink, Sunstate Airlines, Eastern Australia Airlines or any one world® member airline

## Known discrepancies

- The partner page lists discounted economy B, H, K, L, M, V at 25% of miles flown, but the calculator prices these classes at 50% (SP tier H) on all probed routes as of 2026-07-14. The calculator (operational data) is taken as primary here; the page table appears stale.

---

Machine-readable source of this entry: `data/airlines/qantas.yaml` in this repo (raw calculator API samples under `sources/api-raw/`).
