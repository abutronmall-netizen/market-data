# Deriv OHLC history

Reconstruct `candles.csv.gz` by concatenating the ordered `candles.csv.gz.part-XX` files, then decompress gzip. Columns: `symbol,timeframe,start_time_utc,open,high,low,close` (UTC Unix seconds).

**30-bar warmup fix:** 13 symbols have 30 consecutive, fully closed M1, M5, M15, H1, H4 and D1 bars preceding **2026-10-22 00:00:00 UTC**. Native MT5 Deriv history was backfilled from **2026-10-14 through 2026-10-21**; October 22 onward from the previous snapshot is unchanged. Previous backfill from Oct 22–Nov 2 is retained. An actual training pipeline must refresh its dataset and remove any hardcoded start-date filter.

**Known source gap:** Native M1 for **2026-10-18 00:00–01:26 UTC** is not available. These missing minute bars and incomplete M5/M15 buckets were not fabricated. Genuine broker-native archived H1/H4 bars were included to preserve hourly context. Source hashes, overlaps and missing gaps are in `MANIFEST.json`. All client accounts, deals, credentials and execution state are excluded.
