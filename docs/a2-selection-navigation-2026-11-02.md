# Selection-preserving A2 navigation — 3.10.0

A visitor who selected capabilities could previously lose those choices by using a general contact button instead of the picker’s continue button. Product-page language switches also discarded the selection. Contact calls to action now carry the same selected product and capabilities, and switching between Persian and English preserves those choices.

Resetting the picker updates the links too. A product page reconstructs only choices belonging to that product and ignores unknown or repeated module identifiers. No free-text draft or private information is carried in these links; no browser storage or automatic message submission was added. Canonical URLs remain unchanged.

Navigation tests pass eight language, viewport and appearance combinations in both Chromium and WebKit, covering contact links, language round trips, reset and cross-product query rejection. Existing brief regression and static page checks also pass, retaining 315 canonical sitemap URLs. Destination selection states were visually reviewed in light/dark and mobile/desktop. No conversion gain or owner acceptance is claimed.

Try the [Persian product page](https://amiraliyaghouti.com/fa/watch-platform.html#module-1), choose a capability, then switch language or use a contact button.

Release 3.10.0 is published. All 260 release files match live HTTPS hashes. Chromium and WebKit each pass all eight live navigation contexts. Selected published destination states were visually reviewed. The previous release remains available for recovery.
