# harvest-result-2026-09-14-newsfile

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-14 / newsfile / daily / yesterday / — / —
Started / Finished (Kyiv): 10:41 / 11:10
Status: COMPLETE
Pages fetched: 3
Rows total / new / seen: 60 / 33 / 27
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 1 / 0 / 0 / 0 / 0 / 0
Listing pages rebuilt: 4 pages, 96 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 10:42 | 20 | 2026-09-14 3:00 AM EDT, Teako Minerals Launches New Corporate Brand, Website and Expanded Digital Presence | 2026-09-11 8:44 AM EDT, Antimony Resources Corp. (ATMY) (ATMYF) (K8J0) Reports High-Grade Antimony (Sb) Assays | 20 | continuous (last 09-11 8:44 AM → first 09-11 8:10 AM, ~0.6h) |
| 2 | 10:46 | 20 | 2026-09-11 8:10 AM EDT, Atlantico Confirms Gallium and Rare Earths in All 114 Follow-Up Samples at Novo Cruzeiro | 2026-09-10 5:00 PM EDT, Adex Mining Announces Results of Annual General and Special Meeting of Shareholders | 12 | continuous (last 09-10 5:00 PM = first 09-10 5:00 PM, 0h) |
| 3 | 10:50 | 20 | 2026-09-10 5:00 PM EDT, Wesdome Intersects 7.8 g/t Gold over 57.2 Metres at Kiena Deep | 2026-09-10 8:00 AM EDT, Mackay Gold & Silver to Acquire the Historic Big Bonanza | 1 | not evaluated — minimum depth (3 pages) reached, walk stopped |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 314101 | 2026-09-13 8:27 AM EDT | 2026-09-13T08:27:00-04:00 | NSJ Gold Corp. | NSJ Gold Corp. (NSJ) (9PZ) Announces Closing of Over-Subscribed Financing for Exploration and Development on its Antimony 2.0 Property, New Brunswick, Canada | none | https://www.newsfilecorp.com/release/314101/NSJ-Gold-Corp.-NSJ-9PZ-Announces-Closing-of-OverSubscribed-Financing-for-Exploration-and-Development-on-its-Antimony-2.0-Property-New-Brunswick-Canada |

## Body boundaries (all sources from v9)
| id | first 80 chars of body | dateline paragraph # | last 80 chars of body |
|---|---|---|---|
| 314101 | Vancouver, British Columbia--(Newsfile Corp. - September 13, 2026) - NSJ Gold Co | 1 | ors / Jag Sandhu, CEO and President / Tel: 604-501-1214, Email: JAGJNS@OUTLOOK.COM |

## Failures, verbatim

none

## Remaining (INCOMPLETE only)

n/a — run COMPLETE

## Tool use outside fetch/browser

none

## Notes

- WINDOW: yesterday = 2026-09-13 (ET). Only one listing row was dated 2026-09-13 on this source (314101, 8:27 AM EDT) — the gap between it and the next-older row (37 Capital, 2026-09-11 8:04 PM EDT) spans all of Saturday 2026-09-12 and most of Sunday 2026-09-13, which is the expected weekend quiet period for issuer press releases; no CONTINUITY_GAP condition applies because the intervening hours fall on a weekend, not business hours.
- Rows dated 2026-09-14 (RUN_DATE) seen on page 1 (314151, 314096, 314114, 314103) were excluded per §3.1/§0.1 and NOT written to seen-urls.txt; they remain for tomorrow's run.
- 28 rows dated 2026-09-10/09-11 (older than RUN_DATE-1) were newly appended to seen-urls.txt with " # skipped <date>" (§2.1). Total appended to seen-urls.txt this run: 29 (1 harvested + 28 skipped).
- run-marker.json found before this run had status "completed" from 2026-09-11 (the last time newsfile ran) but was missing the "top_row" field entirely — an older-version artifact. §3.2b's page-1 freshness comparison could not be performed against a stored top_row; it was skipped this run and the marker now stores top_row (314151, "2026-09-14 3:00 AM EDT") going forward so the next run can compare normally. Flagging this for you: newsfile had not been run since 2026-09-11 (three calendar days), so rows dated 2026-09-12 and most of 2026-09-13 were never in that day's WINDOW:yesterday and, per the harvest design (§0.1), never will be — they are only in the mirror if you later do a WINDOW:all backfill run.
- No tables, no quotations longer than one sentence, and no e-mail masking observed in the harvested article; text fidelity check (§4 step 1c) passed with no markup remnants.
- L2 listing extraction (§3.2L) returned exactly 20 rows per page (TOTAL=20), matching expected rows/page for newsfile; no LISTING_SHORT.
