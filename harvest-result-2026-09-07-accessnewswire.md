# harvest-result-2026-09-07-accessnewswire

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-07 / accessnewswire / bootstrap / 2026-09-04 / —
Started / Finished (Kyiv): 11:47 / 11:52
Status: COMPLETE
Pages fetched: 1
Rows total / new / seen: 20 / 20 / 0 (state was empty — bootstrap); rows with listing date ≥ SINCE: 3; rows older than SINCE, not harvested: 17
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY: 3 / 0 / 0 / 2 (TEXT_QUALITY items are among the 3 fetched OK; see Notes)
Listing pages rebuilt: 1 pages, 3 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 11:48 | 20 | September 4, 2026 5:00 PM — Golden Minerals Announces Management Change and Argentine Project Update | September 2, 2026 7:00 AM — Earthwise and Eagle Plains Intersect Gold Mineralization in all Holes at the Iron Range Precious Metals Project, SE BC | 20 (3 in scope) | not fetched — oldest row (Sep 2) is earlier than SINCE, bootstrap stop rule met on page 1 |

Page 1 URL: `https://www.accessnewswire.com/newsroom/industry/metals-and-mining?page=1`

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 1216555 | September 4, 2026 7:00 AM | 2026-09-04T07:00:00-04:00 | Storm Exploration Inc. | Storm Further Upsizes Private Placement to $3.2M | TEXT_QUALITY | https://www.accessnewswire.com/newsroom/en/metals-and-mining/storm-further-upsizes-private-placement-to-3.2m-1216555 |
| 1217228 | September 4, 2026 4:30 PM | 2026-09-04T16:30:00-04:00 | Panther Minerals Inc. | Panther Minerals Closes Brokered Private Placement of $3,000,000 | TEXT_QUALITY | https://www.accessnewswire.com/newsroom/en/metals-and-mining/panther-minerals-closes-brokered-private-placement-of-3-000-000-1217228 |
| 1217059 | September 4, 2026 5:00 PM | 2026-09-04T17:00:00-04:00 | Golden Minerals Company | Golden Minerals Announces Management Change and Argentine Project Update | none | https://www.accessnewswire.com/newsroom/en/metals-and-mining/golden-minerals-announces-management-change-and-argentine-project-update-1217059 |

## Failures, verbatim
None. No fetch returned an error or empty content.

TEXT_QUALITY details:
- 1216555 — contact block line reads `E: [email protected]` in the fetched text. The issuer's real e-mail address is replaced by the literal string `[email protected]` (site-side e-mail obfuscation, the address itself is not delivered to the fetch tool) [measured]. Everything else in the body is intact; dateline and `SOURCE: Storm Exploration Inc.` line present.
- 1217228 — same defect: `For more information, please call 877-305-4150, email [email protected].` [measured]. Everything else intact; dateline and `SOURCE: Panther Minerals Inc.` line present.

## Remaining (INCOMPLETE only)
—

## Notes
- State folder `harvest-state/accessnewswire/` did not exist before this run; created. `seen-urls.txt` now holds 3 URLs, `index.json` 3 records [measured].
- Only page 1 was fetched. The bootstrap rule (§3.1) stops as soon as a page's oldest row is older than SINCE; page 1 spans Sep 4 5:00 PM → Sep 2 7:00 AM, so the stop condition was met immediately and no page boundary existed to run the continuity check on [measured]. No new rows dated Sep 5–7 appeared on the listing (Sep 5–6 were a weekend; Sep 7 04:48 ET at fetch time, before the US business day) [measured].
- Ordering anomaly on the source listing: row 2 (Panther, `September 4, 2026 4:30 PM`) has a higher article id (1217228) than row 1 (Golden Minerals, 5:00 PM, id 1217059). Article ids on ACCESS Newswire are not monotonic with listing time [measured]. The harvest orders by listing time, not id.
- Duplicate releases on page 1 (outside SINCE scope, not harvested): rows 6 and 7 are the same headline "Arcus & Core Mobilize for 3,000 Metre Drilling Program…" under two ids (1216082, 1216088); rows 19 and 20 are the Eagle Plains / Earthwise joint release published twice with the issuer names swapped (1215224, 1215271) [measured]. Expect the same pattern in daily runs — the by-URL dedup will keep both copies, which is correct for a copy layer.
- Golden Minerals article page shows a chrome timestamp line `Friday, 04 September 2026 05:00 PM` between headline and dateline [measured]; excluded from the body per §4.2 (body starts at the dateline). This line confirms the listing timezone inference only weakly — it matches the listing time but does not name a zone.
- All three bodies begin with the dateline and end with the `SOURCE:` line; no TEXT_TRUNCATED [measured]. Body sizes: 1216555 ≈ 2.9 k chars, 1217059 ≈ 3.5 k chars, 1217228 ≈ 8.9 k chars [measured]. The 1217059 body size matches the 08:05 Kyiv test fetch (~3,494 chars) [measured].
- All 4 HTML files parse with Python's html.parser without error [measured].
