# harvest-result-2026-09-14-businesswire

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-14 / businesswire / daily / yesterday / - / -
Started / Finished (Kyiv): 2026-09-14 10:33 / 2026-09-14 10:45
Status: COMPLETE
Pages fetched: 2
Rows total / new / seen: 20 / 0 / 19 (1 row dated RUN_DATE, not recorded per WINDOW:yesterday)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 0 / 0 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 page, 11 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 2026-09-14 10:34 | 10 (TOTAL=10) | Sep 14, 2026 at 3:05 AM, Nano One Selected for Inaugural Canada Investment Summit 2026 | Sep 9, 2026 at 10:19 PM, BKV Corporation Prices Upsized $500 Million Convertible Senior Notes Offering | 0 | continuous |
| 2 | 2026-09-14 10:35 | 10 (TOTAL=10) | Sep 9, 2026 at 8:30 PM, Nyangumarta Warrarn Aboriginal Corporation and Rio Tinto sign milestone agreement for Winu Project | Sep 8, 2026 at 9:00 AM, Efficient Markets Reports Record BLM Utah Geothermal Lease Sale | 0 | n/a (walk stopped) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
none

## Body boundaries (all sources from v9)
| id | first 80 chars of body | dateline is paragraph # | last 80 chars of body |
|---|---|---|---|
n/a — no articles fetched this run

## Failures, verbatim
none

## Remaining (INCOMPLETE only)
n/a

## Tool use outside fetch/browser
none

## Notes
[measured] Sep 13, 2026 is a Sunday and Sep 12, 2026 a Saturday; the walk window (RUN_DATE-1 = Sep 13) contains zero listing rows — the wire published nothing that day. All 19 non-today rows across pages 1-2 were already present in seen-urls.txt from prior runs (through 2026-09-12); 0 new rows, 0 new `# skipped` rows appended this run. The single Sep 14 (today) row was left unrecorded per §0.1/§3.1 (tomorrow's window). Freshness check (§3.2b): stored top_row (Masan, .../20260910612111) differed from today's page-1 top row (Nano One, .../20260914324675) → listing judged fresh, no stale-listing branch triggered.

Spec note for review, not acted on: §3.2b's stale-listing branch instructs re-fetching page 1 via L2 for any L1-listing source, but §Environment explicitly forbids Business Wire from ever using L2 ("blocks the home network"). This run's listing was fresh so the conflict did not fire, but if Business Wire's listing ever repeats its top row for >12 business hours, the spec as written has no valid action for it — worth resolving before that happens.

Minimum walk depth (2 pages) was fetched even though the WINDOW:yesterday stop rule would have ended the walk after page 1 (page 1's oldest row, Sep 9, is older than RUN_DATE-1 = Sep 13).
