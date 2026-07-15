# /san-francisco Audit — Verification Against Actual Data + Ranking Plan

**July 15, 2026.** Verification of the third-party audit of `https://www.gjel.com/san-francisco`
using: live page fetches (today), the July 14 full-site crawl (1,320 pages / 90,002 links),
WordPress REST inspection, and Ahrefs keyword/ranking data.

---

## Part 1 — Claim-by-claim verification

| # | Audit claim | Verdict | Evidence |
|---|---|---|---|
| 1 | Title & H1 combine PI + car accident intents | **Confirmed** | Title: "San Francisco Personal Injury & Car Accident Lawyer \| GJEL"; H1: "San Francisco Personal Injury & Car Accident Lawyers \| GJEL Attorneys" |
| 2 | Veh. Code §§17707/17708 misplaced in UM/UIM section | **Confirmed** | On-page: "…underinsured motorist coverage fills the gap… California Vehicle Code Section 17707 and 17708 outline specific vehicle ownership and liability responsibilities…" §§17707–08 govern liability tied to a minor's driving/license signer; UM/UIM is Ins. Code §11580.2 |
| 3 | "SF results" section uses non-SF cases | **Confirmed** | H2 "Proven Results for San Francisco Injury Victims" → H3 "Recent **Bay Area** verdicts": $20.452M AC Transit (bus), $7.5M big-rig, $2.2M **Santa Clara County**. Zero SF-venue results |
| 4 | Courthouse/local-experience claims lack adjacent evidence | **Confirmed** | "We've filed and tried cases in this courthouse for years" — no linked case, docket, or verdict adjacent |
| 5 | SOL wording inconsistent | **Confirmed (body vs FAQs)** | Body states two years categorically; PI FAQ correctly qualifies (§335.1 + gov-claim exception); car FAQ says "generally". Body should match the FAQs |
| 6 | Police-report guidance incomplete; no SR-1 | **Confirmed** | Page says "Even if the accident seems minor, call the police. The police reports officers file at the scene become critical evidence." **0 mentions** of SR-1 or DMV anywhere on the page |
| 7 | Stats link to Vision Zero program page, not data | **Confirmed** | Anchor "San Francisco Vision Zero and SWITRS crash data" → `sfmta.com/projects/vision-zero` (program page) |
| 8 | Local anchors point to statewide pages | **Confirmed — with corrected detail** | The actual offender is the **nav anchor "San Francisco Personal Injury Attorneys" → statewide `/personal-injury-attorneys`** on the hub and all 7 SF child pages. The claimed "SF car accident lawyers → statewide car page" link was **not found** in the 90,002-link crawl; SF-car anchors point to `/san-francisco` (currently correct) |
| 9 | `/san-francisco-2` in HTML sitemap | **Confirmed** | Linked from `/sitemap` and `/sitemap-2` with anchor "San Francisco Car Accident Attorneys & Personal Injury…"; 301s (single hop) to `/san-francisco` |
| 10 | Legacy `/san-francisco/car-accident-lawyers` worth investigating | **Confirmed + resolved** | It (and `/san-francisco/personal-injury-attorneys`) 301 **single-hop** to `/san-francisco` today. **Zero internal links** point at either (crawl-verified) — the "GJEL page still refers to it" claim was not found internally; may be an external reference. The path is clean to reclaim |
| 11 | NAP/phone/review inconsistency | **Confirmed — worse than stated** | On-page: 883 Sacramento St **Apt A**; phones (415) 986-4777 **plus two different 866 numbers** (866-292-9907 and 866-218-3776); "5.0 · 73 reviews" widget near top vs "43 Google reviews on our San Francisco" lower down. (Third-party profiles showing 220 Montgomery not independently verified in this session) |
| 12 | Long but repetitive | **Confirmed** | ~5,000+ words. Outline shows 2 damages sections, 2 process sections, 2 FAQ stacks, repeated fee language, plus heading typo "Don't Face This **AloneGet** Expert Legal Help" and 3 missing-space sentence joins |
| 13 | Canonical/indexation "unknown" | **Now known — clean** | Self-canonical `https://www.gjel.com/san-francisco`; meta robots `follow, index`; page returns 200; zero canonical issues in the July 14 crawl |
| 14 | Large templated location footprint | **Confirmed** | Sitemap exposes ~25+ city hubs × practice children with heavily shared modules (per July 14 audit + city-hub anchor evaluation) |

### New data the audit didn't have (changes the plan's emphasis)

**Rankings (Ahrefs, July 14):** gjel.com ranks for only **6** keywords containing "san francisco":

| Keyword | Vol/mo | GJEL position | Ranking URL |
|---|---|---|---|
| san francisco auto accident lawyer | 350 | **#25** | /san-francisco |
| car accident lawyer san francisco | 200 | **#17** | /san-francisco |
| san francisco wrongful death lawyer | 100 | #34 | /san-francisco/…wrongful-death… |
| san francisco bus accident lawyer | 100 | #4 | **/bus-accident-lawyers (statewide!)** |

