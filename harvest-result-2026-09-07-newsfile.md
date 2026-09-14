# harvest-result-2026-09-07-newsfile

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-07 / newsfile / bootstrap / 2026-09-05 / —
Started / Finished (Kyiv): 12:15 / 12:24
Status: COMPLETE
Pages fetched: 1
Rows total / new / seen: 20 / 20 / 0 (state was empty — bootstrap); rows with listing date ≥ SINCE: 1; rows older than SINCE, not harvested: 19
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 1 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 pages, 1 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 12:17 | 20 | 2026-09-06 5:00 PM EDT — South Pit Drilling Continues to Intersect High-Grade Mineralization, Cotabambas Project, Peru | 2026-09-04 7:00 AM EDT — Mogotes Closes Season at Filo Sur with New Porphyry Targets at Luz del Sol and Cuenca; Plans 20,000 m of Drilling for 2026-2027 | 20 (1 in scope) | not fetched — oldest row (Sep 4) is earlier than SINCE, bootstrap stop rule met on page 1 |

Page 1 URL: `https://www.newsfilecorp.com/news/mining-metals?pg=1`

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 313191 | 2026-09-06 5:00 PM EDT | 2026-09-06T17:00:00-04:00 | Panoro Minerals Ltd. | South Pit Drilling Continues to Intersect High-Grade Mineralization, Cotabambas Project, Peru | none | https://www.newsfilecorp.com/release/313191/South-Pit-Drilling-Continues-to-Intersect-HighGrade-Mineralization-Cotabambas-Project-Peru |

## Failures, verbatim
None. No fetch returned an error or empty content.

## Remaining (INCOMPLETE only)
—

## Notes
- State folder `harvest-state/newsfile/` did not exist before this run; created. `seen-urls.txt` now holds 1 URL, `index.json` 1 record [measured].
- Only page 1 was fetched. Page 1 spans Sep 6 5:00 PM EDT → Sep 4 7:00 AM EDT, so the bootstrap stop rule (§3.1) was met immediately; no page boundary existed for the continuity check [measured]. Row 1 (Sep 6, Sunday) is followed directly by row 2 (Sep 4 7:57 PM) — no rows dated Sep 5 on page 1 [measured]. Given the 23-hour hole between pages 1 and 2 seen earlier on 7 Sep, a Sep 5 release could in principle sit on page 2 without appearing here; the bootstrap rule as written does not require checking page 2, so this run did not. If that matters, add a minimum depth for bootstrap as §3.1 already has for daily.
- Row order on page 1 is by listing time, not by id: ids 313067, 313139, 312928, 313074, 312819, 312885 etc. sit between higher ids [measured]. Newsfile ids are not monotonic with listing time; the harvest orders by listing time.
- Body 313191: begins with the dateline paragraph, ends with the `To view the source version…` line; contact e-mail `info@panoro.com` arrived unmasked (no EMAIL_MASKED on newsfilecorp.com for this release) [measured]. Body ≈ 22.3 k chars, 102 paragraphs + 1 table (11 rows incl. header) written as `<pre>` [measured].
- The release references Figures 1–4 (drill-hole location map, cross-sections, long section); these are images on the source page and carry no text that the fetch layer returned, so nothing was written for them [measured]. The line `WEB PHONE: Click Here` is the link text of a dial-in link; the link target is not preserved (markup removed per §4.3) [measured].
- Fetch-tool timing: page 1 listing fetched at 12:17 Kyiv = 05:17 ET, before the US business day; no Sep 7 rows existed yet [measured].
- All 2 HTML files parse with Python's html.parser without error [measured].
