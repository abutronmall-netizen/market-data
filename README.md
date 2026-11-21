# ABUTRON FX market data

Public market-only historical datasets, separated by broker:

- `Deriv/` — Deriv synthetic-index candle history.
- `FP-Markets/` — FP Markets market candle and quote history.

Source timestamps are UTC. No broker account identifiers, trade ledgers, balances, credentials, or execution permissions belong in this repository.

Exports are snapshots, not a claim of continuously synchronized live feeds. Dataset manifests provide source counts, timestamps, and SHA-256 checksums.

## 2026-11-21 incremental market update

- [Deriv](Deriv/updates/2026-11-21/MANIFEST.json): 141,730 additional closed candles, through 2026-11-21 07:35 UTC.
- [FP Markets](FP-Markets/updates/2026-11-21/MANIFEST.json): 17,245 additional closed candles, through 2026-11-20 21:58 UTC, and 13 additional bid/ask observations through 21:59:59 UTC.

Prior historical files remain unchanged. Load the earlier dataset and the dated updates; for split archives concatenate numbered parts in order, then decompress; use each manifest's SHA-256 and columns. The FP weekend quote observations are historical, not live. This is an available-data snapshot, not a claim of continuous coverage.
