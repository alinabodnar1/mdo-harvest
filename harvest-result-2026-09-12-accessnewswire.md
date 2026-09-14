# harvest-result-2026-09-12-accessnewswire

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-12 / accessnewswire / daily / yesterday / — / —
Started / Finished (Kyiv): 2026-09-12T10:41:07+03:00 / 2026-09-12T11:17:27+03:00
Status: COMPLETE
Pages fetched: 2 (layer L2 / browser, per source table)
Rows total / new / seen: 40 / 5 / 35
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 5 / 0 / 0 / 0 / 5 / 0
Listing pages rebuilt: 2 pages, 38 items

## Walk
| page | fetched (Kyiv, approx.) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | ~10:42 | 20 | Sep 11, 2026 8:35 PM, "Gamma Resources Announces Extension of Private Placement Closing Date" | Sep 10, 2026 9:10 AM, (row at page boundary) | 5 | overlap |
| 2 | ~10:43 | 20 | Sep 10, 2026 (row at page boundary) | Sep 8, 2026 (row at page boundary) | 0 | (last page fetched — minimum depth of 2 satisfied, stop rule already met on page 1: all 5 new rows and the seen/unseen boundary fell within page 1) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 1220140 | September 11, 2026 8:35 PM | 2026-09-11T20:35:00-04:00 | Gamma Resources Ltd. | Gamma Resources Announces Extension of Private Placement Closing Date | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/gamma-resources-announces-extension-of-private-placement-closing-date-1220140 |
| 1219985 | September 11, 2026 5:00 PM | 2026-09-11T17:00:00-04:00 | Rio Grande Resources Ltd. | Rio Grande Resources Engages Machai Capital for Investor Outreach | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/rio-grande-resources-engages-machai-capital-for-investor-outreach-1219985 |
| 1220001 | September 11, 2026 4:05 PM | 2026-09-11T16:05:00-04:00 | Usha Resources Ltd. | Usha Resources Announces Leadership Transition | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/usha-resources-announces-leadership-transition-1220001 |
| 1219909 | September 11, 2026 3:25 PM | 2026-09-11T15:25:00-04:00 | Algo Grande Copper Corp. | Algo Grande Copper Intersects 30.23 Metres Grading 1.5% CuEq, including 3.55 Metres at 9.4% CuEq and 1.2-Metre Interval at 15.8% CuEq, 100 Metres Vertical Step-Out from Historical Intersects | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/algo-grande-copper-intersects-30.23-metres-grading-1.5-cueq-including-3.55-metres-1219909 |
| 1219819 | September 11, 2026 11:00 AM | 2026-09-11T11:00:00-04:00 | Critical Elements Lithium Corporation | Critical Elements Selected for Canada Investment Summit Prospectus, Showcasing Project to Leading Global Investors | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/critical-elements-selected-for-canada-investment-summit-prospectus-showcasing-pro-1219819 |

## Body boundaries
| id | first 80 chars of body | dateline paragraph # | last 80 chars of body |
|---|---|---|---|
| 1220140 | "VANCOUVER, BC / ACCESS Newswire / September 11, 2026 / GAMMA Resources Ltd (TSXV" | 1 | "SOURCE: Gamma Resources LTD" |
| 1219985 | "VANCOUVER, BC / ACCESS Newswire / September 11, 2026 / Rio Grande Resources Ltd." | 1 | "SOURCE: Rio Grande Resources" |
| 1220001 | "VANCOUVER, BC / ACCESS Newswire / September 11, 2026 / Usha Resources Ltd. ("Ush" | 1 | "SOURCE: Usha Resources Ltd." |
| 1219909 | "First assay results received from the Company's Phase II diamond drilling progra" | 6 (sub-headline + 4 HIGHLIGHTS bullets precede the dateline paragraph) | "SOURCE: Algo Grande Copper Corp." |
| 1219819 | "MONTRÉAL, QC / ACCESS Newswire / September 11, 2026 / Critical Elements Lithium " | 1 | "SOURCE: Critical Elements Lithium Corp." |

## Failures, verbatim

none — all 5 new items fetched and mirrored successfully. Two items required a corrective second WebFetch pass before the body met the fidelity bar (see Notes); neither is a FETCH_FAILED, since the final body written to the mirror is the fully verified, correct one.

## Remaining (INCOMPLETE only)

