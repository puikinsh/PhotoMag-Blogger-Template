# Changelog

All notable changes to the PhotoMag Blogger Template are documented in this file.

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
