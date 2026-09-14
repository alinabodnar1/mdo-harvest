# harvest-result-2026-09-12-businesswire

RUN_DATE / SOURCE / MODE / WINDOW / SINCE / RESUME_FROM: 2026-09-12 / businesswire / daily / yesterday / n/a / n/a
Started / Finished (Kyiv): 2026-09-12 08:43 / 2026-09-12 08:52
Status: CONTINUITY_GAP
Pages fetched: 2
Rows total / new / seen: 20 / 3 / 17
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 3 / 0 / 0 / 1 / 0 / 0
Listing pages rebuilt: 1 page, 11 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 2026-09-12 08:44 | 10 | Sep 11, 2026 at 9:09 AM — Masan High-Tech Materials: How a Vietnamese Company Is Building a Role in Global Strategic Materials Supply Chains | Sep 9, 2026 at 8:30 PM — Nyangumarta Warrarn Aboriginal Corporation and Rio Tinto sign milestone agreement for Winu Project | 3 | gap (3h51m business-hours portion, Sep 9 16:09→20:30 ET) |
| 2 | 2026-09-12 08:45 | 10 | Sep 9, 2026 at 4:09 PM — Cyclic Materials Opens America's First Commercial-Scale Facility Delivering Automated Rare Earth Magnet Recovery | Sep 8, 2026 at 8:00 AM — GrafTech Announces Graphite Electrode Price Increase | 0 | n/a — walk stopped (min depth 2 reached, WINDOW:yesterday stop condition already met on page 1) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260910612111 | Sep 11, 2026 at 9:09 AM | 2026-09-11T09:09:00-04:00 | Masan High-Tech Materials | Masan High-Tech Materials: How a Vietnamese Company Is Building a Role in Global Strategic Materials Supply Chains | TEXT_QUALITY | https://www.businesswire.com/news/home/20260910612111/en/Masan-High-Tech-Materials-How-a-Vietnamese-Company-Is-Building-a-Role-in-Global-Strategic-Materials-Supply-Chains |
| 20260911613545 | Sep 11, 2026 at 6:57 AM | 2026-09-11T06:57:00-04:00 | Northisle Copper and Gold Inc. | Northisle Announces Selection of the North Island Project for the 2026 Canada Investment Summit Dealbook | none | https://www.businesswire.com/news/home/20260911613545/en/Northisle-Announces-Selection-of-the-North-Island-Project-for-the-2026-Canada-Investment-Summit-Dealbook |
| 20260911712077 | Sep 11, 2026 at 3:05 AM | 2026-09-11T03:05:00-04:00 | Nano One Materials Corp. | Nano One Advances Development Company Project to Build LFP Cathode Production in Canada | none | https://www.businesswire.com/news/home/20260911712077/en/Nano-One-Advances-Development-Company-Project-to-Build-LFP-Cathode-Production-in-Canada |

## Body boundaries (all sources from v9)
| id | first 80 chars of body | dateline paragraph # | last 80 chars of body |
|---|---|---|---|
| 20260910612111 | "As global strategic-minerals supply chains are reshaped, competitive advantage i" | n/a — no dateline sentence on the page (see TEXT_QUALITY) | " a Vietnam-based strategic materials platform connected to global supply chains." |
| 20260911613545 | "VANCOUVER, British Columbia--(BUSINESS WIRE)--Northisle Copper and Gold Inc. (TS" | 1 | "www.northisle.ca" |
| 20260911712077 | "Highlights" | 6 (Highlights heading + 4 bullets precede it) | "+1 (604) 420-2041" |

## Failures, verbatim
none

## Remaining (INCOMPLETE only)
n/a — run status is CONTINUITY_GAP, not INCOMPLETE; nothing left to fetch.

## Tool use outside fetch/browser
none

## Notes

No `harvest-state/businesswire/run-marker.json` existed before this run — this is the first run for this source under the v11+ marker regime (businesswire's index.json/seen-urls.txt predate it). The §3.2b freshness check therefore had no prior `top_row` to compare against; today's page-1 top row (Masan High-Tech Materials, Sep 11 2026 9:09 AM) has been stored in the marker for the next run to compare against.

Continuity check (§3.3) between page 1 and page 2: last row of page 1 (Sep 9, 2026 8:30 PM) to first row of page 2 (Sep 9, 2026 4:09 PM) — both on a Wednesday. Business-hours portion of the interval (clipped to 07:00–20:00) = 3h51m, 51 minutes over the ≤3h "continuous" threshold, so this run is marked CONTINUITY_GAP. The stop rule alone (WINDOW: yesterday) already required only page 1 (its oldest row is before RUN_DATE−1); the gap rule's "one more page than the stop rule required" is page 2, which coincides with businesswire's minimum walk depth (2 pages) already fetched — so no 3rd page was added. All 10 rows on page 2, and the 7 rows on page 1 dated Sep 10 or earlier, were already in `seen-urls.txt`/`index.json` from the 2026-09-11 run, so the gap had no effect on what was harvested; flagging it here only for the record per §3.3.

0 URLs were newly appended to `seen-urls.txt` with the `# skipped` suffix this run — every row on both pages older than Sep 11, 2026 was already recorded (harvested or skipped) in a prior run.

Masan High-Tech Materials (id 20260910612111): the page has no dateline sentence ("CITY, State--(BUSINESS WIRE)--...") and no contact block at the end — it reads as sponsored/analysis copy (BusinessWire "BrandView"-style native content) rather than a standard issuer press release. `issuer` was set from the headline/body ("Masan High-Tech Materials") rather than from a dateline sentence, and `dateline` was set to "Not disclosed" for lack of one, even though this is not a trade-press source. Flagged TEXT_QUALITY so a reviewer can decide how (or whether) to treat this item downstream — this prompt applies no news-type judgment itself.

nocache value used: 2026091208 (RUN_DATE digits + Kyiv hour 08, per §1).
