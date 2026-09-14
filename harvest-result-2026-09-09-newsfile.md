# harvest-result-2026-09-09-newsfile

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-09 / newsfile / daily / — / —
Started / Finished (Kyiv): 09:08 / 09:15
Status: COMPLETE — **with a suspected stale listing, see Notes (1)**
Pages fetched: 3 (minimum depth for newsfile; stop rule of §3.1 satisfied on every page)
Rows total / new / seen: 60 / 0 new in scope (57 older than floor → written as `# skipped`) / 3
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 0 / 0 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 pages, 3 items

Floor (oldest date in `index.json`): 2026-09-06T17:00:00-04:00.

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 09:10 | 20 | 2026-09-08 12:30 AM EDT — Goldgroup Reports Strong First Results from 26,000 Metre San Francisco Drill Program | 2026-09-04 8:00 AM EDT — Urbana Corporation - Renewal of Normal Course Issuer Bid | 0 new / 3 seen / 17 older than floor (Sep 4) | continuous — Sep 4 8:00 AM → Sep 4 7:30 AM, business-hours portion 0.5 h |
| 2 | 09:11 | 20 | 2026-09-04 7:30 AM EDT — World Copper Announces Board and Management Changes; Non-Brokered Private Placement | 2026-09-03 4:05 PM EDT — Canadian Gold Resources Increases Québec Gaspé Land Position by 72% Through Strategic Staking Along the Garin River Fault | 0 new / 0 seen / 20 older than floor | continuous — Sep 3 4:05 PM → Sep 3 3:00 PM, business-hours portion 1 h 05 min |
| 3 | 09:12 | 20 | 2026-09-03 3:00 PM EDT — Spark Energy Minerals Appoints Marina Fagundes de Freitas to its Board of Directors | 2026-09-03 7:29 AM EDT — Benton and Metals Creek Acquire an Additional 262 Claim Units at Smoking Gun Hydrogen-Helium in Newfoundland, Await Final Result from Soil Gas Sampling Program | 0 new / 0 seen / 20 older than floor | not fetched further — minimum depth reached, stop rule satisfied on pages 1–3 |

Page URLs: `https://www.newsfilecorp.com/news/mining-metals?pg=1`, `?pg=2`, `?pg=3` (L1, WebFetch).

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| — | — | — | — | none | — | — |

## Body boundaries (all sources from v9)
| id | first 80 chars of body | dateline is paragraph # | last 80 chars of body |
|---|---|---|---|
| — | n/a — no article fetched this run | — | — |

## Failures, verbatim
None. All three listing fetches returned content; no article fetch was attempted.

## Remaining (INCOMPLETE only)
—

## Tool use outside fetch/browser
- `device_bash` (shell on the user's computer, folder `newswire`) — 3 calls: read state (`seen-urls.txt`, `index.json`, previous result file); run `mig.py` (append `# skipped` rows, §2.1 migration); run `rebuild.py` (rebuild `mirror/newsfile/page1.html`, §5.2). Scratch scripts kept in the VM `$HOME`, outside the folder.
- `Bash` (cloud container) — 2 calls of `sleep 2`, pacing between listing fetches (§3).
- `Write` — this result file.
- No web search, no browser, no article link followed.

## Notes
1. **Suspected stale listing — the pages did not change in 22 hours [measured].** All 60 rows on pages 1–3 are identical, in order and in date text, to the 60 rows recorded by the 2026-09-08 run (fetched 11:04 Kyiv = 04:04 ET on Sep 8). Today's fetch was at 09:10 Kyiv = 02:10 ET on Sep 9. Taken at face value, the listing says Newsfile's Mining & Metals category published **nothing** during the whole ET business day of Tuesday 8 September (the first working day after Labor Day), while the newest row remains 313311 at 12:30 AM EDT Sep 8. Two points make that reading implausible: (a) on the 7–8 Sep runs this category showed 20–40 rows per business day (Sep 3: ≥ 37 rows across pages 2–3; Sep 4: ≥ 28 rows) [measured]; (b) row 312966 on page 2 is Ivanhoe Mines announcing that it *will* issue a Western Forelands update on September 8, 2026 — no such release appears on pages 1–3 [measured]. The likely cause is a cached copy of `?pg=N` served to the fetch layer (data-centre) — the same mechanism §1 already documents for the bare URL ("The bare URL is stale") and for Business Wire (frozen without `nocache`). §1 forbids changing the URL and §7 forbids the browser on an L1 source, so this run did not test either hypothesis. **No release from Sep 8 has been harvested; the state is correct for what the pages showed, but the mirror is probably missing a full business day.** Decision needed (see chat): allow a `nocache`-style parameter for `newsfile`, re-run later in the day, or authorise a one-off L2 comparison as was done for australianmining on 7 Sep.
2. **v8 migration performed:** 57 rows older than the floor (17 on page 1, 20 on page 2, 20 on page 3; all dated Sep 3–4) appended to `seen-urls.txt` with the `# skipped <listing date>` suffix. `seen-urls.txt` now holds 60 lines (3 harvested + 57 skipped). The daily stop rule of §3.1 now has something to fire on: on tomorrow's run every row on pages 1–3, as they stand, is either seen or skipped [measured].
3. Both page boundaries `continuous` (0.5 h and 1 h 05 min of business time), identical to 8 Sep — expected, since the pages themselves are identical [measured].
4. No article file written, no `index.json` record added; `mirror/newsfile/page1.html` rebuilt from `index.json` with `harvest-run` = 2026-09-09 (3 items, all within 14 days, 1 page). No existing `articles/<id>.html` touched [measured].
5. The stop rule and the minimum-depth rule of v9 worked as written: with the skipped rows recorded, the walk is bounded at 3 pages instead of running to the site's end as on 8 Sep. The stale-listing problem in Note 1 is orthogonal to this — a bounded walk over stale pages is still a walk over stale pages.
6. Recommendation for v10, if Note 1 is confirmed: (a) add a cache-buster to the `newsfile` listing URL on the same terms as `businesswire` (`&nocache=<RUN_DATE digits><Kyiv hour>`, identical within a run) — to be **measured first** on one run, not adopted blindly, since Newsfile may ignore or reject unknown parameters; (b) add a **freshness check** to §3: if the first row of page 1 is already in `seen-urls.txt` *and* more than 12 business hours (source zone) have passed since its listing time, the run must flag `STALE_LISTING` in Status rather than report `COMPLETE`. The current status enum cannot express what happened today.
