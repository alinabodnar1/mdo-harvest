# harvest-result-2026-09-07-im-mining

RUN_DATE / SOURCE / MODE / SINCE / RESUME_FROM: 2026-09-07 / im-mining / bootstrap / 2026-09-04 / —
Started / Finished (Kyiv): 15:56 / 16:01
Status: COMPLETE
Pages fetched: 2 (`/news/page/1/`, `/news/page/2/`; month-archive fallback not needed)
Rows total / new / seen: 24 / 5 (listing date ≥ SINCE) / 0 — no prior state for this source; 19 rows dated ≤ 2026-09-03 were outside SINCE and not fetched
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED: 5 / 0 / 0 / 0 / 0
Listing pages rebuilt: 1 page, 5 items

## Walk
| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 15:56 | 12 | 2026/09/07 — Voith launches PowerDrive Mining electrified conveyor drive system | 2026/09/03 — ABB to provide switchgear for LKAB sorting plant in Malmberget | 5 (rows 1–5; rows 6–12 dated 09/03 < SINCE) | continuous (last(1) 09/03 → first(2) 09/03, same date) |
| 2 | 15:56 | 12 | 2026/09/03 — Caterpillar, FieldAI to advance AI-powered industrial innovation | 2026/09/01 — Metso signs agreement for concentrator plant delivery to GTK Mintec's new pilot plant in Outokumpu | 0 (all < SINCE) | — (stop: page 1 oldest row already < SINCE; page 2 fetched for minimum depth) |

## Items harvested this run
| id | listing date (raw) | date (ISO) | issuer | title | marker | original URL |
|---|---|---|---|---|---|---|
| 20260904-normet-opens-technology-centre-to-accelerate-the-future-of-u | 2026/09/04 (url) | 2026-09-04T00:00:00+01:00 | Not disclosed | Normet opens technology centre to accelerate the future of underground mining | none | https://im-mining.com/2026/09/04/normet-opens-technology-centre-to-accelerate-the-future-of-underground-mining/ |
| 20260904-hyva-looks-to-scale-digital-tipping-solutions-for-autonomous | 2026/09/04 (url) | 2026-09-04T00:00:00+01:00 | Not disclosed | Hyva looks to scale digital tipping solutions for autonomous mining trucks after success with XCMG at Yimin | none | https://im-mining.com/2026/09/04/hyva-looks-to-scale-digital-tipping-solutions-for-autonomous-mining-trucks-after-success-with-xcmg-at-yimin/ |
| 20260907-metso-to-deliver-first-commercial-scale-dri-smelting-furnace | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Metso to deliver first commercial-scale DRI Smelting Furnace plant to Eti Bakir | none | https://im-mining.com/2026/09/07/metso-to-deliver-first-commercial-scale-dri-smelting-furnace-plant-to-eti-bakir/ |
| 20260907-bhp-awards-worley-contracts-for-copper-south-australia-proje | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | BHP awards Worley contracts for Copper South Australia projects | none | https://im-mining.com/2026/09/07/bhp-awards-worley-contracts-for-copper-south-australia-projects/ |
| 20260907-voith-launches-powerdrive-mining-electrified-conveyor-drive- | 2026/09/07 (url) | 2026-09-07T00:00:00+01:00 | Not disclosed | Voith launches PowerDrive Mining electrified conveyor drive system | none | https://im-mining.com/2026/09/07/voith-launches-powerdrive-mining-electrified-conveyor-drive-system/ |

## Failures, verbatim
none

## Remaining (INCOMPLETE only)
—

## Notes
- [measured] Article pages show only a date ("Posted on 4 Sep 2026" / "7 Sep 2026"), no time of day. All five `date` values therefore carry `T00:00:00+01:00` per §1.1 rule 2. Listing rows also show a date only.
- [measured] No im-mining rows dated 2026-09-05 or 2026-09-06 (Sat/Sun) on either page. Page 1 goes 09/07 (3 rows) → 09/04 (2 rows) → 09/03 (7 rows). Consistent with a weekday-only publisher, not a gap.
- [measured] `/news/page/N/` returned normal listing pages both times; the month-archive fallback was not exercised.
- [measured] The 60-character slug cut in §1.1 rule 1 produces ids ending in a bare hyphen or a cut word (e.g. `…conveyor-drive-`, `…future-of-u`). Filenames are valid and unique in this run, but a trailing `-` is untidy for URLs; consider "cut at 60 then trim to the last full `-` segment" in v6.
- [measured] The fetch tool's phrasing from §4 step 1 worked on all five im-mining pages; no copyright refusal. Article bodies contain no e-mail addresses, so `EMAIL_MASKED` did not occur.
- [measured] Article 1 (Voith) contains U+2011 non-breaking hyphens ("cost‑attractive", "low‑risk") as delivered by the fetch layer; kept as received.
- Not asked for: the 19 rows dated 09/01–09/03 on pages 1–2 are not in `seen-urls.txt` (only fetched articles are recorded, per §2). A later bootstrap with an earlier SINCE would pick them up.