**`/san-francisco` has zero top-100 rankings for any "personal injury" query.** The combined-intent
page is weakly car-leaning and completely invisible for PI.

**Opportunity sizing (Ahrefs Keywords Explorer, US):**

| Cluster | Combined vol/mo | Difficulty | CPC |
|---|---|---|---|
| SF car accident lawyer/attorney (+auto) | ~2,500 | **KD 16–19** (auto variant 47) | up to $45 |
| SF personal injury lawyer/attorney | ~2,900 | **KD 69–73** | $25–30 |

The car cluster is a genuinely low-difficulty, high-CPC opening. The PI cluster is a long game
that needs the hub's full authority plus real local proof.

---

## Part 2 — Plan to rank for SF car accident + personal injury keywords

### URL map (audit's default mapping is right, and the ranking data now proves it)

| Intent | URL | Title / H1 |
|---|---|---|
| SF personal injury | `/san-francisco` (refocused hub) | San Francisco Personal Injury Lawyers \| GJEL Attorneys |
| SF car accident | `/san-francisco/car-accident-lawyers` (reclaim the 301 path) | San Francisco Car Accident Lawyers \| GJEL Attorneys |

Why not reverse the assignment: the hub's car rankings are weak (#17/#25 — little to lose),
the car cluster's KD 16–19 means a dedicated page with clean internal anchors can win it
outright, and the hub already receives 51 "San Francisco office" boilerplate anchors plus all
PI-scoped signals. Restoring `/san-francisco/car-accident-lawyers` to 200 reverses its current
single-hop 301 cleanly and inherits any residual external equity — zero internal links need
changing because none exist (crawl-verified).

### Phase 1 — Corrections on the current page (this week; REST-executable)

1. Replace §§17707/17708 in the UM/UIM section with Ins. Code §11580.2 (attorney review).
2. Rewrite crash-report guidance: SFPD prepares collision reports for injury / hit-and-run /
   DUI cases; add the DMV SR-1 requirement (10 days; injury, death, or property damage over
   the threshold) as an independent obligation.
3. Align the body SOL wording with the FAQs (qualified, §335.1, government-claim exception).
4. Fix the "AloneGet" heading and the 3 missing-space sentence joins.
5. Label review scopes ("43 Google reviews — San Francisco office" vs firmwide) and present
   one visible local number (415) with DNI for tracking; drop one of the two 866 numbers.
6. Link every crash statistic to its dataset (SFMTA Vision Zero data portal / TIMS-SWITRS,
   with date range and scope) or delete the number.
7. Remove `/san-francisco-2` from the HTML sitemap pages.

### Phase 2 — Build the car page (week 1–2)

Restore `/san-francisco/car-accident-lawyers` as a 200 page (~1,800–2,500 words) using the
car-specific material *moved out of the hub*: corrected post-crash steps (SFPD/SR-1), at-fault
and comparative-fault rules, corrected UM/UIM, SF crash-type sections, the car FAQ — plus three
proof types: 3–5 venue-labeled SF/Bay Area **car** results with attorney + case links, the named
attorneys handling SF car cases, and SF-scoped reviews. The Muni/public-entity angle (6-month
government claim deadline) is an SF-specific differentiator competitors under-serve.

### Phase 3 — Refocus the hub as the PI page (week 2–3)

Strip the moved car content; keep a compact car section linking down to the new page. Lead
with: SF office + attorneys, PI results (venue-labeled), how SF claims are litigated (Civic
Center Courthouse — now *with* linked case evidence), practice-area links to all 8 SF children,
a single PI FAQ. Cut the duplicate damages/process/fee blocks (~40% of current length).

### Phase 4 — Internal links (the day the pages go live; REST-executable)

- Nav/sidebar "San Francisco Personal Injury Attorneys" → `/san-francisco`
  (currently points statewide — the single biggest signal fix).
- All "San Francisco car accident lawyer(s)" anchors → the new car page.
- SF child pages (motorcycle, truck, bicycle, wrongful death, scooter, fatal-car) link up to both.
- Add ~10 in-content links to the car page from SF car blog/archive posts
  (same playbook as the Oakland/San Jose motorcycle round).
- `/bus-accident-lawyers` ranks #4 for "san francisco bus accident lawyer" — ensure it links
  the SF hub; consider an SF bus/Muni child page later.

### Phase 5 — Entity + measurement

- One canonical office record (name, address, one local phone, hours, geo, GBP, sameAs) pushed
  to footer, location page, and LegalService schema; then reconcile external citations
  (Super Lawyers, LinkedIn, FindLaw — outside this session's reach).
- Track the two clusters separately (GSC + rank tracking): query→URL ownership, impressions,
  position, and whether two GJEL URLs ever appear for one cluster. Re-crawl in 30 days.

**Success criteria (90 days):** car page top-10 for "san francisco car accident
lawyer/attorney" (KD 16–19 makes this realistic); hub earning its first top-100 PI rankings;
zero SF-intent anchors pointing at statewide URLs.
