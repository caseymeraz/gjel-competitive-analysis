# Internal Linking Plan: Oakland & San Jose Motorcycle Pages

Companion to `seo-audit.html` (Action Plan item #6). Goal: give the two highest-value
city × practice child pages enough descriptive **in-content** links that Google resolves
local motorcycle queries to them instead of the city hubs.

Prepared July 14, 2026 from the full-site crawl. "In-content" means inside the article/body
copy — not nav menus, office-address footers, or sidebar widgets, which Google discounts.

---

## Target 1: `/oakland/motorcycle-accidents`

**Query to win:** "oakland motorcycle accident lawyer" (2,500/mo). Currently `/oakland`
(the car-accident city hub) ranks #10 for it; this page ranks #6 for the smaller
"oakland motorcycle accident attorneys".

**Current state:** 16 inlinks, but only **1 in-content** (from `/motorcycle-accident-lawyers`).
Everything else is nav menus and the office-address footer block.

### Links to add (11)

| # | Source page (all live, 200) | Suggested anchor | Placement |
|---|---|---|---|
| 1 | `/oakland` (city hub) | Oakland motorcycle accident lawyers | In the body intro where practice areas are described — the hub currently links the child only from its nav menu. This is the single most important link: it tells Google the hub defers to the child for motorcycle queries |
| 2 | `/oakland/car-accident/accident-statistics` | Oakland motorcycle accident lawyer | The page already says "peril extends to motorcyclists as well" — link that sentence's motorcycle reference to the child page instead of leaving it unlinked/pointing at the hub |
| 3 | `/blog/fatal-motorcycle-crash-kills-oakland-man` | Oakland motorcycle accident attorneys | In the closing "legal options" paragraph |
| 4 | `/archives/fatal-motorcycle-accident-in-oakland-dangers-of-traffic-violations` | motorcycle accident lawyer in Oakland | In the safety-resources section |
| 5 | `/archives/lane-splitting-100k-settlement-in-alameda-county` | Oakland motorcycle accident lawyers | Alameda County settlement post — link from the county/venue mention |
| 6 | `/verdicts/motorcycle-accident-in-san-leandro` | motorcycle accident attorneys serving Oakland and the East Bay | San Leandro borders Oakland; link from the case-summary paragraph |
| 7 | `/2023-motorcycle-crash-statistics` | Oakland motorcycle accident lawyer | Where Bay Area / county-level stats are discussed |
| 8 | `/motorcycle-accident-lawyers/verdicts-results` | Oakland motorcycle accident attorneys | In a line noting GJEL's East Bay office handles these cases |
| 9 | `/berkeley/motorcycle-accidents` | Oakland motorcycle accident lawyers | "Nearby areas we serve" body paragraph (reciprocate from Oakland page) |
| 10 | `/hayward/motorcycle-accidents` | Oakland motorcycle accident lawyers | Same nearby-areas pattern |
| 11 | `/oakland/bicycle-accident-lawyers` | Oakland motorcycle accident attorneys | Cross-practice body link ("if you were riding a motorcycle rather than a bicycle…") |

---

## Target 2: `/san-jose/motorcycle-accident-lawyers`

**Query to win:** "motorcycle accident lawyer san jose" (1,200/mo). Currently `/san-jose`
(the general city hub) ranks #4 for it.

**Current state:** 25 inlinks, only **2 in-content** (both from `/motorcycle-accident-lawyers`).
The rest are nav menus, office-address footers, and sidebar widgets.

### Links to add (10)

| # | Source page (all live, 200) | Suggested anchor | Placement |
|---|---|---|---|
| 1 | `/san-jose` (city hub) | San Jose motorcycle accident lawyers | In body copy where the hub describes motorcycle cases — currently the only body mention is a sidebar widget. Same logic as Oakland: hub defers to child |
| 2 | `/blog/fatal-motorcycle-accident-in-willow-glen-crash` | San Jose motorcycle accident attorneys | Willow Glen is a San Jose neighborhood — link from the location reference |
| 3 | `/blog/fatal-hit-and-run-claims-life-of-san-jose-woman` | motorcycle accident lawyer in San Jose | Closing legal-options paragraph |
| 4 | `/archives/san-jose-traffic-sensors-bike-motorcycle-safety` | San Jose motorcycle accident lawyers | Move the existing *sidebar* link into the article body — the content is literally about San Jose motorcycle safety |
| 5 | `/how-to-find-the-best-personal-injury-lawyer-in-san-jose` | San Jose motorcycle accident lawyers | In the practice-area breakdown section (currently only a sidebar link) |
| 6 | `/2023-motorcycle-crash-statistics` | San Jose motorcycle accident lawyer | Where Santa Clara County stats appear |
| 7 | `/motorcycle-accident-lawyers/types-accidents` | San Jose motorcycle accident attorneys | In an intersection/urban-riding section |
| 8 | `/gilroy/motorcycle-accidents` | San Jose motorcycle accident lawyers | Nearby-areas body paragraph (South Bay cluster) |
| 9 | `/san-jose/bicycle-accident-lawyers` | San Jose motorcycle accident attorneys | Cross-practice body link |
| 10 | `/blog/motorcycle-accident-leaves-rider-hospitalized` | motorcycle accident attorneys serving San Jose and the South Bay | Gilroy crash post — South Bay venue mention |

---

## Rules of thumb while implementing

1. **One in-content link per source page** to the target — don't stack multiples.
2. **Vary the anchor** as shown; the exact-match phrase should be ~half the profile, with
   "in Oakland/San Jose" and "attorneys" variants making up the rest.
3. **Keep the bare anchors for the parents:** "motorcycle accident lawyer(s)" (unqualified)
   stays reserved for `/motorcycle-accident-lawyers`; city-qualified anchors go to the city children.
4. After adding, request re-indexing of both child pages and the two city hubs in GSC.
5. Repeat this playbook next for Stockton and Fresno motorcycle pages (both already rank
   #5 and #17 with essentially zero in-content support).
