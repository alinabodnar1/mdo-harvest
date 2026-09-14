# harvest-result-2026-09-08-im-mining

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-08 / im-mining / daily / — / —
Started / Finished (Kyiv): 08:42 / 08:51
Status: CONTINUITY_GAP
Pages fetched: 3 (`/news/page/1/`, `/news/page/2/`, `/news/page/3/`) + 1 diagnostic fetch of the month archive `/2026/09/page/2/` (see Notes; no rows taken from it)
Rows total / new / seen: 36 (12 + 12 + 12; 9 of them duplicates across pages 2–3 → 27 unique URLs) / 9 / 3 in `seen-urls.txt` + 15 unique rows dated 2026-09-01…09-03, older than the bootstrap SINCE (2026-09-04) and never harvested — treated as pre-window, not fetched (see Notes)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 9 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 page, 14 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 08:42 | 12 | 2026/09/08 — Viridis orders large pressure filter from Dewater for Colossus rare earths project in Brazil | 2026/09/07 — Metso to deliver first commercial-scale DRI Smelting Furnace plant to Eti Bakir | 9 (rows 1–9; rows 10–12 seen) | **gap** — last(1) 2026/09/07 (Mon) → first(2) 2026/09/03 (Thu); weekday 2026/09/04 (Fri) skipped. The two 09/04 articles harvested yesterday (Normet, Hyva) appear on neither page → fetched one more page per §3.3 |
| 2 | 08:42 | 12 | 2026/09/03 — Caterpillar, FieldAI to advance AI-powered industrial innovation | 2026/09/01 — Metso signs agreement for concentrator plant delivery to GTK Mintec's new pilot plant in Outokumpu | 0 (0 seen; 12 pre-window) | **overlap** — first(3) = row 4 of page 2 (page 3 shifted by 3, not 12) |
| 3 | 08:43 | 12 | 2026/09/02 — What should an exploration algorithm do with an assay that never existed? | 2026/09/01 — Royal Tyres-Ascenso partnership to bring new radial OTR tyres to southern Africa market | 0 (0 seen; 9 repeats of page 2 + 3 pre-window) | — (stop: extra page fetched for the gap; all rows pre-window) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260907-redpath-equips-shafts-at-northam-platinums-zondereinde | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Redpath equips shafts at Northam Platinum's Zondereinde Western Expansion Project | none | https://im-mining.com/2026/09/07/redpath-equips-shafts-at-northam-platinums-zondereinde-western-expansion-project/ |
| 20260907-kal-tire-mining-tire-groups-maple-program-achieves-iso | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Kal Tire Mining Tire Group's Maple Program achieves ISO verification | none | https://im-mining.com/2026/09/07/kal-tire-mining-tire-groups-maple-program-achieves-iso-verification/ |
| 20260907-tonly-showcases-dte95-battery-electric-mining-truck-at | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Tonly showcases DTE95 battery electric mining truck at Steinexpo | none | https://im-mining.com/2026/09/07/tonly-showcases-dte95-battery-electric-mining-truck-at-steinexpo/ |
| 20260907-barloworld-signs-distribution-deal-with-hermann-paus | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Barloworld signs distribution deal with Hermann Paus Maschinenfabrik | none | https://im-mining.com/2026/09/07/barloworld-signs-distribution-deal-with-hermann-paus-maschinenfabrik/ |
| 20260907-frost-sullivan-report-cites-leading-lgmg-position-in-wide | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Frost & Sullivan report cites leading LGMG position in wide body trucks | none | https://im-mining.com/2026/09/07/frost-sullivan-report-cites-leading-lgmg-position-in-wide-body-trucks/ |
| 20260907-zijin-mining-backs-weir-to-deliver-highly-efficient | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Zijin Mining backs Weir to deliver highly efficient, sustainable grinding solution | none | https://im-mining.com/2026/09/07/zijin-mining-backs-weir-to-deliver-highly-efficient-sustainable-grinding-solution/ |
| 20260908-ferreyros-delivers-the-1000th-caterpillar-mining-truck-in | 2026/09/08 (url) | 2026-09-08T00:00:00+01:00 | Not disclosed | Ferreyros delivers the 1,000th Caterpillar mining truck in Peru | none | https://im-mining.com/2026/09/08/ferreyros-delivers-the-1000th-caterpillar-mining-truck-in-peru/ |
| 20260908-metso-to-deliver-comprehensive-copper-iron-ore-processing | 2026/09/08 (url) | 2026-09-08T00:00:00+01:00 | Not disclosed | Metso to deliver 'comprehensive' copper, iron ore processing solution for Viscaria copper mine restart | none | https://im-mining.com/2026/09/08/metso-to-deliver-comprehensive-copper-iron-ore-processing-solution-for-viscaria-copper-mine-restart/ |
| 20260908-viridis-orders-large-pressure-filter-from-dewater-for | 2026/09/08 (url) | 2026-09-08T00:00:00+01:00 | Not disclosed | Viridis orders large pressure filter from Dewater for Colossus rare earths project in Brazil | none | https://im-mining.com/2026/09/08/viridis-orders-large-pressure-filter-from-dewater-for-colossus-rare-earths-project-in-brazil/ |

