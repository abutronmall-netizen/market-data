# Deriv historical synthetic-index candles

Assemble ordered parts with `cat candles.csv.gz.part-* > candles.csv.gz`. Verify SHA-256 against `MANIFEST.json`, then read with `gzip -dc candles.csv.gz`. Timestamps are UTC; this is a snapshot, not a live feed.
