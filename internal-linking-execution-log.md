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
