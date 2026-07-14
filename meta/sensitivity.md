---
title: Sensitivity policy
description: Tier policy for this KB — airline and programme facts compiled from public Cathay pages are public; methodology and KB-internal notes are internal.
tags: [meta, policy]
sensitivity: internal
---

This KB compiles publicly published airline-programme facts, so most entries are `public`.

## Policy by folder

| Folder | Default tier | Rationale |
|---|---|---|
| `programme/`, `earning/`, `airlines/` | `public` | Compiled from public cathaypacific.com pages; shippable externally |
| `meta/` | `internal` | Methodology (API harvesting details), KB conventions |

`confidential` is currently unused. Use it if entries ever capture personal account data
(SP balances, membership numbers, travel history) — those identify a real individual.

Default when frontmatter omits `sensitivity` is `internal`; always set it explicitly.
