# harvest-result-2026-09-11-newsfile

RUN_DATE: 2026-09-11 / SOURCE: newsfile / MODE: daily / WINDOW: yesterday / SINCE: n/a / RESUME_FROM: n/a
Started (Kyiv): 2026-09-11 17:15 (14:15:28Z) / Finished (Kyiv): 2026-09-11 18:45 (15:45:30Z)
Status: COMPLETE
Pages fetched: 4 (mining-metals?pg=1..4)
Rows total / new / seen: 80 / 61 / 19 (6 recorded as `# skipped`, 13 already seen from an earlier same-day attempt; see Notes)
Articles fetched OK / FETCH_FAILED / TEXT_TRUNCATED / TEXT_QUALITY / EMAIL_MASKED / TABLE_UNVERIFIED: 71 / 1 / 0 / 8 / 10 / 1 (one item carries both EMAIL_MASKED and TEXT_QUALITY)
Listing pages rebuilt: 4 pages, 95 items

## Walk

| page | fetched (Kyiv) | rows | first row (date, title) | last row (date, title) | new | boundary to next |
|---|---|---|---|---|---|---|
| 1 | 2026-09-11 18:2x (confirmatory re-fetch; see Notes) | 20 | 2026-09-11 6:30 AM EDT, Adyton Resources Announces Filing of NI 43-101... | 2026-09-10 12:02 PM EDT, Registration is Now Live for CEM's 2027 Capital Event Series | 17 (3 rows dated 2026-09-11 correctly excluded, not written anywhere) | page1 ends mid-2026-09-10 |
| 2 | 2026-09-11 18:2x | 20 | 2026-09-10 10:39 AM EDT, Element One Targets Earth's Oldest Clean Energy Source... | 2026-09-10 7:30 AM EDT, Benton Discovers High-Grade Gold at the Dominion Project... | 20 | still inside 2026-09-10 |
| 3 | 2026-09-11 18:2x | 20 | 2026-09-10 7:25 AM EDT, Sranan Gold Channel Sampling Returns 39.55 g/t Gold... | 2026-09-10 6:00 AM EDT, Medaro Mining Sampling Returns up to 32.99%... | 20 | still inside 2026-09-10 |
| 4 | 2026-09-11 18:2x | 20 | 2026-09-10 6:00 AM EDT, DLP Receives Drill Permits at Esperanza... | 2026-09-09 11:32 AM EDT, CEO.CA's Inside the Boardroom: Why a Former GM Executive... | 4 (+6 skipped, +10 already seen) | oldest row on page4 (2026-09-09) predates RUN_DATE−1 → walk stopped, min depth (3) satisfied |

Note on timestamps: the walk shown above is a **confirmatory re-fetch performed after this session resumed from a context reset**, not the original walk. The original pre-reset walk's own per-page fetch timestamps were not preserved across the reset; row content and IDs match exactly what the resumed session used to complete the run, so counts above are correct, but the "fetched (Kyiv)" column reflects the re-fetch time, not the true original walk time. Flagged transparently rather than fabricating a plausible-looking earlier timestamp.

## Items harvested this run

61 items dated 2026-09-10 were newly fetched and written this run (harvest_run=2026-09-11, date=2026-09-10). Full per-item detail (id, dates, issuer, title, marker, URL) is in `harvest-state/newsfile/index.json` — reproducing all 61 rows here would just duplicate that file. Markers among this run's 61 new items:

| id | title (short) | marker |
|---|---|---|
| 313743 | Centurion Completes Limestone Gold Panning and Scouting Program... | TEXT_QUALITY |
| 313767 | Prospector Metals Reports Multiple High-Grade Gold-Silver-Copper... | EMAIL_MASKED |
| 313782 | Oroco Continues South Zone Success | EMAIL_MASKED |
| 313806 | Amex découvre une nouvelle zone aurifère... (French duplicate of 313805) | TEXT_QUALITY |

All other 57 of the 61 new items: marker `none`.

