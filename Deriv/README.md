# Deriv OHLC history

Broker-native OHLC data only. The canonical dataset is the concatenation of all ordered `candles.csv.gz.part-XX` chunks, decompressible as gzip CSV. Columns: `symbol,timeframe,start_time_utc,open,high,low,close`; timestamps are UTC Unix seconds.

**2026-10-22 through 2026-11-02** was backfilled from complete and independently validated M1 records found in Deriv-Demo MT5 native HCC history caches. On November 2, the MT5 cache lacks seven minutes around 13:00 UTC; missing bars are not synthesized. M5, M15, H1, H4 and D1 candles were aggregated from those M1 bars and checked against overlapping original broker-native OHLC. Data before October 22 and after November 2 from the previous snapshot remain unchanged. This extends the early lower-timeframe training window, including October 24. A consuming trainer must replace its old cache and must not hardcode a November 2 start.

`MANIFEST.json` contains SHA-256 checksums, validation coverage and original snapshot digest. No customer identity or trading records are included.
