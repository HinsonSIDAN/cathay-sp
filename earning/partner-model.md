---
title: Partner flight earning model (SP matrix)
description: How partner-marketed flights earn — Asia Miles as rate % × miles flown, Status Points from the universal tier × zone matrix (oneworld only, others earn 0 SP).
tags: [spec, earning, status-points, oneworld]
sensitivity: public
related:
  - earning/zones
  - airlines
  - meta/methodology
last_reviewed: '2026-07-14'
---

> **Source:** Cathay's official Status Points & Asia Miles calculator (API-observed across
> ~1,900 queries, 2026-07-14; raw samples in `sources/api-raw/`), cross-checked against
> every partner page on cathaypacific.com. Method and verification log: methodology entry
> under meta (linked in frontmatter).

Flights **marketed by a partner airline** (not CX — for CX-marketed flights see
[[airlines/cathay-pacific]]) earn like this:

```
Asia Miles    = rate% × actual miles flown            (per one-way sector)
Status Points = sp_matrix[tier][zone]                 (oneworld airlines only)
```

- `rate%` and `tier` depend on the airline + booking class — see each airline entry
  under [[airlines]].
- **Only oneworld members earn Status Points.** Non-alliance partners (Air Canada,
  Air China, Air New Zealand, Austrian, Bangkok Airways, LATAM, Lufthansa, SWISS,
  Shenzhen Airlines) earn Asia Miles and **0 SP**.
- Partner flights use the **legacy zone scheme** (the Aug 2025 zone change applied to
  CX-marketed flights only) — boundaries below.

## Partner distance zones

| Zone | Miles flown |
|---|---|
| Ultra-short | 1 – 750 |
| Short | 751 – 2,750 |
| Medium-1 | 2,751 – 3,750 |
| Medium-2 | 3,751 – 5,000 |
| Long | 5,001 – 7,500 |
| Ultra-long | 7,501+ |

## Universal SP matrix (tier × zone)

Verified conflict-free across all oneworld partners. Tier letters are the calculator's
`bookingClassGroup` values; each airline maps its booking classes onto them.

| Tier | Typical classes | Ultra-short | Short | Medium-1 | Medium-2 | Long | Ultra-long |
|---|---|---|---|---|---|---|---|
| A | First (150%) | 15 | 25 | 50 | 70 | 90 | 100 |
| B | Business (125–150%) | 15 | 25 | 45 | 60 | 75 | 85 |
| C | Business-lite (100–125%) | 10 | 20 | 35 | 50 | 65 | n/a* |
| D | Premium Economy (110%) | 10 | 15 | 25 | 30 | 40 | 45 |
| E | PE-standard (100%) | 5 | 10 | 20 | 25 | 35 | 40 |
| F | Economy-full (100%) | 5 | 10 | 20 | 25 | 35 | 40 |
| G | Economy-mid (50–75%) | 5 | 10 | 15 | 20 | 25 | 30 |
| H | Economy-discount (25–50%) | 5 | 10 | 15 | 15 | 20 | 25 |
| J | Deep-discount (25%) | 5 | 5 | 5 | 10 | 10 | 10 |

\* No oneworld partner sells an eligible C-tier class on a >7,500-mile sector, so this
cell is unobservable.

Notes:

- Tiers E and F pay identical SP; the calculator distinguishes the letters (PE vs economy).
- The tier is assigned **per booking class by each airline, not purely by the miles rate** —
  e.g. Finnair I/R earn 100% miles but sit in business tier C, while Finnair W/E/T/P
  (also 100%) sit in tier E.
- Small AM-rate anomalies on very short sectors (e.g. DOH–DXB pricing at ~102%) are
  ticketed-point-mileage vs great-circle differences, not different rates.

## Who earns what

| Group | Airlines |
|---|---|
| SP + AM (oneworld) | [AA](../airlines/american-airlines.md), [AS](../airlines/alaska-airlines.md), [BA](../airlines/british-airways.md), [AY](../airlines/finnair.md), [FJ](../airlines/fiji-airways.md), [IB](../airlines/iberia.md), [JL](../airlines/japan-airlines.md), [MH](../airlines/malaysia-airlines.md), [QF](../airlines/qantas.md), [QR](../airlines/qatar-airways.md), [AT](../airlines/royal-air-maroc.md), [RJ](../airlines/royal-jordanian.md), [UL](../airlines/srilankan-airlines.md), [WY](../airlines/oman-air.md) (inferred) |
| AM only, 0 SP | [AC](../airlines/air-canada.md), [CA](../airlines/air-china.md), [NZ](../airlines/air-new-zealand.md), [OS](../airlines/austrian-airlines.md), [PG](../airlines/bangkok-airways.md), [LA](../airlines/latam-airlines.md), [LH](../airlines/lufthansa.md), [LX](../airlines/swiss.md), [ZH](../airlines/shenzhen-airlines.md) |
| No earning | [UO](../airlines/hk-express.md), [GF](../airlines/gulf-air.md), [S7](../airlines/s7-airlines.md) |

Machine-readable source: `data/partner-earning-model.yaml` in this repo.