The remaining 31 items carrying `harvest_run=2026-09-11` (19 dated 2026-09-09, 12 dated 2026-09-08) were **not** fetched this run — they were already present in `index.json`/`seen-urls.txt`/`mirror/.../articles/` when this run resumed, written by an earlier same-day attempt that died before it could write a `run-marker.json` (file mtimes ~11:0x UTC on 2026-09-11, well before this run's own `started` timestamp of 14:15:28Z). This run correctly recognized them as already-seen during the listing walk and did not re-fetch or duplicate them. Markers among those orphaned items include the pre-existing FETCH_FAILED (313313), TABLE_UNVERIFIED (313547), and several TEXT_QUALITY/EMAIL_MASKED entries — see index.json for the full list.

## Body boundaries (all sources from v9)

| id | first 80 chars of body | dateline is paragraph # | last 80 chars of body |
|---|---|---|---|
| 313757 | "All required permits received – DLP has received the necessary permits an" | 8 (Highlights block precedes dateline) | "...its Regulation Services Provider ... accepts responsibility for the adequacy or accuracy of this release." |
| 313787 | "Feasibility stage Lac Knife Project to be showcased to global capital wit" | 2 (sub-headline precedes dateline) | "...Neither TSX Venture Exchange nor its Regulation Services accepts responsibility for the adequacy or accuracy of this release." |
| 313728 | "Vancouver, British Columbia--(Newsfile Corp. - September 10, 2026) - Meda" | 1 | "...https://www.newsfilecorp.com/release/313728" |
| 313782 | "Vancouver, British Columbia--(Newsfile Corp. - September 10, 2026) - Oroc" | 1 | "...Neither the TSX Venture Exchange nor its Regulation Services Provider accepts responsibility for the adequacy or accuracy of this news release." |
| 313806 | "Montréal, Québec--(Newsfile Corp. - 10 septembre 2026) - Les Mines d'Or A" | 1 | "...For the original version of this press release, visit https://www.newsfilecorp.com/release/313806 Source: Amex Gold Mining Inc." |

(Spot-checked; not every one of the 61 new items was re-verified paragraph-by-paragraph this run — see Notes on verification depth.)

## Failures, verbatim

- 313806 (Amex Perron Rosé Zone, French-language duplicate of 313805): three separate WebFetch attempts against the mandated exact prompt (one earlier in the run, two more when the article had to be re-fetched after this session's context reset) all returned an **English paraphrase/summary**, never the faithful French body. No attempt used altered/aggressive phrasing to try to force a different result — repeated identical attempts either succeed or they don't; escalating wording risks coercing the reader model rather than capturing faithfully, and is exactly the kind of workaround this run must not do. Marked `TEXT_QUALITY`; best-available (most complete) English paraphrase used as body; `meta[name=title]` uses the French listing title since the true French headline was never obtained.
- 313743 (Centurion): first-pass fetch returned a garbled quote fragment (misplaced closing quote, dropped continuation sentence). A targeted second-pass quote-verification request ("Return the paragraph(s) beginning 'We are very pleased' exactly as written.") returned the correct full quote, which was used. Marked `TEXT_QUALITY`, reason "quote wording differs between passes" per §4 step 1b.
- 313313 (pre-existing orphan, not from this run's own fetch activity): recorded as `FETCH_FAILED` in index.json.

## Remaining (INCOMPLETE only)

n/a — status is COMPLETE.

## Tool use outside fetch/browser

- `device_bash` calls to read/write `harvest-state/newsfile/{index.json,seen-urls.txt,run-marker.json}` and to build/verify `mirror/newsfile/page{1..4}.html` from `index.json` — state-file management explicitly permitted and disclosed per §7.
- `device_bash` used once to correct a schema/data defect introduced by this session during batch 5/6 (see Notes) — also state-file management, not a fetch/search.
- No web search, no browser use, no link-following inside any article body.

## Notes

Everything below is [measured] against this session's own tool output unless stated otherwise.

1. **This run started mid-flight from a resumed/reset session.** A device-bridge disconnection occurred earlier in the run; it was handled with two scheduled retry check-ins (5 min, then 30 min) and resolved when the user resumed the session and the bridge reconnected. [measured: tool errors and reconnection at the time]

2. **Orphan articles from an earlier died attempt.** 31 items in `index.json` (19 dated 2026-09-09, 12 dated 2026-09-08) carry `harvest_run: "2026-09-11"` but were written by an earlier same-day attempt that died before producing a `run-marker.json` — their file mtimes (~11:0x UTC) predate this run's own `started` timestamp (14:15:28Z) by roughly 3 hours. [measured: `ls`/`stat` on the article files vs. `run-marker.json`]. This run correctly treated them as already-seen and did not re-fetch them, but their `harvest_run` tag technically misattributes them to this run rather than the earlier one. Recommend for the spec: the harvest process should write (or preserve) a `run-marker.json` as its very first action, before any fetch, precisely so that a died attempt is distinguishable from the run that later recovers its output.

3. **Schema drift introduced and corrected within this run.** While rebuilding after the session resumed, 14 `index.json` records (batches covering ids 313776, 313777, 313782, 313805, 313807, 313739, 313761, 313802, 313728, 313806, 313757, 313785, 313787, 313794) were initially appended with a `url` field instead of the established `original_url`/`file` schema used by every other record, and 3 of them (313776, 313777, 313782) also carried an incomplete `raw_date`/`date` (missing the listing's time-of-day, e.g. `2026-09-10` instead of `2026-09-10 7:00 AM EDT`). Both were caught by comparing this run's appended records against the schema of pre-existing records, and corrected in place (index.json records rewritten to the standard schema; the corresponding 3 article `.html` files had their `<meta name="date">`/`<meta name="raw-date">` corrected to `2026-09-10T07:00:00-04:00` / `2026-09-10 7:00 AM EDT`) before this result file was written. [measured: `index.json` field diff before/after; article meta before/after]. Flagging per your standing instruction to surface gaps rather than let them ship quietly — this was a real defect in this run's own output, not a pre-existing one.

4. **Fetch-tool paraphrasing is not fully predictable.** Across this run, the same source and the same mandated prompt wording produced a faithful, complete body on most attempts but a paraphrased/summarized one on others (313743, 313806, and — per the pre-reset portion of this run — 313489 and one Medaro Mining attempt that succeeded faithfully only on a third identical retry). This run's policy was: retry the identical mandated prompt at most once or twice, never escalate to different/stronger wording, and if it still fails, mark `TEXT_QUALITY` and disclose rather than force it. This seems like the right policy, but it does mean a small, not-fully-predictable fraction of releases will need manual QA attention (313806 in this run) rather than being fully automatable as-is — relevant to your "don't automate ahead of results" principle: this failure mode is evidence the harvest step itself isn't 100% reliable yet, before any news-type judgment is layered on top.

5. **Verification depth was sampled, not exhaustive, for the bulk of this run's 61 new items.** Full two-pass table/quote verification (§4 steps 1a/1b) was applied where a quality issue was actually observed (313743) or where a table was genuinely absent from the fetched text (marked `TABLE NOT IN TEXT` and left as such, not fabricated). The "Body boundaries" table above spot-checks 5 representative items rather than all 61; a full per-item audit was not performed this run due to volume.

6. **Skipped rows this run:** 6 URLs recorded as `# skipped <date>` in `seen-urls.txt` (all listing rows dated 2026-09-09, i.e. outside the `RUN_DATE − 1` window): 313769, 313756, 313754, 313737, 313742, 313725.

7. **RUN_DATE-dated rows correctly excluded:** 3 rows on listing page 1 dated 2026-09-11 (313946, 313964, 313963) were not written to `seen-urls.txt` and not fetched, per the window rule.

8. **Listing pages:** rebuilt from the full, corrected `index.json` (95 records); all 95 fall within the 14-day retention window (oldest: 2026-09-06), so nothing was dropped from the listing this run.
