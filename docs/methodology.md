# Methodology & coverage

## How this knowledge base is compiled

1. **Primary source first**: cathaypacific.com pages (membership / status points / partner
   airline earning pages) and official Cathay PDFs. Pages are fetched and the earning tables
   extracted from the page markup; PDFs are archived under `sources/`.
2. **Cross-checks**: official FAQ pages, the Cathay Status Points & Asia Miles calculator, and
   reputable secondary sources (frequent-flyer press) only to corroborate, never as the
   primary number.
3. Every data file records its source URLs and retrieval date in the header comment.

## Data conventions

- One YAML file per airline under `data/airlines/`.
- Status Points are per **one-way sector**, for the **marketing carrier** shown.
- CX distance zones are defined in `data/zones.yaml`; partner airlines may use different
  zone/route schemes, recorded per file.

## Coverage checklist

### Programme core
- [x] Status tiers & thresholds (Green/Silver/Gold/Diamond)
- [x] Distance zone definitions (effective 2025-08-20)
- [x] Cathay Pacific (CX) marketed flights — full table effective 2025-08-20
- [ ] 2027 enhanced programme changes (announced; effective 2027-01-01)

### Cathay group
- [ ] HK Express (UO)

### oneworld partners
- [ ] Alaska Airlines (AS)
- [ ] American Airlines (AA)
- [ ] British Airways (BA)
- [ ] Fiji Airways (FJ)
- [ ] Finnair (AY)
- [ ] Iberia (IB)
- [ ] Japan Airlines (JL)
- [ ] Malaysia Airlines (MH)
- [ ] Oman Air (WY)
- [ ] Qantas (QF)
- [ ] Qatar Airways (QR)
- [ ] Royal Air Maroc (AT)
- [ ] Royal Jordanian (RJ)
- [ ] SriLankan Airlines (UL)

### Other partner airlines (non-oneworld)
- [ ] To be enumerated from Cathay's partner airlines page

## Verification log

| Date | What | Result |
|------|------|--------|
| 2026-07-14 | CX table extracted from news page HTML vs official full-table PDF (5 languages) | Match, all cells |
