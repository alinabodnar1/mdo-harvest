# harvest-result-2026-09-08-accessnewswire

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-08 / accessnewswire / daily / — / —
Started / Finished (Kyiv): 11:19 / 11:29
Status: COMPLETE
Pages fetched: 2
Rows total / new / seen: 40 / 5 / 3 (plus 32 rows older than the state floor 2026-09-04 — not harvested, see Notes)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 5 / 0 / 0 / 2 / 5 (markers overlap; every item was written)
Listing pages rebuilt: 1 pages, 8 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 11:20 | 20 | September 8, 2026 3:05 AM — Battery X Metals to Appoint Accomplished Technology and Consumer Brands Executive Nicholas Reichenbach to Board of Directors | September 2, 2026 9:00 AM — Emerging Growth Research Issues Press Release Announcing New Flash Report on First Phosphate Corp. | 5 (rows 1–5); rows 6–8 seen; rows 9–20 pre-floor | `continuous` — last(1) Sep 2 9:00 AM = first(2) Sep 2 9:00 AM; business-hours portion 0 h |
| 2 | 11:22 | 20 | September 2, 2026 9:00 AM — Vox Royalty Enters into Binding Agreement to Acquire the White Dam Gold Royalty in Australia | September 1, 2026 2:00 AM — MKA Half Year 2026 Results | 0 (all 20 rows pre-floor, none in seen-urls) | not fetched — minimum depth (2) reached, no in-scope rows left |

Page URLs: `https://www.accessnewswire.com/newsroom/industry/metals-and-mining?page=1`, `…?page=2`

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 1217589 | September 7, 2026 11:00 AM | 2026-09-07T11:00:00-04:00 | Ecora Royalties PLC | Ecora Royalties PLC Announces Change of Registered Office Address | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/ecora-royalties-plc-announces-change-of-registered-office-address-1217589 |
| 1217878 | September 7, 2026 7:45 PM | 2026-09-07T19:45:00-04:00 | Barton Gold Holdings Limited | Tunkillia Environmental Scoping Report Approved | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/tunkillia-environmental-scoping-report-approved-1217878 |
| 1217898 | September 8, 2026 2:00 AM | 2026-09-08T02:00:00-04:00 | Guardian Metal Resources plc | Guardian Metal Resources PLC Announces Admission to FTSE AIM 50 Index | EMAIL_MASKED | https://www.accessnewswire.com/newsroom/en/metals-and-mining/guardian-metal-resources-plc-announces-admission-to-ftse-aim-50-index-1217898 |
| 1217304 | September 8, 2026 3:01 AM | 2026-09-08T03:01:00-04:00 | Apex Critical Metals Corp. | Apex Expands Trinity Zone with Step-out Hole Returning 197.5 m Interval of 2.12% REO at the Rift Rare Earth Project in SE Nebraska | EMAIL_MASKED;TEXT_QUALITY | https://www.accessnewswire.com/newsroom/en/metals-and-mining/apex-expands-trinity-zone-with-step-out-hole-returning-197.5-m-interval-of-2.12-r-1217304 |
| 1217883 | September 8, 2026 3:05 AM | 2026-09-08T03:05:00-04:00 | Battery X Metals Inc. | Battery X Metals to Appoint Accomplished Technology and Consumer Brands Executive Nicholas Reichenbach to Board of Directors | EMAIL_MASKED;TEXT_QUALITY | https://www.accessnewswire.com/newsroom/en/metals-and-mining/battery-x-metals-to-appoint-accomplished-technology-and-consumer-brands-executive-1217883 |

Body sizes [measured]: 1217589 ≈ 2.2 k chars, 1217898 ≈ 3.0 k, 1217878 ≈ 9.0 k, 1217883 ≈ 10.1 k, 1217304 ≈ 14.7 k. All five bodies begin with the dateline and end with the `SOURCE:` line.

## Body boundaries (trade-press sources only)
n/a — wire source.

## Failures, verbatim
None. No fetch returned an error or empty content.

TEXT_QUALITY details:
- 1217304 (Apex) — **Table 1** ("Drillhole Location and Attributes") arrived as five data rows without its header row (column names for hole id, length, azimuth, dip, easting, northing, elevation are not in the text). **Table 2** ("Assay Highlights") arrived as its caption and footnotes (a)/(b) only — no data rows. Most likely the assay table is an image on the source page; the fetch layer cannot see it [measured: the reader returned nothing between the Table 2 caption and footnote (a)]. Figures 1–2 and Image 1 are referenced in the text and are images — dropped, as expected. Everything else intact.
- 1217883 (Battery X) — the two quotation paragraphs (CEO Massimo Bellini Bressi; Nicholas Reichenbach) were returned **paraphrased** by the fetch tool's reader model: the quoted fragments are present in quotation marks, but the connective wording ("He added that…", "Reichenbach responded positively to his appointment, saying…") is the reader's, not the release's. A second prompt against the cached page recovered more of the quoted text than the first (the first pass had shortened both quotes to one sentence each) but still not the sentence structure of the original. The stored body uses the second, fuller version. All other paragraphs intact.

