# harvest-result-2026-09-08-newsfile

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-08 / newsfile / daily / — / —
Started / Finished (Kyiv): 11:04 / 11:15
Status: COMPLETE
Pages fetched: 3 (minimum depth for newsfile; no further page required — see Notes on the stop rule)
Rows total / new / seen: 60 / 59 not in seen-urls.txt (2 in scope, 57 pre-bootstrap — see Notes) / 1
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 2 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 pages, 3 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 11:04 | 20 | 2026-09-08 12:30 AM EDT — Goldgroup Reports Strong First Results from 26,000 Metre San Francisco Drill Program | 2026-09-04 8:00 AM EDT — Urbana Corporation - Renewal of Normal Course Issuer Bid | 19 not in seen (2 in scope: 313311, 313288; 17 dated Sep 4, pre-bootstrap) / 1 seen (313191) | continuous — Sep 4 8:00 AM → Sep 4 7:30 AM, business-hours portion 0.5 h |
| 2 | 11:05 | 20 | 2026-09-04 7:30 AM EDT — World Copper Announces Board and Management Changes; Non-Brokered Private Placement | 2026-09-03 4:05 PM EDT — Canadian Gold Resources Increases Québec Gaspé Land Position by 72% Through Strategic Staking Along the Garin River Fault | 20 not in seen (0 in scope; all Sep 3–4, pre-bootstrap) / 0 seen | continuous — Sep 3 4:05 PM → Sep 3 3:00 PM, business-hours portion 1 h 05 min |
| 3 | 11:05 | 20 | 2026-09-03 3:00 PM EDT — Spark Energy Minerals Appoints Marina Fagundes de Freitas to its Board of Directors | 2026-09-03 7:29 AM EDT — Benton and Metals Creek Acquire an Additional 262 Claim Units at Smoking Gun Hydrogen-Helium in Newfoundland, Await Final Result from Soil Gas Sampling Program | 20 not in seen (0 in scope; all Sep 3, pre-bootstrap) / 0 seen | not fetched further — minimum depth reached, no row newer than the bootstrap SINCE remains |

Page URLs: `https://www.newsfilecorp.com/news/mining-metals?pg=1`, `?pg=2`, `?pg=3`.

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 313288 | 2026-09-07 7:55 PM EDT | 2026-09-07T19:55:00-04:00 | Sigma Lithium Corporation | Sigma Lithium Confirms Its Mining and Industrial Operations Remain Unaffected by a Preliminary Judicial Ruling Issued Without Due Process | none | https://www.newsfilecorp.com/release/313288/Sigma-Lithium-Confirms-Its-Mining-and-Industrial-Operations-Remain-Unaffected-by-a-Preliminary-Judicial-Ruling-Issued-Without-Due-Process |
| 313311 | 2026-09-08 12:30 AM EDT | 2026-09-08T00:30:00-04:00 | Goldgroup Mining Inc. | Goldgroup Reports Strong First Results from 26,000 Metre San Francisco Drill Program | none | https://www.newsfilecorp.com/release/313311/Goldgroup-Reports-Strong-First-Results-from-26000-Metre-San-Francisco-Drill-Program |

## Body boundaries (trade-press sources only)
n/a — wire source.

## Failures, verbatim
None. No fetch returned an error or empty content.

## Remaining (INCOMPLETE only)
—