n/a — run is COMPLETE

## Tool use outside fetch/browser

Every call outside the mandated WebFetch article requests and the L2 browser listing render was a read or write of this run's own state, article, and mirror files on the connected `newswire` folder: reading/updating `run-marker.json` (started → completed, with `top_row`), appending 5 URLs to `seen-urls.txt`, appending 5 records to `index.json`, writing the 5 new article files under `mirror/accessnewswire/articles/`, and rebuilding `page1.html`/`page2.html` from the updated index — as required by §2, §4 step 5, and §5. To get the article-writing and listing-rebuild logic to run on the connected device, two short Python scripts were composed in the working environment and transferred to the device via a base64-encoded copy, then executed there with `python3`; this is standing infrastructure for moving generated file content onto the connected folder, not a deviation from the harvest procedure — no web search was performed and no link inside a harvested article was followed.

## Notes

[measured] Before this run started, `harvest-result-2026-09-12-accessnewswire.md` already existed for today, written by an earlier same-day run at 2026-09-12T10:07:24–10:13:20 Kyiv, reporting Status COMPLETE with only 1 new item (id 1219691, Silver Tiger Metals) out of 40 listing rows across 2 pages. A separate diagnostic run in between (`listing-freshness-test-result-2026-09-12-accessnewswire.md`, 10:21–10:26 Kyiv) directly tested the accessnewswire listing step and found that the L1 (WebFetch) listing snapshot was stale by 5+ items and 13+ hours relative to the L2 (browser-rendered) listing, and recommended the source table require L2 for this source's listing step — which harvest-prompt-v13.md's source table already specifies. That means the 10:07–10:13 run under-harvested: it should have found the 5 additional Sep-11-dated releases (Gamma Resources, Rio Grande Resources, Usha Resources, Algo Grande Copper, Critical Elements Lithium) that were live on the site by the time it ran, but its listing fetch missed them.

This run followed v13's own source-table mandate (L2/browser for the accessnewswire listing step) and, on page 1, saw the current, complete listing headed by Gamma Resources (8:35 PM). Checking all 40 rows across both pages against `seen-urls.txt` found exactly the 5 URLs the diagnostic had flagged as missing, still unseen; all 5 were fetched and mirrored this run via the normal dedup mechanism, with no special-cased "re-run" logic needed. This file replaces the 10:07–10:13 result file for RUN_DATE 2026-09-12 / accessnewswire, since v13 §6 keeps one result file per run_date+source; the totals above (40 rows / 5 new / 35 seen, 38 items in the rebuilt listing) are the corrected, complete figures for the day. The earlier run's own result file is not otherwise altered or deleted.

[measured] Two of the five new articles needed a second, targeted WebFetch pass before the body met the no-paraphrase fidelity bar in §4:
- Usha Resources (1220001): the first WebFetch pass returned a condensed, restructured summary (missing the dateline paragraph and merging paragraphs). A second WebFetch request, quoting the article's actual opening words and asking for the text verbatim through to the SOURCE line, returned the complete, correctly structured body, which was then transcribed with markdown stripped per §4 step 3 while preserving the literal masked-email text per the EMAIL_MASKED rule.
- Algo Grande Copper (1219909): the first pass's output had two page-chrome lines ("Friday, 11 September 2026 03:25 PM" and "Topic: Company Update") sitting between the title and the HIGHLIGHTS block. These are explicitly non-body per §4 step 2 (the page's own date/time line and Topic:/category label) and were excluded when transcribing; the HIGHLIGHTS bullets and the dateline paragraph immediately after were kept in order, and the multi-sentence quote from João Rocha was verified against the source text on a second pass.

Neither case is recorded as TEXT_QUALITY, since the body actually written to the mirror is the verified, correct one, not the flawed first draft.

[note on this result file's own timestamps] Page-level listing-fetch times in the Walk table above are approximate: this session's context was compacted partway through the run, and the sub-minute timestamps for the two individual L2 page loads were not separately preserved outside the run-level `started`/`finished` markers now in `run-marker.json`. The run's start (10:41:07) and finish (11:17:27, when state finalization and this file were completed) are solid; the ~10:42/~10:43 page-fetch times are a best-effort reconstruction of ordering within that window, not a verified log — flagging this as a gap in this run's own record-keeping rather than presenting false precision.
