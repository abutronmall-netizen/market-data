# FP Markets historical market data

`candles.csv.gz` contains OHLC price candles and `quotes.csv.gz` contains bid/ask quote observations. Read with `gzip -dc <file>`. UTC timestamps. Repeated historical rows may originate from overlapping broker DEMO exports; new native additions are deduplicated by instrument and timestamp. This snapshot contains market-only records. See `MANIFEST.json` for row counts, dates and SHA-256 checksums.
