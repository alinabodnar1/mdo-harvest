# harvest-result-2026-09-14-im-mining

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-14 / im-mining / daily / yesterday / - / -
Started / Finished (Kyiv): 2026-09-14T10:22:04+03:00 / 2026-09-14T10:23:17+03:00
Status: COMPLETE
Pages fetched: 2
Rows total / new / seen: 24 / 0 / 24
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 0 / 0 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 pages, 23 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 2026-09-14T10:22:xx+03:00 | 12 | 14 Sep 2026, Hancock Iron Ore scales Microsoft Azure AI to extend rail lifespan by 10% | 10 Sep 2026, Ventanas becomes first Codelco operation to achieve 100% worker transport electromobility | 0 (3 rows dated 11 Sep newly recorded as skipped; 2 rows dated 14 Sep not recorded per §3.1; 7 rows dated 10 Sep already seen) | continuous |
| 2 | 2026-09-14T10:22:xx+03:00 | 12 | 10 Sep 2026, University of Arizona receives government funds for San Xavier Underground Mining Lab development | 08 Sep 2026, Sandvik lays down new load and haul markers in Turku | 0 (all rows already in seen-urls.txt) | n/a (min depth reached, oldest row on page 2 older than RUN_DATE-1; walk stopped) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| (none) | | | | | | |

## Body boundaries (all sources from v9)
| id | first 80 chars of body | dateline is paragraph # | last 80 chars of body |
|---|---|---|---|
| (none — no articles fetched this run) | | | |

## Failures, verbatim

(none)

## Remaining (INCOMPLETE only)
(n/a — run is COMPLETE)

## Tool use outside fetch/browser
none

## Notes
[measured] Target window for this run is RUN_DATE-1 = 2026-09-13 (Sunday), Europe/London. Neither listing page (page 1 or page 2) contains any row dated 2026-09-13 or 2026-09-12 — im-mining published nothing on those two calendar dates (weekend gap). This is a genuine content gap, not a listing/continuity fault: page 1's rows jump directly from 14 Sep (2 rows, RUN_DATE, not recorded per §3.1) to 11 Sep (3 rows, recorded as # skipped, older than RUN_DATE-1) to 10 Sep (7 rows, already seen from the 2026-09-11 run).

[measured] No run was performed on 2026-09-12 or 2026-09-13, so articles genuinely dated 2026-09-11 and 2026-09-12 (each source's respective "yesterday" on those missed days) were never in a WINDOW:yesterday target window and are now permanently recorded as # skipped per §3.1/§0.1 — they will not be harvested by a future daily run. This is expected behavior of the WINDOW:yesterday design (only the exact RUN_DATE-1 date is ever harvested), not a bug in this run. Flagging in case a WINDOW:all backfill is wanted to bring 11–13 Sep into the mirror later.

[measured] Prior run-marker.json (from the 2026-09-11 run) had no "top_row" field (that field was only introduced in v13, after the last im-mining run). The §3.2b freshness check could not compare against a stored top_row; treated as no-prior-data and proceeded with a normal walk. This run's marker now stores top_row = the 2026-09-14 page-1 newest row (Hancock Iron Ore / rail lifespan article) for the next run's comparison.

Rows appended to seen-urls.txt this run: 3 (all "# skipped", dated 11 Sep 2026). 0 rows harvested. Minimum walk depth (2 pages) was met; walk stopped there per the stop rule, since page 2's oldest row (08 Sep 2026) is older than RUN_DATE-1.

index.json unchanged (still 23 items, floor remains 2026-09-04). Listing page(s) rebuilt with harvest-run updated to 2026-09-14; 14-day retention cutoff (2026-08-31) did not drop any items.