EMAIL_MASKED details: every one of the five releases carries at least one `[email protected]` literal (Ecora — RNS contact; Barton — two contact e-mails; Guardian — Tavistock, Edelman Smithfield, RNS; Apex — CEO e-mail; Battery X — CEO e-mail) [measured].

## Remaining (INCOMPLETE only)
—

## Notes
- **Prompt gap — daily stop rule after a bootstrap with SINCE.** The bootstrap on 2026-09-07 used `SINCE: 2026-09-04` and wrote only the 3 in-scope URLs to `seen-urls.txt`. Rows older than SINCE (17 on page 1 alone) were never recorded as seen. Today §3.1 daily says "stop after the first page on which every row is already in seen-urls.txt" and §4 says "for every new URL … fetch". Read literally, that would have harvested 32 pre-SINCE rows (Sep 1–3) on pages 1–2 and kept walking, since no older page can ever be all-seen [measured: page 2 had 0 seen rows]. I did not do that. I treated the oldest listing date in `index.json` (2026-09-04) as the **state floor** and harvested only rows with listing date ≥ floor, which gives the 5 releases from Sep 7–8 — what a daily run is for. Suggested fix for v8, pick one: (a) bootstrap appends **all** rows it saw, including pre-SINCE ones, to `seen-urls.txt` (cheapest — the stop rule then works as written); or (b) add a `floor-date` line to the state folder and make daily skip rows older than it. Until fixed, every daily run on every source bootstrapped with SINCE hits this.
- Timing of fetch vs. source day: page 1 fetched at 11:20 Kyiv = 04:20 ET, before the US business day. Sep 8 rows so far are all 02:00–03:05 ET (UK/Canadian issuers releasing for the London open). Today's North-American releases will appear on tomorrow's run. Same pattern as the 2026-09-07 run [measured].
- Boundary page 1 → page 2 was an exact same-minute join (both Sep 2, 2026 9:00 AM) — no gap, no overlap [measured].
- The listing date for Barton Gold (ADELAIDE) is `September 7, 2026 7:45 PM`; the dateline says September 7 too. Under the ET inference that is 09:45 Sep 8 Sydney time — plausible for an ASX morning announcement, which weakly supports the ET assumption for the listing timezone [inferred].
- The page timestamps shown on the article pages (`Monday, 07 September 2026 11:00 AM`, etc.) matched the listing time on all five [measured]; excluded from the body per §4.2.
- Fetch-layer fidelity observation [measured]: the reader model behind the fetch tool is not a copier. On this run it (1) substituted `email@example.com` for the obfuscated addresses in the Barton release on the first prompt, and returned the true `[email protected]` literal only when the prompt named that literal explicitly; (2) paraphrased quoted speech in the Battery X release on both prompts; (3) flattened the Barton contact block and project list into single `|`-joined lines on the first prompt and into proper rows on the second. Adding the sentence "Keep e-mail addresses exactly as they appear in the page text" to the article prompt (used from article 3 onward) fixed (1). For (2) there is no prompt fix I found; it is a `TEXT_QUALITY` risk on every release with long quotes. A second prompt against the same URL within 15 minutes runs on the cached page, so it costs no extra fetch — worth writing into §4.1 as the standard recovery step.
- `mirror/accessnewswire/page1.html` was overwritten in place (8 items, 1 page). Deletion is not permitted in the connected folder, so if a future run needs fewer pages than the previous one, the surplus `pageN.html` would remain; today that did not arise (1 page before, 1 page after) [measured].
- State after run: `seen-urls.txt` 8 URLs, `index.json` 8 records, `articles/` 8 files; all 9 HTML files parse with Python's html.parser with balanced tags [measured]. No existing article file was rewritten.
- Duplicate-release pattern noted on 2026-09-07 (same headline under two ids) is still visible on page 1 (Arcus & Core, ids 1216082/1216088) and page 2 (Eagle Plains/Earthwise 1215224/1215271; GGL/Strategic Metals 1215047/1214967) — all pre-floor, none harvested [measured].
