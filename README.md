# cathay-sp — Cathay Status Points knowledge base

A [sidanclaw](https://sidan.ai) team knowledge base on **Cathay (Cathay Pacific) Status
Points calculation**: per-airline, per-fare-class earning tables for Cathay Pacific, HK
Express, all 14 oneworld partners and every other Cathay airline partner, plus membership
programme rules (current + 2027 changes).

## Layout

```
index.md            ← KB root entry (start here)
programme/          ← status tiers, qualification, 2027 programme changes
earning/            ← earning mechanics: CX model, partner SP matrix, zones, examples
airlines/           ← one entry per airline (27 airlines)
meta/               ← sensitivity policy, tag glossary, methodology & verification log
data/               ← machine-readable layer (YAML) that generated the entries
sources/            ← archived official PDF + raw calculator API samples (JSONL)
```

The markdown entries follow the sidanclaw KB parser contract (YAML frontmatter with
`title` / `description` / `tags` / `sensitivity`, `index.md` per directory, wikilink
cross-references). Connect this repo in sidanclaw team settings → Knowledge, and the sync
worker mirrors the entries into the searchable KB.

## Updating

1. Re-verify against cathaypacific.com / the Status Points & Asia Miles calculator
   (method in `meta/methodology.md`).
2. Update `data/*.yaml` first, then regenerate or hand-sync the markdown entries.
3. Record the check in the verification log in `meta/methodology.md`.

Data current as of **2026-07-14**. Unofficial; always confirm against cathaypacific.com
before relying on a number.
