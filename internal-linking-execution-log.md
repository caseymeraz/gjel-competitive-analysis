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
