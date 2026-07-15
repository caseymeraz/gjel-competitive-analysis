# Internal Linking — Execution Log

**Executed July 14, 2026** via the WordPress REST API (authenticated as Casey Meraz).
All 21 planned links from `internal-linking-plan.md` are applied and verified rendering
on the live pages. WordPress created a revision for every edited post/page, so any edit
can be reverted from wp-admin → (page) → Revisions.

## Target 1: `/oakland/motorcycle-accidents` — 11 new in-content links

| Source page (WP ID) | Anchor used |
|---|---|
| `/oakland` (page 3992) | Oakland motorcycle accident lawyers |
| `/oakland/car-accident/accident-statistics` (page 3502) | Oakland motorcycle accident lawyer |
| `/blog/fatal-motorcycle-crash-kills-oakland-man` (post 19513) | Oakland motorcycle accident attorneys |
| `/archives/fatal-motorcycle-accident-in-oakland-dangers-of-traffic-violations` (post 11685) | motorcycle accident lawyer in Oakland |
| `/archives/lane-splitting-100k-settlement-in-alameda-county` (post 9705) | Oakland motorcycle accident lawyers |
| `/verdicts/motorcycle-accident-in-san-leandro` (post 3340) | motorcycle accident attorneys serving Oakland and the East Bay |
| `/2023-motorcycle-crash-statistics` (page 3423) | Oakland motorcycle accident lawyer |
| `/motorcycle-accident-lawyers/verdicts-results` (page 4160) | Oakland motorcycle accident attorneys |
| `/berkeley/motorcycle-accidents` (page 5098) | Oakland motorcycle accident lawyers |
| `/hayward/motorcycle-accidents` (page 5047) | Oakland motorcycle accident lawyers |
| `/oakland/bicycle-accident-lawyers` (page 4041) | Oakland motorcycle accident attorneys |

In-content inlinks: **1 → 12**.

## Target 2: `/san-jose/motorcycle-accident-lawyers` — 10 new in-content links

| Source page (WP ID) | Anchor used |
|---|---|
| `/san-jose` (page 798) | San Jose motorcycle accident lawyers |
| `/blog/fatal-motorcycle-accident-in-willow-glen-crash` (post 18065) | San Jose motorcycle accident attorneys |
| `/blog/fatal-hit-and-run-claims-life-of-san-jose-woman` (post 17492) | San Jose motorcycle accident lawyers |
| `/archives/san-jose-traffic-sensors-bike-motorcycle-safety` (post 2117) | San Jose motorcycle accident lawyers |
| `/how-to-find-the-best-personal-injury-lawyer-in-san-jose` (page 3414) | San Jose motorcycle accident lawyers |
| `/2023-motorcycle-crash-statistics` (page 3423) | San Jose motorcycle accident lawyer |
| `/motorcycle-accident-lawyers/types-accidents` (page 3433) | San Jose motorcycle accident attorneys |
| `/gilroy/motorcycle-accidents` (page 5053) | San Jose motorcycle accident lawyers |
| `/san-jose/bicycle-accident-lawyers` (page 3927) | San Jose motorcycle accident attorneys |
| `/blog/motorcycle-accident-leaves-rider-hospitalized` (post 18558) | motorcycle accident attorneys serving San Jose and the South Bay |

In-content inlinks: **2 → 12**.

## Verification

Every edited page was re-fetched (cache-busted) after the update and the new anchor
confirmed present in the rendered HTML: **21/21 live**.

## Still open (needs wp-admin/theme access, not post content)

1. **Template trailing slashes:** `/contact-us/` (966 links) and `/attorneys/` (472 links) — theme edit.
2. **Byline:** `/author/andy` → homepage 301 (542 links). Quick win: change the redirect to point at `/andrew-gillin` in the redirect manager; proper fix is the byline template.
3. **Sitemap:** 238 redirecting URLs in the Rank Math post sitemaps.
4. **GSC:** request indexing for both target pages + both city hubs.
5. Revoke/rotate the application password used for this run (Users → Profile → Application Passwords).

---

# Round 2 — City Hub Anchor Cleanup (July 15, 2026)

Follow-up to the city-hub inlink evaluation (`data/city-hub-inlink-evaluation.csv`).

## Executed: 34 settlement-calculator pages fixed

Every calculator page's closing CTA linked a city hub with the anchor "office location",
"office", "nearest office", or (twice) an empty anchor — 34 links total (17 → /oakland,
17 → /san-francisco). Each was rewritten via the REST API to:

> "…visit our **[Oakland|San Francisco] personal injury office** or contact us at…"

Also cleaned up while in there: stray whitespace-only duplicate links to the hubs and
`/locations` that sat next to the real links (the two "[empty]" anchors from the evaluation),
and a missing-space typo the old markup caused ("officeor").

