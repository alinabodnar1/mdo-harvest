# harvest-result-2026-09-08-businesswire

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-08 / businesswire / daily / — / —
Started / Finished (Kyiv): 11:35 / 11:40
Status: COMPLETE
Pages fetched: 2 (minimum depth; nocache=2026090811, identical on both pages)
Rows total / new / seen: 20 / 1 (≥ state floor 2026-09-04) / 2 (plus 17 rows older than the state floor — not harvested, see Notes)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 1 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 page, 3 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 11:35 | 10 | Sep 7, 2026 at 8:00 PM — Ngarlawangga Aboriginal Corporation and Rio Tinto sign Interim Modernised Agreement | Sep 3, 2026 at 7:30 AM — LibertyStream Signs Term Sheet for Up to US$95 Million in Project Financing | 1 new (row 1) / 2 seen (rows 2–3) / 7 pre-floor (Sep 3) | continuous — Sep 3 7:30 AM → Sep 3 2:00 AM; business-hours portion 0 h 30 min (07:00–07:30 ET) |
| 2 | 11:36 | 10 | Sep 3, 2026 at 2:00 AM — Komatsu and Atlassian Williams F1 Team Renew Award-Winning Global Partnership with Expanded Technical Collaboration | Sep 1, 2026 at 7:03 AM — Silver Bow Mining Intersects 994.2 g/t AgEq Over 4.0 m, including 1,586.1 g/t AgEq Over 2.3 m, from the Rainbow Block in Butte, Montana | 0 new / 0 seen / 10 pre-floor (Sep 1–3) | — (walk ended at minimum depth; "Next" link present) |

Page URLs: `https://www.businesswire.com/newsroom/industry/natural/mining-minerals?page=1&nocache=2026090811`, `…?page=2&nocache=2026090811`.

Stop rule: no row on page 2 is newer than the state floor; minimum depth 2 reached; walk stopped (same convention as the 2026-09-08 newsfile and accessnewswire runs — see Notes).

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260907004218 | Sep 7, 2026 at 8:00 PM | 2026-09-07T20:00:00-04:00 | Rio Tinto | Ngarlawangga Aboriginal Corporation and Rio Tinto sign Interim Modernised Agreement | none | https://www.businesswire.com/news/home/20260907004218/en/Ngarlawangga-Aboriginal-Corporation-and-Rio-Tinto-sign-Interim-Modernised-Agreement |

## Body boundaries (trade-press sources only)
n/a — wire source.

## Failures, verbatim
None.

## Remaining (INCOMPLETE only)
—

## Notes
- **State-floor convention applied (same as newsfile/accessnewswire today).** `seen-urls.txt` held only the 2 URLs the 2026-09-07 bootstrap (SINCE 2026-09-04) took in scope; the 17 rows dated Sep 1–3 on pages 1–2 are therefore "not in seen-urls" but were excluded on purpose. Read literally, §3.1/§4 would harvest them and the daily stop rule could never fire (page 2 had 0 seen rows) [measured]. I harvested only rows with listing date ≥ 2026-09-04 (the oldest date in `index.json`) and stopped at the minimum depth. The pre-floor URLs were **not** added to `seen-urls.txt`; they will show as "not seen" again tomorrow until v8 fixes this (bootstrap should record every listed URL, or the state folder should carry a floor date).
- [measured] `nocache=2026090811` served fresh content: page 1 row 1 is Sep 7, 2026 8:00 PM, a row that did not exist in yesterday's 13:16 fetch. Rows 2–10 of page 1 and all of page 2 are identical, row for row, to yesterday's pages 1–2 shifted by one — Business Wire had exactly one new mining-minerals release between the two runs (Sep 7 was Labor Day in the US).
- [measured] Boundary 1→2 today (Sep 3 7:30 AM → Sep 3 2:00 AM) was `continuous` with 30 min of business time; yesterday the same rows sat on either side of a different boundary (Sep 3 2:00 AM → Sep 2 9:38 PM) and read as a "gap". The boundary position moved by one row because of the one new release, which is the expected behaviour; the previous "gap" was the overnight lull, not missing rows (see 2026-09-07 note on an overnight allowance).
- [measured] Fetch at 11:35 Kyiv = 04:35 ET, before the US business day; today's North-American releases will appear in tomorrow's run.
- [measured] Article page shows the date only ("September 7, 2026"), no time; `date` uses the listing time 8:00 PM ET as §5.1 requires. The dateline is KARRATHA, Australia — 8:00 PM ET Sep 7 is 08:00 AWST Sep 8, i.e. a Perth-morning release, consistent with the ET inference for listing times [inferred].
- `issuer`: the dateline sentence names two parties (Ngarlawangga Aboriginal Corporation and Rio Tinto); the contact block, addresses and registration numbers are Rio Tinto's, so `issuer` = "Rio Tinto". Flagging this because the spec's "company name from the dateline sentence" has no rule for joint releases; the extraction stage will see both names in the text regardless.
- [measured] Body: 21 paragraphs from the dateline through "Riotinto.com" at the end of the corporate address block; the contact block was returned as line-grouped blocks and written as one `<p>` per block with the line breaks kept. E-mail `media.enquiries@riotinto.com` arrived in clear — no `EMAIL_MASKED` on businesswire.com, consistent with 2026-09-07. Quotations were checked against a single pass only; the accessnewswire finding (reader model may paraphrase long quotes) applies as a residual risk, though the text reads as release prose with no signs of rewording.
- [measured] Article-extraction prompt used the §4.1 wording ("return the article body as plain text, keep all paragraphs, remove only markdown") plus "keep e-mail addresses exactly as they appear" — no refusal on the first attempt.
- Yesterday's article files carried no `layer` and `kind` meta tags (written under v6); today's file has both (`L1`, `release`). Existing files were not rewritten, per §7.
- State after run: `seen-urls.txt` 3 URLs, `index.json` 3 records, `articles/` 3 files, `page1.html` rebuilt (1 of 1, 3 items, run 2026-09-08).