## Body boundaries (trade-press sources only)
| id | first 80 chars of body | last 80 chars of body |
|---|---|---|
| 20260907-redpath-equips-shafts-at-northam-platinums-zondereinde | Redpath Africa Limited has completed its component of Northam Platinum's Zondere | to ensuring the successful execution and completion of projects of this nature." |
| 20260907-kal-tire-mining-tire-groups-maple-program-achieves-iso | Kal Tire's Mining Tire Group has achieved independent ISO verification for the c | educe waste and improve the environmental performance of their tyre operations." |
| 20260907-tonly-showcases-dte95-battery-electric-mining-truck-at | In recent years, Xi'an-based Tonly Heavy Industries has continued its globalisat | ements of its trucks to different countries and different types of mining areas. |
| 20260907-barloworld-signs-distribution-deal-with-hermann-paus | Today, at Electra Mining Africa 2026 in Nasrec, Johannesburg, Barloworld signed  | ters, concrete sprayers and mixers, fire fighting trucks and mine rescue trucks. |
| 20260907-frost-sullivan-report-cites-leading-lgmg-position-in-wide | Frost & Sullivan, the global consulting firm, recently completed a specialised m | reliability-focused to continuously create value for the global mining industry. |
| 20260907-zijin-mining-backs-weir-to-deliver-highly-efficient | Weir, the mining technology company, has been awarded an order to supply two END | to being where our customers are so that we can support them when they need it." |
| 20260908-ferreyros-delivers-the-1000th-caterpillar-mining-truck-in | Ferreyros, a leader in heavy machinery, has delivered to Compañía Minera Antamin | onitoring centres and laboratories; and a team committed to world-class service. |
| 20260908-metso-to-deliver-comprehensive-copper-iron-ore-processing | Metso and Gruvaktiebolaget Viscaria have signed an agreement for the delivery of | ment to be delivered to the processing plant is part of the Metso Plus offering. |
| 20260908-viridis-orders-large-pressure-filter-from-dewater-for | Viridis Mining and Minerals Ltd has announced the placement of its first major e |  have established with the local community and municipal and State governments." |

## Failures, verbatim
none

## Remaining (INCOMPLETE only)
—

## Notes
- [measured] **Stale listing cache on `/news/page/2/`.** Page 1 gained 9 rows since yesterday's run (3 × 09/08, 6 × 09/07), yet page 2 is byte-for-byte the same row set as yesterday (Caterpillar/FieldAI 09/03 → Metso/GTK Mintec 09/01). A fresh page 2 would have to begin with yesterday's page-1 row 4 (Normet, 09/04). Page 3, fetched for the gap, begins at page-2 row 4 (offset 3 = 12 − 9), i.e. page 3 is fresh and page 2 is not. Net effect: the 2 × 09/04 rows (already harvested 7 Sep) and 7 × 09/03 rows (pre-window) are invisible in this run's listing. Nothing in the harvest window (≥ 09/04) is known to be lost, but 09/07 rows beyond the 9 on page 1 cannot be ruled out until page 2 refreshes. Recommend: re-walk `/news/page/2/` on tomorrow's run and compare.
- [measured] Diagnostic fetch of the month archive `https://im-mining.com/2026/09/page/2/` (permitted fallback URL, §1) returned yet another offset — 11 rows, starting at Tailings 2026 (page-2 row 3) — so it is also a cached copy, from a different moment. The two WordPress archives are served from independent caches; the month archive is not a reliable cross-check for the news archive on the same day.
- [measured] **Stop rule in daily mode does not terminate on this source.** §3.1 stops "after the first page on which every row is already in `seen-urls.txt`". Rows older than the bootstrap SINCE were never written to `seen-urls.txt` (§2 records only fetched URLs), so pages 2 and 3 contain 0 seen rows and the literal rule would walk to the end of the archive. This run treated rows dated before the bootstrap SINCE (2026-09-04) as "pre-window" and stopped at the §3.3 gap depth. Two ways to close the gap in v8: (a) bootstrap writes every *listed* URL (not only fetched ones) to `seen-urls.txt`, or a separate `skipped-urls.txt`; or (b) the daily stop rule reads "every row is seen **or older than the oldest date in `index.json`**". Option (a) is cleaner for the dedup key. The same hole exists for the four wire sources.
- [measured] The §1.1 rule 1 id trim (cut at 60, then drop the trailing partial segment) worked on all 9 ids; none ends in a hyphen or a cut word. The 5 ids from 7 Sep keep their old form per the same rule.
- [measured] Redpath article: the four "principal work packages" arrived from the fetch layer as a single paragraph with items joined by `;` and `and` (likely a `<ul>` flattened by the reader). No text is missing; paragraph structure inside that block may differ from the original. Not marked — the release text is intact and no chrome leaked.
- [measured] Article pages show a date only ("Posted on 7 Sep 2026" / "8 Sep 2026"), no time; all `date` values carry `T00:00:00+01:00` per §1.1 rule 2. Consistent with the 7 Sep run.
- [measured] The §4 step 1 phrasing produced no copyright refusal on any of the 9 article fetches or the 4 listing fetches. No e-mail addresses in any body; `EMAIL_MASKED` did not occur.
- [measured] Source characters kept as received: `®`, `™`, `CO₂`, `€`, `km²`, `ŚGP`, `Jaźwica`, `Compañía`, `Emsbüren`, en-dashes. Fetch times: 4 listing pages 08:42–08:43, 9 articles 08:44–08:49, ≥ 2 s between requests.
- [measured] Rows 1–9 of page 1 are all 09/07–09/08 supplier/OEM stories (Redpath, Kal Tire, Tonly, Barloworld, LGMG, Weir, Ferreyros/Cat, Metso, Dewater). No news-type judgement was applied; noted only because it shows this source's daily volume (≈ 9 new articles per weekday, so far) is within one batch.
