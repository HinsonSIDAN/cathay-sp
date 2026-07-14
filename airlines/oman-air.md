---
title: Oman Air (WY)
description: Oman Air (WY) earning when crediting to Cathay — Asia Miles rate and Status Points per booking class and distance zone (oneworld member).
tags: [reference, airline, earning, oneworld]
sensitivity: public
related:
  - earning/partner-model
iata: WY
alliance: oneworld
earns_status_points: true
last_reviewed: '2026-07-14'
source_url: https://www.cathaypacific.com/cx/en_HK/our-partners/oman-air.html
---

> **Source:** [Oman Air partner page (cathaypacific.com)](https://www.cathaypacific.com/cx/en_HK/our-partners/oman-air.html) and the official Cathay Status Points & Asia Miles calculator (API-observed, 2026-07-14).

Oman Air is a oneworld member: flights marketed by WY earn **Asia Miles** (rate % × actual miles flown) **and Status Points** (zone lookup by SP tier) when credited to Cathay. Zones and the SP tier matrix are defined in [[earning/partner-model]].

## Published earning table (partner page)

| Cabin | Fare classes | Asia Miles |
|---|---|---|
| Business Studio | F, A | 150% of actual miles flown |
| Business Class | J, C, D, I, P | 125% of actual miles flown |
| Economy Class | Y | 100% of actual miles flown |
| Economy Class | B | 50% of actual miles flown |
| Economy Class | H, K, M, L, V, S, N, Q, O, R, T | 25% of actual miles flown |

## Data caveats

Oman Air joined oneworld on 30 June 2024 and has a live Cathay partner earn page, but as of 2026-07-14 the Cathay Status Points & Asia Miles calculator does not return data for WY (not in its supported airline list). The Asia Miles rates below are as published. Status Points tiers are INFERRED from the standard oneworld partner matrix by matching cabin/rate (unverified against the calculator): F, A -> tier A; J, C, D, I, P -> tier B; Y -> tier F; B -> tier H; H, K, M, L, V, S, N, Q, O, R, T -> tier J. Verify against the calculator or booking flow before relying on WY SP numbers.

---

Machine-readable source of this entry: `data/airlines/oman-air.yaml` in this repo (raw calculator API samples under `sources/api-raw/`).
