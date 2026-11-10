# Big U Card Catalog — accessibility audit

**Audit date:** 2026-11-10  
**Scope:** `index.html`, catalog controls, card grid/table, mobile filter drawer, keyboard and responsive behavior.  
**Target:** WCAG 2.2 AA best practices; **not** a certification or a substitute for manual assistive-technology testing.

## High-priority findings and fixes

| Finding | Severity | Resolution |
| --- | --- | --- |
| Mobile filters could open but not be closed inside the panel | Critical | Added large, persistent **Close** button and fixed **Show results** button; also Escape and outside-click dismissal on wider screens |
| Filter opener was an inaccessible `<div>` | High | Converted it to a native `<button>` with accessible name and `aria-expanded` / `aria-controls` |
| Keyboard focus could escape behind the open filter panel | High | Modal dialog semantics, keyboard focus cycle, background `inert`, initial focus, and focus restoration |
| Closed mobile filters could still be reached by keyboard | High | `inert` plus CSS visibility and pointer behavior when collapsed |
| Several search, range, and sort controls lacked associated labels | High | Added `for` associations, labelled min/max inputs, and an accessible sort label |
| Grid / Table selection was not communicated | Medium | Added `aria-pressed` state and labelled view-control group |
| Keyboard focus was difficult to see | Medium | Added consistent high-visibility focus outlines |
| Phone layouts could overflow horizontally | Medium | Constrained grid item widths, responsive toolbar and page sections |
| Table comparison difficult to navigate by assistive tech | Medium | Added caption, column headers, row headers and keyboard-scrollable labelled region |
| Copy title did not give feedback | Medium | Added accessible status announcement and visible copy state |
| Screen-reader navigation lacked skip link | Medium | Added skip-to-results link and clearly named results section |
| Excess motion | Low | Added reduced-motion media-query handling |
| Tiny actionable controls | Medium | Expanded button and checkbox-label targets to improve touch operability |

## Checks performed

- Headless Chromium viewport widths: **320, 375, 390, 430, 768, 1024 and 1280 CSS pixels**
- All seven widths showed **60 cards**, **zero horizontal document overflow**, and **zero JavaScript page errors**
- All `input` and `select` controls had an associated native label or accessible name
- Mobile dialog: open, visible Close, Show results, Escape, Tab and Shift+Tab wrap, background blocking, focus restoration
- Player filtering after closing: choosing **Kevin Durant** correctly displayed **5 records**
- Tablet overlay: tapping the dimmed area dismissed filters
- Desktop: persistent filters and Table view with **60 rows** and updated `aria-pressed`
- JavaScript syntax verified with `node --check`

## Manual follow-up recommended

1. Verify **Safari on an actual iPhone**, including dynamic address-bar and on-screen keyboard behavior.
2. Verify **VoiceOver** (iOS) and **TalkBack** (Android) announcements, swipe navigation, and modal containment.
3. Run a formal WCAG 2.2 AA audit using an automated checker plus manual color-contrast and 200%/400% text zoom testing.
4. Confirm all external seller pages and card data are valid; an accessible catalog does not guarantee accessible third-party pages.

No formal WCAG conformance claim is made by this audit.

## References

- [W3C WAI modal dialog pattern](https://www.w3.org/WAI/ARIA/apg/patterns/dialog-modal/)
- [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/)
