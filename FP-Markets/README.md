# FP Markets historical candle data

The canonical FP Markets OHLC archive has been extended with genuine broker-native MT5 history across active sessions, **28 October – 6 November 2026**, including the candles required by the **5 November** training entries. Earlier records are preserved. Data includes **13 normalized symbols**; no private trading or client account records are published.

## Assemble the canonical dataset

From the repository root:

    cat FP-Markets/candles.csv.gz.part-* > FP-Markets/candles.csv.gz
    sha256sum FP-Markets/candles.csv.gz

The assembled SHA-256 must match datasets[0].sha256 in FP-Markets/MANIFEST.json. The prior single-file GitHub archive was superseded; use the numbered parts as the canonical price-history source. The compression is gzip, CSV columns are symbol,broker_symbol,timeframe,start_time_utc,open,high,low,close,broker_time_raw.

The start_time_utc value is a UTC Unix timestamp. Native FP Markets server time is **UTC+02:00** for these samples, validated by matching overlapping broker-native H1 prices; broker_time_raw is retained. **Do not treat broker_time_raw as UTC.** For training, deduplicate repeated multi-account observations by (symbol, timeframe, start_time_utc), and calculate features using only **closed candles at or before each entry time**. No synthetic minute candles were created over broker market closures or gaps.

The original **quotes.csv.gz remains unchanged**: no historical November 5 bid/ask quote records were reconstructed from OHLC. See MANIFEST.json for counts, file hashes and source provenance.
