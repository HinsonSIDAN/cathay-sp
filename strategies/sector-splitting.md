---
title: Sector splitting (分段賺分)
description: Status Points grow sub-linearly with distance, so routing via a hub earns more than flying nonstop — the zone-table math with verified examples.
tags: [strategy, status-points, earning]
sensitivity: public
related:
  - airlines/cathay-pacific
  - earning/partner-model
  - earning/zones
last_reviewed: '2026-07-14'
---

SP is a **per-sector zone lookup**, and the zone table is heavily sub-linear in distance:
on CX Business Light, an Ultra-short sector (≤750mi) pays 25 SP while an Ultra-long
(7,501mi+, ten times the distance) pays only 120 SP. Consequence: **any connection you
add earns extra points** — the shorter sectors punch far above their distance.

## CX Business Light per-sector values (from [[airlines/cathay-pacific]])

| Zone | SP | SP per 1,000mi (approx) |
|---|---|---|
| Ultra-short (≤750) | 25 | 33–100+ |
| Short T1 (751–2,750) | 35 | 13–47 |
| Short T2 (Japan/India etc.) | 45 | 16–60 |
| Medium (2,751–5,000) | 75 | 15–27 |
| Long (5,001–7,500) | 100 | 13–20 |
| Ultra-long (7,501+) | 120 | ≤16 |

## Verified splitting examples (all live CX-marketed sectors, Business Light)

| Journey | Nonstop SP | Split routing | Split SP | Gain |
|---|---|---|---|---|
| Hong Kong → Melbourne | 75 ([[routes/hkg-mel]]) | HKG-SYD + SYD-MEL | 75+25 = **100** | +33% |
| Hong Kong → Sapporo | 45 ([[routes/hkg-cts]]) | HKG-HND + HND-CTS | 45+25 = **70** | +56% |
| Taipei → San Francisco | — (no nonstop) | TPE-HKG + HKG-SFO | 25+100 = **125** | vs 100 for HKG-SFO alone |
| Beijing → San Francisco | — (no nonstop) | PEK-HKG + HKG-SFO | 35+100 = **135** | vs 100 for HKG-SFO alone |

The same holds on partner metal via the partner matrix ([[earning/partner-model]]):
tier-B business pays 15 SP for an ultra-short hop vs 85 for ultra-long — a
QR HKG⇄Europe via DOH earns (60+45)×2 = 210 SP where a hypothetical nonstop would earn
75×2 = 150 (see [[strategies/qr-doha-runs]]).

## How to use it

1. Prefer connecting itineraries over nonstops when the fare difference is small —
   the connection is *paid for* in SP.
2. Stack it with [[strategies/ex-origin-fares]]: the cheap ex-origin ticket **is** a
   split itinerary, so you collect both effects at once.
3. Ultra-short feeders (TPE, MNL, regional Japan) have the best SP-per-mile in the
   system; Short-T2 feeders (Japan, India) have the best SP-per-mile-per-dollar on CX.

## Caveats

- Both sectors must be on eligible fare classes; through-fares usually book both sectors
  in the same class.
- Split itineraries take longer and add misconnection risk.
- Some through-fares price *higher* than nonstops — the trick only wins when paired
  with ex-origin pricing or genuine connectivity needs.