All 34 pages live-verified post-update: new city anchors render, no weak anchors remain.
Backups in session scratchpad (`wp_backups2.json`) + WordPress revisions per page.

## Not executable via REST — needs page-builder/theme access

These pages store content in ACF fields with custom PHP templates (`page-template-case-ind.php`),
whose fields are not exposed to the REST API. Edit in wp-admin:

1. **Repoint 6 links to city child pages** (from the evaluation's REPOINT rows):
   - `/california-bicycle-accident-lawyers`: "San Jose" → `/san-jose/bicycle-accident-lawyers`,
     "Oakland" → `/oakland/bicycle-accident-lawyers`, "San Francisco" → `/san-francisco/bicycle-accident-lawyers`
     (anchor: "{City} bicycle accident lawyers")
   - `/motorcycle-accident-lawyers`: "San Jose" → `/san-jose/motorcycle-accident-lawyers`,
     "Oakland" → `/oakland/motorcycle-accidents`, "San Francisco" → `/san-francisco/motorcycle-accidents`
     (anchor: "{City} motorcycle accident lawyers")
2. **Upgrade bare-city anchors** on `/car-accident-lawyers`, `/personal-injury-attorneys`,
   `/hit-run-attorney`: "Oakland" → "Oakland car accident lawyers" etc. (hubs stay the target —
   the hubs ARE the city car-accident/PI pages).

---

# Round 3 — /san-francisco Phase 1 Corrections (July 15, 2026)

Executes Phase 1 of `sf-verification-and-plan.md` on WP page 3979 via REST. All changes
live-verified (11/11 checks). Backup: `wp_backups3.json` (scratchpad) + WP revision.

| Fix | Change |
|---|---|
| Statute | Veh. Code §§17707/17708 (minor-driver liability, wrong context) replaced with Ins. Code §11580.2 in the UM/UIM section |
| Crash reporting | "Call police even for minor accidents" replaced with accurate SFPD report criteria (injury / hit-and-run / DUI) + DMV SR-1 requirement (10 days; injury, death, or $1,000+ damage) |
| Statute of limitations | Categorical body sentence now qualified: §335.1, exceptions, six-month government/Muni claim note (matches FAQs) |
| Typos | "suffering.With", "blame.If", "stops.Market" — spaces restored |
| Citation | "Vision Zero and SWITRS crash data" link repointed from the SFMTA program page to the DataSF "Traffic Crashes Resulting in Injury" dataset |

**Attorney review recommended** for the statute and SR-1 wording (both are now accurate but
were drafted by the SEO process, not counsel).

## Not editable via REST (template/widget/plugin — manual list)
- "Don't Face This AloneGet…" heading typo — template widget.
- Two different 866 numbers + 73-review widget — template-driven; normalize in theme/widget.
- `/san-francisco-2` entries on `/sitemap` and `/sitemap-2` — pages are shortcode-generated;
  the stale entry must be cleared in the sitemap plugin/redirect record.

## Next per plan: Phase 2 (build /san-francisco/car-accident-lawyers), Phase 3 (refocus hub
as PI page), Phase 4 (anchor rewiring incl. nav "San Francisco Personal Injury Attorneys" →
/san-francisco).

---

# Round 4 — San Francisco Split Executed (July 15, 2026)

Phases 2–4 of `sf-verification-and-plan.md`, executed via WP REST (user-authorized,
including redirect-rule management).

## New page: https://www.gjel.com/san-francisco/car-accidents (WP page 22040) — LIVE
- 4 venue-labeled case results with links: $285K Golden Gate Park/SF pedestrian UM case;
  $1M rush-hour chain-reaction (Andy Gillin personally); $300K Oakland (managing attorney
  Andy Gillin); I-80 Richmond policy limits (Gillin & Larsen). All facts sourced from the
  case pages on the site.
- Andy Gillin attorney section (links /andrew-gillin), corrected SFPD/SR-1 guidance,
  Ins. Code §11580.2 UM/UIM, comparative fault, Muni six-month claim, focused car FAQ,
  links to hub + 5 SF child pages + statewide page.
- "Where Car Accidents Happen Most in San Francisco" section (with DataSF citation)
  moved here from the hub.
- SEO title set via Rank Math meta: "San Francisco Car Accident Lawyers | GJEL Attorneys".

**URL note:** the planned `/san-francisco/car-accident-lawyers` path is held by a Rank Math
redirect that survived two API deletions (API reported success; `x-redirect-by: Rank Math`
persisted). The page shipped at `/san-francisco/car-accidents` instead — which matches the
site's naming family (`/oakland/motorcycle-accidents`, `/san-francisco/truck-accident`).
**Manual item:** in Rank Math → Redirections, find the rule for
`san-francisco/car-accident-lawyers` and repoint it to `/san-francisco/car-accidents`
(currently it dumps to the hub).

