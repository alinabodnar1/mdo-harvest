# harvest-result-2026-09-14-accessnewswire

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-14 / accessnewswire / daily / yesterday / — / —
Started / Finished (Kyiv): 2026-09-14T09:40:14+03:00 / 2026-09-14T09:42:52+03:00
Status: COMPLETE
Pages fetched: 2 (layer L2 / browser, per source table)
Rows total / new / seen: 40 / 0 / 38 (+2 dated RUN_DATE, not recorded — see Notes)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 0 / 0 / 0 / 0 / 0 / 0
Listing pages rebuilt: 2 pages, 38 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | ~09:40 | 20 | Sep 14, 2026 2:00 AM, "Caledonia Mining Corporation Plc: Capital Markets Day Update" | Sep 10, 2026 7:30 AM, "Green Bridge Metals Intersects 195.0 Metres Grading 0.25% Cu and 10.18% TiO2 at Titac South, Minnesota…" (id 1219004) | 2 (both dated RUN_DATE, not recorded) | continuous |
| 2 | ~09:41 | 20 | Sep 10, 2026 7:30 AM, "Green Bridge Metals Intersects 195.0 Metres Grading 0.25% Cu and 10.18% TiO2 at Titac South, Minnesota…" (id 1219362) | Sep 8, 2026 9:00 AM, "Norsemont to Participate at Precious Metals Summit Beaver Creek" | 0 | (last page fetched — minimum depth of 2 satisfied; stop rule already met on page 1, since its oldest row (Sep 10) is older than RUN_DATE−1 = Sep 13) |

Continuity note on the page-1/page-2 boundary: last row of page 1 (id 1219004, Sep 10 7:30 AM) and first row of page 2 (id 1219362, Sep 10 7:30 AM) share an identical title and timestamp but are different article IDs/URLs — evidently two distinct issuer submissions filed at the same stated time, not a pagination duplicate (dedup is by URL; both are already in `seen-urls.txt` from earlier runs). Boundary business-hours gap = 0h → `continuous`.

## Items harvested this run

none — no unseen row on either page fell on RUN_DATE−1 (2026-09-13). See Notes.

## Body boundaries (all sources from v9)

n/a — no articles fetched this run.

## Failures, verbatim

none.

## Remaining (INCOMPLETE only)

n/a — run is COMPLETE.

## Tool use outside fetch/browser

none, beyond reading/writing this run's own state and mirror files on the connected `newswire` folder (via the device shell): reading `run-marker.json`, `index.json`, `seen-urls.txt`; writing `run-marker.json` (started → completed, with the new `top_row`); rebuilding `page1.html`/`page2.html` from the unchanged `index.json` (to refresh the `harvest-run` stamp). `seen-urls.txt` and `index.json` were not modified, since there was nothing new to append. No web search was performed and no link inside a listing or article page was followed.

## Notes

[measured] Freshness check (§3.2b): the previous completed run's marker (2026-09-12) recorded `top_row` = Gamma Resources (id 1220140, "September 11, 2026 8:35 PM"). Today's page-1 top row is different — Caledonia Mining Corporation Plc: Capital Markets Day Update (id 1220338, "September 14, 2026 2:00 AM") — so the listing is fresh; no L1 re-check or STALE_LISTING was needed.

[measured] Of the 40 rows seen across both pages, exactly 2 are unseen: both are dated 2026-09-14 (today, i.e. RUN_DATE) — Caledonia Mining Corporation Plc (id 1220338, 2:00 AM) and Guardian Metal Resources PLC "…Drilling Results Support Potential Resource Growth" (id 1220394, 2:00 AM). Per §3.1 (v11 fix), rows dated RUN_DATE are tomorrow's window: not harvested, and not written to `seen-urls.txt`. The other 38 rows (spanning Sep 8 7:00 AM through Sep 11 8:35 PM) were all already present in `seen-urls.txt` from the 2026-09-11 and 2026-09-12 runs — none required a fresh `# skipped` append.

[measured] **No listing row on either page is dated 2026-09-13 (RUN_DATE−1), the day this run's WINDOW targets.** The listing jumps directly from the two Sep 14, 2:00 AM rows to Sep 11, 8:35 PM with nothing in between across all 40 rows on both pages. 2026-09-12 and 2026-09-13 are Saturday and Sunday; this reads as a genuine quiet weekend for accessnewswire's metals-and-mining category (issuer press releases cluster on weekday business hours) rather than a listing gap: the freshness check confirms the listing is current (it already shows today's 2:00 AM releases), and the minimum-depth walk (2 pages) surfaced no missed rows in between. No `CONTINUITY_GAP` is raised, since the gap-detection rule in §3.3 applies to page-boundary comparisons, not to within-page date jumps, and the only page boundary in this run (page 1 → page 2, both at the Sep 10 7:30 AM timestamp) showed 0 hours of business-time gap.

[measured] Net effect: this run harvested 0 new articles and made no changes to `index.json` or `seen-urls.txt`. `run-marker.json` was still updated (`top_row` refreshed to today's page-1 top row, for tomorrow's freshness check) and the two listing pages were rebuilt from the unchanged `index.json` (same 38 items, `harvest-run` stamp updated to 2026-09-14).

Count of `# skipped` URLs appended this run: 0.