## Notes
- **Spec gap, decided with the user during the run.** `seen-urls.txt` held 1 URL after the 2026-09-07 bootstrap (SINCE 2026-09-05), so 57 rows dated Sep 3–4 on pages 1–3 are "not in seen-urls" although the bootstrap excluded them on purpose. Read literally, §4 ("for every new URL") would fetch all 57, and the daily stop rule of §3.1 ("every row already in seen-urls") could not trigger on any page — the walk had no bound short of the site's end (daily mode has no hard cap) [measured]. The user chose: harvest only rows with listing date ≥ the bootstrap SINCE (2 articles), stop at the minimum depth. The 57 pre-bootstrap URLs were **not** added to `seen-urls.txt`, so they will show as "not seen" again tomorrow. Suggested fix for v8: (a) on bootstrap, write every listed URL older than SINCE to `seen-urls.txt` (or a separate `skipped-urls.txt`) so the daily stop rule has something to stop on; and (b) add a hard cap (8 pages) to daily mode as bootstrap already has.
- Fetch timing: page 1 fetched 11:04 Kyiv = 04:04 ET. Only two rows newer than Sep 6 existed: Sep 7 7:55 PM (Labor Day evening) and Sep 8 12:30 AM [measured]. Sep 7 was a US/Canadian holiday; the ET business day of Sep 8 had not started.
- Both page boundaries were `continuous` (0.5 h and 1 h 05 min of business time) [measured]. Contrast with 7 Sep, when a 23-hour hole sat between pages 1 and 2 — the boundary position is not stable from day to day.
- Row order is by listing time; ids are not monotonic (e.g. 312928 and 313074 sit between 313139 and 313155 on page 1) [measured]. URL, not id, remains the dedup key.
- **313311 — fetch-layer fabrication, caught and discarded.** Tables 1 and 2 of the Goldgroup release are images on the source page (`images.newsfilecorp.com/files/1060/313311_ggtbl1…jpg`, `…ggtbl2…jpg`). On the first pass the fetch tool's reader returned two fully-formed tables with plausible headers, all six holes at identical coordinates/azimuth/dip/depth and cells reading "Various" — invented content [measured]. A second request for the tables alone answered "TABLE NOT IN TEXT"; a third request for the exact section between "Highlights include:" and "Next Steps" returned the captions, `[IMAGE]` placeholders, the "To view an enhanced version of this graphic" lines and the Notes lines, and no table rows [measured]. The written body uses the third pass for that section (captions, image-link lines, Notes, Figure 1–3 captions kept as text; no table rows). The rest of the body comes from the first pass, which matched the third pass sentence for sentence in the overlapping section. Marker left `none`: the release text is intact and the tables have no text on the source page. Recommendation for v8: for any release whose first pass returns a table, ask the fetch tool a second time for that table alone and drop it unless the second pass reproduces it — the reader model fills image tables from context.
- 313311 body: highlights list says GGD-178 16.8 m @ 4.36 g/t incl. 10.9 m @ 6.34 g/t; the following paragraph says 4.35 / 6.33. Both values are in the source text (confirmed on two independent passes) — kept as printed, not reconciled [measured].
- 313311: bullet lists (three objectives, four highlights) arrived as markdown `- ` bullets; the marker was removed and each item written as its own `<p>` per §4.3 [measured].
- 313288: contact e-mails `anna.hartley@sigmalithium.com.br`, `mariana.bengtson@sigmalithium.com.br` and 313311 `ir@goldgroupmining.com` arrived unmasked — no `EMAIL_MASKED` on newsfilecorp.com, consistent with 7 Sep [measured]. Social lines ("LinkedIn: Sigma Lithium" etc.) are link text; link targets dropped with the markup.
- 313288 body: 53 paragraphs, 11.5 k chars; 313311 body: 97 paragraphs, 23.4 k chars. Each begins with the dateline paragraph and ends with the `To view the source version…` line (asserted programmatically before writing) [measured].
- Article files written this run carry `<meta name="layer">` and `<meta name="kind">` per the v7 template; the 2026-09-07 file `313191.html` (v6 template) lacks both and was not rewritten (§7) [measured].
- Listing page1.html rebuilt from `index.json`: 3 items, all within 14 days, 1 page [measured]. `index.json` 3 records, `seen-urls.txt` 3 URLs.
- Housekeeping: a temporary transfer file `new-records-2026-09-08.tmp.json` (the 2 new index records, used to move them onto the machine) could not be deleted by this session and was moved to `newswire/_to_delete/` — safe to delete.
- All 4 HTML files parse with Python's html.parser without error [measured].
