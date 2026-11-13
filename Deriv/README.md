# Deriv historical synthetic-index candles

Assemble the six ordered parts and verify SHA-256:

```bash
cat candles.csv.gz.part-* > candles.csv.gz
sha256sum candles.csv.gz
# Expected: 5ad0076d56dee4f1531bf8a6f37bd0e1f8b0d878b07cdbee9d52bb4c4fc0b517
```

Then use `gzip -dc candles.csv.gz` to read the CSV. All timestamps are UTC. See `MANIFEST.json` for row count and part hashes.
