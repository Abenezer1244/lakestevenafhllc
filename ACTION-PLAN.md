# SEO Action Plan — Lake Stevens AFH LLC
**Generated:** 2026-05-10 | **SEO Health Score:** 61 / 100  
**Priority order:** Critical → High → Medium → Low  

---

## CRITICAL — Fix Before Launch (blockers)

| # | Action | File(s) | Effort | Impact |
|---|--------|---------|--------|--------|
| C1 | **Replace `YOUR_FORM_ID` with live Formspree endpoint** — both contact forms are non-functional | `index.html:1478`, `contact.html:285` | 10 min | Contact form works |
| C2 | **Fix factual error: "6 Residents maximum" → "4"** on services.html | `services.html:332` | 2 min | Accuracy/trust |
| C3 | **Create `robots.txt`** at site root with Sitemap directive and explicit AI crawler allow | New file | 15 min | Crawl policy |
| C4 | **Create `sitemap.xml`** listing all 5 canonical URLs | New file | 15 min | Indexation speed |
| C5 | **Claim and verify Google Business Profile** — select "Adult Family Care Facility" as primary category; upload real photos; set hours to "Open 24 hours" | GBP dashboard | 1 hr | Local pack ranking |
| C6 | **Fix H1/H2 word-break rendering artifacts** — `<br>` between "a" and "warm" in hero H1 causes crawlers to read "awarm"; same on contact H1 and several H2s | `index.html`, `contact.html` | 30 min | SERP snippet quality |

---

## HIGH — Fix Within 1 Week

| # | Action | File(s) | Effort | Impact |
|---|--------|---------|--------|--------|
| H1 | **Add `alt` text to all hero background images** — 6 pages all have `alt=""` on hero img elements | All 5 pages | 30 min | Accessibility + image SEO |
| H2 | **Add `width` and `height` to all `<img>` elements** — eliminates CLS (layout shift) | All 5 pages | 45 min | Core Web Vitals (CLS) |
| H3 | **Fix nav `href="index.html"` → `href="/"`** across all pages to match homepage canonical | All 5 pages | 20 min | Duplicate URL signals |
| H4 | **Add hero LCP image preload** — `<link rel="preload" as="image" href="[hero-url]">` in `<head>` | `index.html` | 10 min | LCP improvement |
| H5 | **Add `<link rel="preconnect">` for Unsplash, Google Fonts, esm.sh** in all page heads | All 5 pages | 20 min | LCP / TTFB |
| H6 | **Add `font-display=swap` to Google Fonts URL** | All 5 pages | 5 min | FOIT prevention |
| H7 | **Add `sameAs` to all JSON-LD blocks** once GBP is claimed (add GBP URL, Yelp URL, DSHS registry URL) | All 5 pages | 20 min | Knowledge Panel |
| H8 | **Add `AggregateRating` + `review` array** to homepage schema (JSON-LD ready in FULL-AUDIT-REPORT.md) | `index.html` | 20 min | Star ratings in SERPs |
| H9 | **Add `FAQPage` JSON-LD** to contact.html (JSON-LD ready in FULL-AUDIT-REPORT.md) | `contact.html` | 15 min | AI citation / featured snippets |
| H10 | **Change schema `@id` from `#organization` to `#local-business`** on all pages | All 5 pages | 10 min | Schema correctness |
| H11 | **Expand `areaServed`** to include Snohomish County + WA State nodes alongside City | All 5 pages | 15 min | County-level local signals |
| H12 | **Fix services.html thin content** — currently 490 words (39% below minimum); expand dementia care and medication management sections with differentiating detail, geo-modifiers in H2s | `services.html` | 2 hrs | Keyword ranking depth |
| H13 | **Add location modifier to homepage H1** — e.g., "Exceptional senior care in Lake Stevens, WA" | `index.html` | 5 min | Local #1 ranking factor |
| H14 | **Submit site to WA DSHS AFH Provider Directory** — license 41-4806355 should be live and findable | DSHS portal | 30 min | Authority citation |
| H15 | **Create `/llms.txt`** file at site root (draft ready in FULL-AUDIT-REPORT.md) | New file | 15 min | AI search citability |

---

## MEDIUM — Fix Within 1 Month

