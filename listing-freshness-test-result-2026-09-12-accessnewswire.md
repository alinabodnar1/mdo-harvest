# listing-freshness-test-result-2026-09-12-accessnewswire
RUN_DATE / SOURCE / Started / Finished (Kyiv): 2026-09-12 / accessnewswire / 2026-09-12T10:21 / 2026-09-12T10:26

| variant | layer | status | rows (TOTAL) | newest row (date text) | current/stale | note |
|---|---|---|---|---|---|---|
| V1 (baseline) | L1 (WebFetch) | 200 (implied; tool reported no errors) | ~20 (tool gave "approximately 20", not exact) | Sep 11, 2026 7:00 AM — "Silver Tiger Intersects 2.1 Metres..." | current *(passes the ≤24h rule, but see Verdict — proven stale by cross-check)* | Identical top row to the harvest run already logged today at 10:07–10:13 Kyiv (item 1219691). |
| V2 | L1 (WebFetch), `?page=1&nocache=2026091210` | **400 client error** | — | — | n/a | Request failed outright, see Errors. |
| V3 | L1 (WebFetch), `?nocache=2026091210&page=1` (param order swapped) | **400 client error** | — | — | n/a | Same failure with params reordered — not an ordering issue. |
| V4 | L1 (WebFetch), `/newsroom` (all industries) | 200 (implied) | ~20 on page 1 (mixed industries) | Sep 11, 2026 3:25 PM among Metals & Mining–tagged rows (checked explicitly: no "Gamma Resources" 8:35 PM item found anywhere on the page) | current *(passes ≤24h rule; also proven stale — see Verdict)* | Newer than V1 (7:00 AM → 3:25 PM) but still missing the two newest M&M releases that V5 shows. |
| V5 | L2 (browser pane) | 200 (rendered normally) | 20 cards on page (`document.querySelectorAll` count) | Sep 11, 2026 8:35 PM — "Gamma Resources Announces Extension of Private Placement Closing Date" | **current** | Top 5 rows do not exist in V1 at all; row 6 onward matches V1 row-for-row exactly. |
| R1 | L1 (WebFetch), RSS discovered via `<link rel="alternate">` on V5 | 200 | 12 items | pubDate Thu, 09 Jul 2026 — "How to Write an Earnings Call Script That Actually Lands" | **stale / wrong content** | This is the corporate PR-blog feed (`/feed/rss2`), not a news-release feed — oldest item Dec 2025, newest Jul 2026. Not usable as a listing source. An `atom` variant (`/feed/atom`) was also linked but not fetched; same origin, presumably same blog content. |

## Cross-check
Newest 10 rows from V5 (the current variant), each checked against V1:

| # | time (Sep 11 ET unless noted) | headline | in V1? |
|---|---|---|---|
| 1 | 8:35 PM | Gamma Resources Announces Extension of Private Placement Closing Date | **No** |
| 2 | 5:00 PM | Rio Grande Resources Engages Machai Capital for Investor Outreach | **No** |
| 3 | 4:05 PM | Usha Resources Announces Leadership Transition | **No** |
| 4 | 3:25 PM | Algo Grande Copper Intersects 30.23 Metres Grading 1.5% CuEq... | **No** |
| 5 | 11:00 AM | Critical Elements Selected for Canada Investment Summit Prospectus... | **No** |
| 6 | 7:00 AM | Silver Tiger Intersects 2.1 Metres of 7.72 Kilograms... | Yes (V1 row 1) |
| 7 | Sep 10, 10:00 PM | Torq Announces Debt Settlement and Corporate Update | Yes (V1 row 2) |
| 8 | Sep 10, 9:25 PM | Anson Receives $212 Million Additional 'Tax Credit'... | Yes (V1 row 3) |
| 9 | Sep 10, 6:45 PM | Newport Gold, Inc. Engages PCAOB-Registered Auditor... | Yes (V1 row 4) |
| 10 | Sep 10, 5:00 PM | Largo Physical Vanadium Announces Results of Annual Meeting... | Yes (V1 row 5) |

**Count of releases the frozen V1 listing hides right now: 5** (rows 1–5 above). Rows 6–10 line up with V1 exactly, one-for-one, which is itself informative: V1 is not scrambled or partially cached, it is a clean snapshot of the listing as it stood at some point *between* 7:00 AM and 3:25 PM ET on Sep 11 — everything published after that snapshot moment (up to now, 8:35 PM Sep 11) is simply absent.

## Errors, verbatim
- V2: `There was an error while fetching: The page returned a 400 client error`
- V3: `There was an error while fetching: The page returned a 400 client error`

## Tool use outside fetch/browser
- `Bash`/`device_bash` calls to read the local clock (Kyiv/UTC/ET) for timestamping and for computing the `nocache` value. No article body was fetched, no harvest state file was read or written, and no article link was followed. One JavaScript snippet was executed inside the rendered V5 page (`Claude_Browser__javascript_tool`) purely to read `<link rel="alternate">` tags and count listing cards — it read the DOM, it did not submit anything or navigate away.

## Verdict
**V5 (L2 / browser render) is the only variant that returns the actually-current listing; V1 and V4 (both L1 / WebFetch) return snapshots that are stale by 5+ items and 13+ hours respectively, and the nocache-parameter and RSS-discovery workarounds both fail** — nocache returns a hard 400 on this endpoint regardless of parameter order, and the discoverable RSS feed (`/feed/rss2`) is the corporate blog, not a release feed, so it cannot substitute as a listing source. One caveat worth flagging back on the spec itself: the "current = newest row within 24h" test as written does **not** catch this problem — V1's newest row (7:00 AM Sep 11) and V4's (3:25 PM Sep 11) both technically pass that rule at today's fetch time, purely because publication volume is high enough that even a stale snapshot still has *something* inside the last 24h. The cross-check (does the listing contain the newest rows a same-URL browser render shows) is what actually detects the staleness; the 24h rule alone would have passed this run as fine. Recommended change to the harvest source table: switch the accessnewswire listing step from L1 (WebFetch) to L2 (browser pane) for both the category page and, if it's ever used, the all-industries page — mirroring what was already learned about newswire.ca/prnewswire in the coverage-diff skill ("never use WebFetch for the listings"). I cannot yet tell whether V1/V4's staleness is a site-side CDN/cache tier served to non-browser traffic or an artifact of WebFetch's own internal cache (V1's snapshot matches this morning's 10:07–10:13 harvest run almost exactly, which sits inside WebFetch's stated 15-minute cache window) — a clean way to settle that would be a follow-up V1 refetch more than 15 minutes after any other WebFetch call to the same URL, which this run's timing didn't allow.
