# Methodology & coverage

## How this knowledge base is compiled

1. **Primary sources**:
   - cathaypacific.com pages (membership / status points / partner airline pages) and
     official Cathay PDFs (archived under `sources/`).
   - **Cathay's Status Points & Asia Miles calculator API**
     (`api.cathaypacific.com/mpo-miles-services/v3/miles-calculator/calculates`) — the same
     backend the official calculator UI uses. It returns, per airline + origin +
     destination + cabin: every booking class with its Asia Miles (`basicMiles`) and
     Status Points (`basicClubPoints`) plus a `bookingClassGroup` tier letter.
2. **Harvest**: the API was probed across ~25 airlines × 10–17 routes (a distance ladder
   from ~180mi to ~9,000mi, plus domestic probes where rates differ) × 4 cabins.
   Raw responses are archived in `sources/api-raw/*.jsonl` (~1,900 queries, 2026-07-14).
3. **Distillation**: per-airline booking-class maps and a universal partner SP matrix were
   derived from the samples. The matrix (tier × zone → SP) was validated across all
   oneworld airlines with **zero conflicts**; zone boundaries were bracketed empirically
   (e.g. 3,676mi→medium_1 vs 3,751mi→medium_2).
4. **Cross-check**: each partner page's published Asia Miles table was scraped and stored in
   the airline file (`published_page_table`); discrepancies vs the API are flagged
   explicitly (`discrepancies:` keys).

## Data conventions

- One YAML file per airline under `data/airlines/`.
- Status Points and Asia Miles are per **one-way sector**, keyed by the **marketing carrier**.
- CX-marketed flights: zone scheme in `data/zones.yaml` (post-2025-08-20 zones).
- Partner-marketed flights: zone scheme + SP matrix in `data/partner-earning-model.yaml`
  (pre-2025-08-20 zones — the Aug 2025 change did not touch partner earning).

## Coverage checklist

### Programme core
- [x] Status tiers & thresholds (Green/Silver/Gold/Diamond) — current programme
- [x] 2027 enhanced programme (Diamond Exec 2,400 SP, rollover, no-reset, reserve) — announced
- [x] Distance zone definitions (CX post-2025-08-20 + partner legacy zones)
- [x] Cathay Pacific (CX) marketed flights — full table effective 2025-08-20 (verified vs official PDF, 5 languages)
- [x] Universal partner SP matrix (tier × zone) — verified across all oneworld partners, zero conflicts

### Cathay group
- [x] HK Express (UO) — no SP/AM earning (redemption only)

### oneworld partners (all 14 current members besides CX)
- [x] Alaska Airlines (AS)
- [x] American Airlines (AA) — incl. domestic vs international business rates
- [x] British Airways (BA)
- [x] Fiji Airways (FJ)
- [x] Finnair (AY)
- [x] Iberia (IB)
- [x] Japan Airlines (JL) — incl. Japan-domestic classes
- [x] Malaysia Airlines (MH)
- [x] Oman Air (WY) — page rates only; SP tiers inferred (calculator does not support WY yet)
- [x] Qantas (QF) — page/API discrepancy flagged (discount economy 25% vs 50%)
- [x] Qatar Airways (QR)
- [x] Royal Air Maroc (AT)
- [x] Royal Jordanian (RJ)
- [x] SriLankan Airlines (UL)
- [x] S7 Airlines (S7) — suspended, no earning

### Other partner airlines (Asia Miles only — 0 Status Points)
- [x] Air Canada (AC)
- [x] Air China (CA)
- [x] Air New Zealand (NZ) — page rates only; calculator returns no data
- [x] Austrian Airlines (OS)
- [x] Bangkok Airways (PG)
- [x] LATAM Airlines (LA)
- [x] Lufthansa (LH)
- [x] SWISS (LX)
- [x] Shenzhen Airlines (ZH)
- [x] Gulf Air (GF) — partnership ended
- [x] Emirates/Hawaiian etc. — probed (EK, HA): not partners, no data

## Known gaps / watch items

- Partner SP matrix tier C × ultra_long is unobservable (no eligible route that long).
- WY (Oman Air) SP earning unverified pending calculator support.
- The 2027 programme relaunch may change earning tables; re-verify after Cathay
  publishes 2027 earning details (watch docs/2027-programme-changes.md open questions).
- Classes a partner publishes but the calculator doesn't offer on probed routes (e.g. JL
  X/D/I international business) carry page rates only.

## Verification log

| Date | What | Result |
|------|------|--------|
| 2026-07-14 | CX table: news-page HTML vs official full-table PDF (EN/TC/SC/JA/KO) | Match, all cells |
| 2026-07-14 | Partner SP matrix: tier×zone consistency across 13 oneworld airlines, ~1,900 API samples | Zero conflicts |
| 2026-07-14 | Partner AM rates: API-observed vs published page tables, all airlines | Match, except QF discount economy (flagged) and JL R (flagged) |
| 2026-07-14 | Zone boundaries (750 / 2,750 / 3,750 / 5,000 / 7,500) via bracketing probes | Confirmed |
