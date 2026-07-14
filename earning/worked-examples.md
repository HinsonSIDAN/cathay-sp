---
title: Worked examples
description: End-to-end Status Points calculations for real itineraries — CX sectors, oneworld partner sectors, non-alliance sectors, and a multi-sector trip.
tags: [guide, earning, status-points]
sensitivity: public
related:
  - airlines/cathay-pacific
  - earning/partner-model
  - programme/status-tiers
last_reviewed: '2026-07-14'
---

Every sector is computed independently by **marketing carrier**; sum sectors for the
itinerary total. Rates as of 2026-07-14.

## 1. CX-marketed flights

Lookup: [[earning/zones]] → [[airlines/cathay-pacific]] (cabin / fare type / fare class).

| Itinerary | Zone | Fare | SP | Asia Miles |
|---|---|---|---|---|
| HKG→LHR (5,994mi) | Long | Business Flex (J) | **130** | 13,000 |
| HKG→NRT (1,841mi, Japan) | Short – Type 2 | Economy Light (M) | **12** | 1,200 |
| HKG→SYD (4,594mi) | Medium | Premium Economy Essential (E) | **45** | 4,500 |
| HKG→TPE (501mi) | Ultra-short | Economy Flex (Y) | **25** | 2,500 |
| HKG→JFK (8,060mi) | Ultra-long | First Flex (F) | **180** | 18,000 |

On CX, Asia Miles = SP × 100 exactly. Short – Type 2 applies only to/from Japan,
Indonesia, Sri Lanka, Nepal, Bangladesh, India.

## 2. oneworld partner flights

Lookup: airline entry (booking class → rate % and SP tier) → [[earning/partner-model]]
(tier × zone matrix; partner zones split Medium at 3,750mi).

| Itinerary | Distance / zone | Class | AM | SP |
|---|---|---|---|---|
| BA LHR→JFK | 3,443mi → Medium-1 | Business C (125%, tier B) | 4,303 | **45** |
| QF SYD→MEL | 438mi → Ultra-short | Economy K (50%, tier H) | 219 | **5** |
| AA DFW→LAX (domestic) | 1,232mi → Short | Business J (150% dom., tier B) | 1,848 | **25** |
| JL HND→CTS (domestic) | 509mi → Ultra-short | Class J = E (125%, tier B) | 639 | **15** |
| QR DOH→SYD | 7,834mi → Ultra-long | Economy Y (100%, tier F) | 7,834 | **40** |
| AY HEL→JFK | 4,106mi → Medium-2 | Business I (100%, tier C) | 4,105 | **50** |

## 3. Non-oneworld partners (Asia Miles only)

| Itinerary | Class | AM | SP |
|---|---|---|---|
| LH FRA→HKG | Business J (125%) | ~7,100 | **0** |
| AC YVR→YYZ | Economy Y (100%) | ~2,085 | **0** |

## 4. Multi-sector itinerary

HKG→LHR on CX Business Flex (J), then LHR→JFK on BA Business (C):

- Sector 1: CX, Long zone, J Flex → 130 SP
- Sector 2: BA, Medium-1, tier B → 45 SP
- **Total: 175 SP** (+ 13,000 + 4,303 Asia Miles)

At 300 SP the member reaches Silver — see [[programme/status-tiers]].

## Practical notes

- Distances are ticketed-point mileage (≈ great-circle); values within a few miles of a
  zone boundary should be checked in the official calculator.
- Codeshares credit by the **marketing** carrier's table, subject to each airline's
  eligibility notes (per airline entry).
- Award tickets, most industry/agency discounts, and unused/refunded tickets earn nothing.