## Hub refocused: /san-francisco (page 3979)
- Title/H1/SEO title now "San Francisco Personal Injury Lawyers | GJEL Attorneys".
- Removed 7 car-specific sections (~21,300 chars, ~36%): post-crash steps, legal rights,
  car types, where-crashes-happen (moved), duplicate damages, duplicate process, car FAQ.
- Added "Hurt in a Car Accident in San Francisco?" bridge section linking the car page.
- Kept: results, attorneys, PI cases, claim process, comparative fault, damages,
  local-knowledge section, PI FAQ, office/contact blocks. Live-verified 12/12 checks.

## Internal links to the car page: 6 live + hub bridge
Added closing in-content links on: /san-francisco/what-to-do-after-accidents,
/archives/the-dos-and-donts…, /archives/the-most-common-types…,
/blog/san-francisco-cable-car-accident…, /san-francisco/fatal-car-accidents,
/san-francisco/bicycle-accident-lawyers. Two more (rear-end-accidents,
link-between-speeding) saved to post content but their templates render an ACF field —
front-end doesn't show them (manual item).

## Backups
wp_backups4.json (hub + car pre-surgery), wp_backups5.json (8 link sources) + WP revisions.

## Remaining manual items for this workstream
1. Rank Math → Redirections: repoint `san-francisco/car-accident-lawyers` rule →
   `/san-francisco/car-accidents`.
2. Template nav anchor "San Francisco Personal Injury Attorneys" → change target from
   /personal-injury-attorneys to /san-francisco (not a WP menu — theme/widget).
3. GSC: request indexing for /san-francisco and /san-francisco/car-accidents.
4. Attorney review of the statute/SR-1/deadline wording on both pages.

---

# Round 5 — Re-Audit Corrections (July 15, 2026)

The second third-party audit was verified against live pages and case-study sources
(~90% accurate, including errors introduced in Round 4). All REST-executable corrections
applied and live-verified 20/20. Backup: `wp_backups6.json` + WP revisions.

## Car page (/san-francisco/car-accidents)
- Results section retitled "Representative San Francisco & Bay Area Car Accident Results";
  intro no longer promises attorney-per-case it doesn't deliver.
- Attributions corrected per the case sources: Jim Larsen credited on the $285K Golden Gate
  Park case; $1M case now located ("I-680 in Dublin") and credited to Larsen + Gillin
  (Andy took the intake call — the overstated "handled from intake through settlement" fixed).
- Attorney section now "The Attorneys Handling…" featuring Gillin + Larsen (bio links);
  "case mill" line replaced with a verifiable involvement statement.
- UM/UIM aligned with the source: uninsured driver → recovered underinsured motorist policy
  limits (flag: attorney should confirm coverage terminology from the file).
- Stats cleaned: 40% state-average claim removed (source couldn't support it); two-thirds
  claim removed; Octavia/Market "#1 / 37 crashes / danger score" replaced with unranked
  wording; "most dangerous roads" / "highest-collision zones" / "notorious" / "long history"
  superlatives softened to descriptive language; DataSF dataset remains linked.
- "Clear liability" → comparative-fault-consistent wording.
- "Office available 24/7" → phones 24/7, office visits by appointment.
- SFPD/CHP report paragraphs moved in from the hub (collision-specific local detail).
- Added "Substantively updated July 2026." (Named "Reviewed by [attorney]" line awaits
  Casey's designation — not added without an actual reviewer.)

## Hub (/san-francisco)
- Both car CTAs → PI CTAs ("Talk to a San Francisco Personal Injury Lawyer Today" /
  "Contact a San Francisco Personal Injury Lawyer").
- "Every type of car accident injury" → full serious-injury PI range.
- "San Francisco's at-fault system" → "California's fault-based system".
- Intro anchor repointed: statewide /car-accident-lawyers → /san-francisco/car-accidents.
- Local section de-car'd ("Winning an injury case…", ER wording, closing copy) and the
  SFPD/CHP collision-report paragraphs moved to the car page; courts/hospitals/venue
  content kept as PI proof.

## Still manual (template/ACF level)
- Hero line "Injured in a San Francisco car accident?" — template.
- Nav "San Francisco Personal Injury Attorneys" → statewide — theme.
- "Nearby Offices" module on the accident-reconstruction article outputting the old car path.
- /san-francisco-2 in HTML sitemap — sitemap plugin.
- Named attorney reviewer line for the car page — needs Casey to designate the reviewer.
- Genuine SF car-accident case studies (only 1 of 4 featured results is SF venue) — content
  gap only the firm's case files can fill.
