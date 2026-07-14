---
title: Japan Airlines (JL)
description: Japan Airlines (JL) earning when crediting to Cathay — Asia Miles rate and Status Points per booking class and distance zone (oneworld member).
tags: [reference, airline, earning, oneworld]
sensitivity: public
related:
  - earning/partner-model
iata: JL
alliance: oneworld
earns_status_points: true
last_reviewed: '2026-07-14'
source_url: https://www.cathaypacific.com/cx/en_HK/our-partners/japan-airlines.html
---

> **Source:** [Japan Airlines partner page (cathaypacific.com)](https://www.cathaypacific.com/cx/en_HK/our-partners/japan-airlines.html) and the official Cathay Status Points & Asia Miles calculator (API-observed, 2026-07-14).

Japan Airlines is a oneworld member: flights marketed by JL earn **Asia Miles** (rate % × actual miles flown) **and Status Points** (zone lookup by SP tier) when credited to Cathay. Zones and the SP tier matrix are defined in [[earning/partner-model]].

## Earning by booking class

| Cabin | Fare classes | Scope | Asia Miles | SP tier | SP Ultra-short | SP Short | SP Medium-1 | SP Medium-2 | SP Long | SP Ultra-long |
|---|---|---|---|---|---|---|---|---|---|---|
| First | F, A | international | 150% | A | 15 | 25 | 50 | 70 | 90 | 100 |
| Business | C | international | 125% | B | 15 | 25 | 45 | 60 | 75 | 85 |
| Business | H | international | 70% | G | 5 | 10 | 15 | 20 | 25 | 30 |
| Premium Economy | W | international | 100% | F | 5 | 10 | 20 | 25 | 35 | 40 |
| Premium Economy | P, R | international | 50% | H | 5 | 10 | 15 | 15 | 20 | 25 |
| Economy | Y | international | 100% | F | 5 | 10 | 20 | 25 | 35 | 40 |
| First | F | domestic | 150% | A | 15 | 25 | n/a | n/a | n/a | n/a |
| Business | E | domestic | 125% | B | 15 | 25 | n/a | n/a | n/a | n/a |
| Economy | J, Y | domestic | 100% | F | 5 | 10 | n/a | n/a | n/a | n/a |
| Economy | A, I | domestic | 50% | H | 5 | 10 | n/a | n/a | n/a | n/a |

## Eligibility

Asia Miles can be earned in eligible fare classes on flights marketed and operated by Japan Airlines / Japan Transocean Air / J-AIR, and on codeshare flights operated by all oneworld carriers. Also earnable (and redeemable) on flights marketed by Japan Airlines and operated by Japan Air Commuter or Hokkaido Air System.

## Known discrepancies

- Partner page lists international Premium Economy R at 100%; the calculator prices R at 50% (tier H). Page also lists business classes J, D, I (125%) and X (70%), and economy B, H, K, M, L, V, S (50%) which the calculator does not offer for the probed routes — page values likely still apply when those classes are ticketed; SP tier can be inferred from the matching rate tier.

---

Machine-readable source of this entry: `data/airlines/japan-airlines.yaml` in this repo (raw calculator API samples under `sources/api-raw/`).
