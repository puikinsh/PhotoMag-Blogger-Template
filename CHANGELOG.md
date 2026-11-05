# Changelog

All notable changes to the PhotoMag Blogger Template are documented in this file.

## [2.3.0] - 2026-11-05

### Fixed

- Load-more requests validate responses and cursors before advancing, retain native navigation on failure, import post wrappers, and stop automatic loading after three pages so the footer remains reachable.
- JSON-LD values use Blogger JSON escaping; article schema is shared by desktop and mobile post renderers, with optional modification dates.
- Blogger supplies Open Graph metadata without duplicate template tags; image-only logos retain a listing-page heading.
- Label page-size links preserve existing query strings, fragments and explicit limits. Feed titles/authors are escaped when rendered as HTML.
- Wide images, embeds, tables, code and long words stay within narrow post columns; navigation wraps and respects reduced-motion preferences.

### Added

- Dependency-free XML/JavaScript/JSON-LD checks, Chrome regression fixtures, contributor instructions and an upgrade/rollback guide.

Post-2.2.0 PhotoMag layout fixes (gathered for the next release).

- **Invisible hero slider fixed** — the slider container is now viewport-anchored and slides carry an ID-scoped `100vh`, so the fullscreen photo and centered title card render instead of a black void (Swiper's late-loading `.swiper-slide{height:100%}` was collapsing them to zero height)
- **Link underlines removed** — restored the `a{text-decoration:none}` reset the template relied on
- **Top bar share toggle centered** — the share icon flex-centers within the bar height
- **Slide-out drawer styled** — uppercase widget headings with separators, a featured-post card with gradient overlay, floated popular-post thumbnails, list resets, and a bordered close button replace the previously near-unstyled raw HTML
- **Main navigation menu restored** — the vanilla menu builder now re-shows the nav widget (the `#pixel-menu > div{display:none}` guard was hiding it because the jQuery `display:block!important` reveal was dropped in the rewrite) and tags submenu parents with `parent` so dropdowns open on hover (the rewrite was adding an unused `hasSubmenu` class)
- **Header social icon aligned** — the share toggle is vertically centered and in line with the search and hamburger icons (the earlier fix targeted `.social-share > a`, but the anchor is nested as `.social-share > ul > li > a`, so it never matched)
- **Footer widgets styled** — Popular Posts get floated thumbnails with titles and snippets, Labels render as bordered pills, and Blog Archive gets a clean indented hierarchy with toggles and post counts

## [2.2.0] - 2026-06-12

Stability and polish release: layout regressions fixed, menus made instant and reliable, typography refined, and accessibility tightened.

- **Grid fix** — the Bootstrap-replacement CSS now matches Bootstrap 4 semantics exactly (column scoping via `:where()`), fixing collapsed header layouts and mega menu items stacking at full width
- **Header, search, and contact form fixes** — restored the logo/menu header layout, removed a double icon in the search overlay, and gave the footer contact form proper field sizing
- **Accessibility/SEO** — every image, server-rendered or JavaScript-generated, now carries an alt attribute (post covers use the post title, ads and avatars are labeled appropriately)
- **Author bio fix** — a default avatar shows when the post author has no Google profile photo, instead of a broken image
- **Self-updating footer copyright year** (with 2026 fallback) and removal of leftover Owl Carousel license comments
- **Documentation** — README rebuilt with a live preview screenshot and a cross-linked gallery of all nine Colorlib Blogger templates

## [2.1.0] - 2026-06-11

### Changed

- **Font Awesome 4.7 + Ionicons 2.0.1 consolidated into Font Awesome 7.2.0** — one icon library instead of two 2014-era ones; every icon class and CSS glyph migrated
- **Social icons modernized** — Google+ and Vine defaults replaced with TikTok, Threads, Pinterest, and X (Twitter); the social bar gains TikTok, Threads, Telegram, and WhatsApp support; the legacy Twitter bird gives way to the X glyph
- Search submit buttons carry an explicit `type='submit'`

## [2.0.0] - 2026-06-11

Major modernization release: zero frameworks, zero render-blocking external assets, structured data, and an accessibility pass.

### Performance

- **jQuery 1.11.0 removed entirely** — menu builder, slide-out sidebar, FeaturedPost background, popular-posts fixes, author injections, date formatting, and the sticky top menu rewritten as modular vanilla JavaScript
- **Homepage slider rebuilt on Swiper 11** (replaces Owl Carousel) — loaded on demand, fade effect, autoplay, and dots preserved; first slide preloads with `fetchPriority=high`
- **Infinite scroll rewritten** with `fetch()` + `DOMParser` instead of `jQuery.ajax` — keeps the load-more button and near-bottom trigger
- **Bootstrap 4.0.0-beta.2 removed** — replaced by ~20 lines of custom CSS; **Sticky-kit removed** (loaded but never called)
- Post covers resize server-side via Blogger's `resizeImage()`; native lazy loading on template images
- Preconnect hints; Font Awesome and Ionicons on pinned https jsDelivr URLs; Google Fonts with `display=swap`; Blogger's widget CSS bundle suppressed via `b:css='false'`

### SEO

- Removed the site-wide `index,nofollow` robots meta
- JSON-LD structured data (`WebSite` + `SearchAction` sitewide, `BlogPosting` on posts), Open Graph and Twitter card meta
- Single `h1` per page; `html lang` from the blog locale; alt text no longer overwritten with filenames

### Accessibility

- Skip-to-content link, main landmark, labeled search field, menu toggle, and archive dropdown; user zoom no longer blocked

### Fixed / Removed

- FollowByEmail widgets (FeedBurner shut down in 2021), the dead Google+ share button, hardcoded "Posts by Diago", Blossom Themes author bio, http:// facebook sharer, stray browser-extension attributes baked into the search form, obsolete vendor prefixes and mobile meta tags

## [1.0.0] - 2018

- Initial release, previously distributed via colorlib.com (now published on GitHub)
