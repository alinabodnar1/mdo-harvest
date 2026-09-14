# harvest-result-2026-09-11-businesswire

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-11 / businesswire / daily / yesterday / — / —
Started / Finished (Kyiv): 15:33 / 15:42
Status: COMPLETE
Pages fetched: 2 (minimum depth; nocache=2026091115, identical on both pages)
Rows total / new / seen: 20 / 2 (dated 2026-09-10) / 3 (already seen, adopted from an interrupted earlier run — see Notes) — plus 2 rows dated RUN_DATE not recorded (v11 §3.1) and 13 rows older than the window, recorded `# skipped`
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 2 / 0 / 0 / 1 / 0 / 0
Listing pages rebuilt: 1 page, 8 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 15:34 | 10 | Sep 11, 2026 at 6:57 AM — Northisle Announces Selection of the North Island Project for the 2026 Canada Investment Summit Dealbook | Sep 9, 2026 at 4:09 PM — Cyclic Materials Opens America's First Commercial-Scale Facility Delivering Automated Rare Earth Magnet Recovery | 2 new (rows 6–7, dated Sep 10) / 3 seen (rows 3–5, adopted) / 2 RUN_DATE not recorded (rows 1–2) / 3 pre-window skipped (rows 8–10) | continuous — Sep 9 4:09 PM → Sep 9 2:21 PM; business-hours portion 1 h 48 min |
| 2 | 15:35 | 10 | Sep 9, 2026 at 2:21 PM — Westwin Elements CEO KaLeigh Long to Speak at Critical Minerals Expo North America | Sep 8, 2026 at 8:00 AM — Aris Mining Begins Construction of the Puruni Bridge in Guyana | 0 new / 0 seen / 10 pre-window skipped | — (walk ended: page 1's oldest row was already before RUN_DATE−1; minimum depth of 2 reached) |

Page URLs: `https://www.businesswire.com/newsroom/industry/natural/mining-minerals?page=1&nocache=2026091115`, `…?page=2&nocache=2026091115`.

Stop rule: page 1's oldest row (Sep 9, 4:09 PM) was already older than RUN_DATE−1 (Sep 10, 2026); the walk continued only to the minimum depth of 2 pages, per §3.1, and stopped there.

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260910784333 | Sep 10, 2026 at 8:00 AM | 2026-09-10T08:00:00-04:00 | IMC Rare Earths Ltd | IMC Rare Earths Reports High-Grade Terbium Recoveries of Up to 95.2% at Itarantim Project | TEXT_QUALITY | https://www.businesswire.com/news/home/20260910784333/en/IMC-Rare-Earths-Reports-High-Grade-Terbium-Recoveries-of-Up-to-95.2-at-Itarantim-Project |
| 20260910160735 | Sep 10, 2026 at 3:15 AM | 2026-09-10T03:15:00-04:00 | E3 Lithium Ltd. | E3 Lithium's Clearwater Project Selected for the Canada Investment Summit Prospectus; Company Establishes Strategic Advisory Group | none | https://www.businesswire.com/news/home/20260910160735/en/E3-Lithiums-Clearwater-Project-Selected-for-the-Canada-Investment-Summit-Prospectus-Company-Establishes-Strategic-Advisory-Group |

Also adopted this run — fetched by an earlier, interrupted session on 2026-09-11; not refetched or rewritten, per §2.0:

| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260910857916 | Sep 10, 2026 at 6:07 PM | 2026-09-10T18:07:00-04:00 | ESAB Corporation | ESAB Corporation Board Declares Dividend | none | https://www.businesswire.com/news/home/20260910857916/en/ESAB-Corporation-Board-Declares-Dividend |
| 20260910722665 | Sep 10, 2026 at 4:15 PM | 2026-09-10T16:15:00-04:00 | Compass Minerals International, Inc. | Compass Minerals Comments on Salt Exclusion from Section 338 Tariffs | none | https://www.businesswire.com/news/home/20260910722665/en/Compass-Minerals-Comments-on-Salt-Exclusion-from-Section-338-Tariffs |
| 20260910599304 | Sep 10, 2026 at 1:41 PM | 2026-09-10T13:41:00-04:00 | ERI | ERI's John Shegerian Shares Insights on Rare Earth Element Recovery at Texas A&M Frontiers in Research Summit | none | https://www.businesswire.com/news/home/20260910599304/en/ERIs-John-Shegerian-Shares-Insights-on-Rare-Earth-Element-Recovery-at-Texas-AM-Frontiers-in-Research-Summit |

## Body boundaries (all sources from v9)
n/a — wire source. For reference on the two newly-written articles:

| id | first 80 chars of body | dateline is paragraph # | last 80 chars of body |
|---|---|---|---|
| 20260910784333 | "Testwork demonstrates exceptionally strong rare earth deposits, prime condit…" | 2 | "…Email: info@imcrareearths.com" |
| 20260910160735 | "E3's Clearwater Project is part of Canada Investment Summit's Prospectus aim…" | 2 | "…communications@e3lithium.ca / 587-324-2775" |

## Failures, verbatim
None.

## Remaining (INCOMPLETE only)
—

## Tool use outside fetch/browser
none

## Notes
- **Recovered an interrupted prior run.** At the start of this run, `harvest-state/businesswire/run-in-progress.json` did **not** exist, but `mirror/businesswire/articles/` already contained three files dated 2026-09-10 (`20260910599304.html`, `20260910722665.html`, `20260910857916.html`) carrying `harvest-run` meta `2026-09-11` and file mtimes of 12:31 Kyiv today — evidence of a run that started earlier today, fetched a partial batch, and died before its `index.json`/`seen-urls.txt` update (and apparently before, or without, its `run-in-progress.json` marker surviving). [measured] I checked each file for a well-formed close (proper closing tags, intact contact block, plausible paragraph count) before adopting it. Per §2.0 I did not refetch or rewrite them; I added their records to `index.json` and their URLs to `seen-urls.txt` from their own `<meta>` tags, then continued the run. Process note: since the marker itself did not survive, recovery here relied on comparing article-file mtimes against the state files rather than on the marker's presence — worth hardening (flush the marker before the first fetch, and/or have recovery also trigger off "articles newer than the last successful run's Finished time that are absent from index.json").
- [measured] `nocache=2026091115` served fresh content: page 1 opened with two 2026-09-11-dated releases (Northisle, Nano One). Per v11's §3.1 fix, these were left **unrecorded** in `seen-urls.txt` — they are tomorrow's `WINDOW: yesterday` window and will be picked up against the live listing then, not a cached copy.
- [measured] Exactly two releases fell inside this run's window (RUN_DATE−1 = 2026-09-10): IMC Rare Earths (8:00 AM ET) and E3 Lithium (3:15 AM ET). Both fetched fresh, contact/boilerplate blocks intact, no truncation.
- [measured] IMC Rare Earths body contains a data table ("Recoveries across the four principal magnet rare earth elements…"). The two-pass check (§4 step 1a) returned identical element/percentage values both times — only header casing differed ("MREO ELEMENT" vs "Element"). Table written as a `<pre>` block using the first-pass wording; not `TABLE_UNVERIFIED`.
- [measured] IMC Rare Earths has two quotes longer than one sentence (§4 step 1b). The Alexandre Rocha da Rocha quote differed materially between passes: pass 1 merged/truncated it to `"These are exceptional testwork results. In my view, Itarantim stands as a global leader"`, dropping "in scale and quality" and an entire closing sentence; pass 2 returned the full three-sentence quote. I used the longer, pass-2 version and set `TEXT_QUALITY`, reason "quote wording differs between passes." The second Scolaro quote ("IMC's strengths are the richness of our deposits…") matched exactly between passes — no correction needed there.
- [measured] E3 Lithium's one long quote (Chris Doornbos, four sentences) matched exactly between pass 1 and pass 2 — no `TEXT_QUALITY` on that article.
- No `EMAIL_MASKED` on either new businesswire.com article today, consistent with 7–8 Sep 2026: `info@imcrareearths.com`, `investor@e3lithium.ca`, `communications@e3lithium.ca` all arrived in clear.
- Both new articles carry a one-line sub-headline above the dateline (IMC: "Testwork demonstrates exceptionally strong rare earth deposits…"; E3: "E3's Clearwater Project is part of Canada Investment Summit's Prospectus…"), captured as body paragraph 1 per §4 step 2. Neither had a HIGHLIGHTS bullet block.
- `issuer`: IMC Rare Earths taken as the company named in the dateline sentence ("IMC Rare Earths Ltd"). E3 Lithium's dateline reads "E3 LITHIUM LTD." in caps; normalized to "E3 Lithium Ltd." to match the company's own later self-reference in the boilerplate ("E3 Lithium Ltd."), the same normalization convention used for ASA Gold and Precious Metals Limited on 2026-09-07.
- Boundary 1→2 (Sep 9, 4:09 PM → Sep 9, 2:21 PM, both Tuesday): `continuous`, 1 h 48 min of business time — well under the 3 h threshold.
- 13 `# skipped <listing date>` rows appended this run (3 from page 1, 10 from page 2), all older than RUN_DATE−1. 2 rows dated RUN_DATE (2026-09-11) were seen on page 1 but, per the v11 fix to §3.1, deliberately **not** written to `seen-urls.txt`.
- State after run: `seen-urls.txt` 21 lines (8 harvested/adopted URLs + 13 skipped), `index.json` 8 records, `articles/` 8 files, `page1.html` rebuilt (1 of 1, 8 items, run 2026-09-11).