| # | Action | File(s) | Effort | Impact |
|---|--------|---------|--------|--------|
| M1 | **Add `favicon.ico` and `apple-touch-icon`** — currently no icon declared | All 5 pages + new file | 30 min | Browser / search appearance |
| M2 | **Add `Service` JSON-LD nodes** for each service via `hasOfferCatalog` | `services.html` | 1 hr | Service-specific rich results |
| M3 | **Add `BreadcrumbList` schema** to all inner pages | 4 pages | 1 hr | SERP breadcrumb display |
| M4 | **Upgrade schema `@type`** to include `NursingHome` (more specific than MedicalBusiness for DSHS-licensed facility) | All 5 pages | 20 min | Schema specificity |
| M5 | **Add `hasMap` property** to all JSON-LD blocks (use Google Maps CID after GBP is verified) | All 5 pages | 15 min | Maps integration |
| M6 | **Create a Privacy Policy page** — required for YMYL/GDPR compliance and form data collection | New page | 1 hr | Trust + compliance |
| M7 | **Expand gallery.html content** — add 2-3 sentences of descriptive copy per category, increase word count above 300 | `gallery.html` | 1 hr | Thin content |
| M8 | **Add two new FAQ items** to contact.html: "What is the difference between an adult family home and assisted living?" and "What areas near Lake Stevens does your home serve?" (140–160 words each) | `contact.html` | 1 hr | AI citation coverage |
| M9 | **Submit Yelp, Caring.com, SeniorAdvisor.com listings** — free tier | Off-site | 2 hrs | Citation authority |
| M10 | **Submit A Place for Mom basic listing** | Off-site | 1 hr | High-intent referral |
| M11 | **Submit to Snohomish County 211 directory** (wa211.org) — frequently used by hospital discharge planners | Off-site | 30 min | Local referral |
| M12 | **Add `priceRange`, `serviceType`, `image`, and `openingHoursSpecification`** to all inner page schemas to match homepage | Inner 4 pages | 30 min | Consistency |
| M13 | **Change `closes: "23:59"` → `"24:00"`** in all openingHoursSpecification blocks | All 5 pages | 10 min | ISO 8601 compliance |
| M14 | **Replace Yahoo email** with a business domain email (e.g., info@lakestevenafh.com) in both visible copy and schema | All 5 pages + DNS | 1 hr | Trust / E-E-A-T |
| M15 | **Add IndexNow key file** and ping on publish | New file + deploy config | 30 min | Bing indexation speed |
| M16 | **Use real staff photos** in about-us.html or remove named staff cards — stock Unsplash headshots labeled as staff are a QRG quality signal failure on a YMYL page | `about-us.html` | varies | E-E-A-T |

---

## LOW — Backlog

| # | Action | Effort | Impact |
|---|--------|--------|--------|
| L1 | Add `WebSite` schema with `SearchAction` to homepage (sitelinks searchbox eligibility) | 30 min | Rich results |
| L2 | Add `WebPage` + `speakable` schema to all pages | 1 hr | Voice / AI |
| L3 | Add OG `locale` meta tag (`en_US`) to all pages | 15 min | Social signals |
| L4 | Create a "Service Area" page for Snohomish County + nearby cities | 3 hrs | County search traffic |
| L5 | Create 2–3 blog posts targeting long-tail ("how to choose an adult family home," "AFH vs assisted living WA," "dementia care at home") | 4–6 hrs | Long-tail traffic |
| L6 | Add `ImageObject` schema to gallery page images | 1 hr | Image rich results |
| L7 | Add `Person` schema for Zinash Shibeshe (owner/operator) with `hasCredential` | 30 min | E-E-A-T |
| L8 | Standardize `openingHoursSpecification` across inner pages (gallery, about-us, services are missing it) | 20 min | Schema consistency |
| L9 | Add `<meta name="referrer" content="no-referrer-when-downgrade">` | 5 min | Minor security |
| L10 | Add Content-Security-Policy and security headers to hosting config (`_headers` or Cloudflare) | 1 hr | Security score |
| L11 | Add "Alzheimer's care Lake Stevens" keyword variant to services page | 30 min | Long-tail keyword |
| L12 | Add Snohomish County geo modifier to about-us.html | 15 min | County-level SEO |

---

## Post-Launch Checklist

Once the site is live at `https://www.lakestevenafh.com/`:

- [ ] Submit `sitemap.xml` in Google Search Console
- [ ] Verify site ownership in Google Search Console
- [ ] Run Lighthouse (Chrome DevTools) and capture Performance, Accessibility, SEO scores
- [ ] Test contact form end-to-end (verify Formspree receives submissions)
- [ ] Ping IndexNow for Bing/Yandex indexation
- [ ] Check all 5 canonical URLs in GSC for indexation status
- [ ] Verify GBP listing is live and address matches site exactly
- [ ] Test schema markup in Google's Rich Results Test
- [ ] Request 3 initial Google reviews from families/referrers

---

## Quick-Win Sequence (Do These First — ~3 Hours Total)

1. Fix services.html "6 Residents" → "4" (2 min)
2. Replace Formspree `YOUR_FORM_ID` in both files (10 min)
3. Create `robots.txt` (15 min)
4. Create `sitemap.xml` (15 min)
5. Create `llms.txt` (15 min)
6. Fix homepage H1 word-break artifact (20 min)
7. Add `width`/`height` to all hero images (30 min)
8. Add alt text to hero images that need it (20 min)
9. Fix nav `index.html` → `/` links (20 min)
10. Add `preconnect` hints for Unsplash, Google Fonts (15 min)

These 10 actions cost ~3 hours and move the SEO Health Score from **61 → ~75**.
