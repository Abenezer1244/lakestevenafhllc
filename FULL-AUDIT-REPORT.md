# SEO Audit Report — Lake Stevens AFH LLC
**Audit Date:** 2026-05-10  
**Site:** https://www.lakestevenafh.com/  
**Status:** Pre-launch (site not yet live — analyzed from local HTML files)  
**Business Type:** Local Service — Adult Family Home (Brick & Mortar, Lake Stevens WA)  
**Auditor:** claude-seo:seo-audit v1.8.1  

---

## Executive Summary

| Category | Score | Weight | Weighted |
|----------|-------|--------|---------|
| Technical SEO | 52/100 | 22% | 11.4 |
| Content Quality | 61/100 | 23% | 14.0 |
| On-Page SEO | 74/100 | 20% | 14.8 |
| Schema / Structured Data | 68/100 | 10% | 6.8 |
| Performance (CWV) | 54/100 | 10% | 5.4 |
| AI Search Readiness | 58/100 | 10% | 5.8 |
| Images | 48/100 | 5% | 2.4 |
| **TOTAL** | | | **60.6 / 100** |

### Overall SEO Health Score: 61 / 100 — "Needs Work (Pre-launch)"

This is a brand-new domain with no backlinks or indexation history. The site has a strong technical foundation (good titles, canonicals, schema base, internal linking) but has several critical pre-launch blockers and a number of high-priority gaps in local SEO, content depth, and structured data that should be resolved before submitting to Google.

---

### Top 5 Critical Issues (Fix Before Launch)

1. **Broken contact forms** — Both `index.html` and `contact.html` have `action="https://formspree.io/f/YOUR_FORM_ID"`. Form submissions will fail on launch, losing every lead.
2. **No robots.txt** — Without this file, crawlers have no guidance; Googlebot can't find the sitemap.
3. **No sitemap.xml** — Google cannot discover pages efficiently; delays indexation of the full site.
4. **Hero images missing alt text** — All page hero/banner images have empty `alt=""`. This is both an accessibility violation (WCAG 2.1 A) and a missed image SEO signal.
5. **H1/H2 text concatenation artifacts** — `data-pretext` layout engine renders words run-together in the DOM (`"Exceptional care in awarm"`, `"Is Lake Stevens AFHthe right fit"`). Google reads the DOM text, not visual output — search snippets will look broken.

### Top 5 Quick Wins

1. Add `robots.txt` and `sitemap.xml` (30 minutes — fixes indexation)
2. Register Formspree and replace `YOUR_FORM_ID` (10 minutes — unblocks lead capture)
3. Add `alt` attributes to all hero images (20 minutes — fixes accessibility + image SEO)
4. Add `width` and `height` attributes to all `<img>` tags (30 minutes — eliminates CLS)
5. Add FAQPage schema to `contact.html` (30 minutes — highest ROI structured data for AI search)

---

## 1. Technical SEO

**Score: 52/100**

### Crawlability & Indexability
| Check | Status | Detail |
|-------|--------|--------|
| robots.txt | ❌ MISSING | No robots.txt at root. Googlebot will crawl but finds no sitemap pointer. |
| sitemap.xml | ❌ MISSING | No XML sitemap. All 5 pages must be discovered organically. |
| Canonical tags | ✅ Pass | All 5 pages have `<link rel="canonical">`. Correct URLs. |
| Meta robots | ✅ Pass | All pages: `index, follow`. |
| Canonical/nav mismatch | ⚠️ Warn | Nav links point to `index.html` but homepage canonical is `/`. Minor signal dilution. |
| HTTPS | ✅ Pass | Canonicals use HTTPS throughout. |
| Lang attribute | ✅ Pass | `<html lang="en">` on all pages. |

### Page Speed & Resources
| Check | Status | Detail |
|-------|--------|--------|
| Viewport meta | ✅ Pass | `width=device-width, initial-scale=1` on all pages. |
| Image width/height | ❌ Missing | No `width`/`height` attributes on any `<img>`. Causes Cumulative Layout Shift (CLS). |
| Lazy loading | ✅ Pass | Below-fold images correctly use `loading="lazy"`. |
| preconnect hints | ❌ Missing | No `<link rel="preconnect">` for Unsplash, Google Fonts, or esm.sh CDN. |
| Render-blocking scripts | ⚠️ Warn | `<script type="module">` imports from `esm.sh` CDN (pretext). If CDN is slow, layout engine delays. |
| Font loading | ⚠️ Warn | Google Fonts loaded via `<link>` without `font-display: swap`. Flash of invisible text risk. |
| defer/async | ✅ Pass | `type="module"` is inherently deferred. Standalone scripts in IIFE at bottom of body. |

### Security & Headers
| Check | Status | Detail |
|-------|--------|--------|
| CSP (meta) | ❌ Missing | No Content-Security-Policy meta tag. Should add once hosting is confirmed. |
| Referrer Policy | ❌ Missing | No `<meta name="referrer">`. Minor. |
| HSTS | N/A | Requires server-level header — not configurable in static HTML. |

### Broken/Pre-launch Blockers
| Issue | Severity | File |
|-------|----------|------|
| `action="https://formspree.io/f/YOUR_FORM_ID"` | **Critical** | index.html:1478, contact.html:285 |
| No robots.txt | **Critical** | — |
| No sitemap.xml | **Critical** | — |

---

## 2. Content Quality

**Score: 61/100**

### Word Count & Thin Content
| Page | Words | Status |
|------|-------|--------|
| index.html | 785 | ✅ Adequate |
| about-us.html | 500 | ⚠️ Borderline thin |
| services.html | 490 | ⚠️ Borderline thin |
| contact.html | 526 | ✅ OK (FAQ content helps) |
| gallery.html | 180 | ❌ Thin — high risk |

Gallery page is the clearest thin-content risk. It has 13 images with captions but only ~180 words of prose. Google may undervalue this page or view it as low-quality without a written description of the space.

### E-E-A-T Signals
| Signal | Status |
|--------|--------|
| Owner/operator named | ⚠️ Partial — "ZS" initials only in trust section; no full name |
| Staff credentials | ⚠️ Partial — job titles listed but no certifications, license numbers, or years |
| WA DSHS license number | ❌ Missing — most high-E-E-A-T care sites list the AFH license # |
| Testimonials | ✅ Present — 3 on homepage, authentic-sounding |
| Physical address | ✅ Present — 11921 24th PL NE, Lake Stevens WA 98258 |
| Phone number | ✅ Present — (206) 383-3109 on all pages |

### Keyword Coverage
| Keyword | Present | Notes |
|---------|---------|-------|
| adult family home Lake Stevens WA | ✅ | Title, H-tags, body |
| adult family home Lake Stevens | ✅ | Multiple pages |
| senior care Lake Stevens WA | ✅ | Meta descriptions |
| dementia care Lake Stevens | ✅ | Services page |
| assisted living Lake Stevens | ⚠️ | Present in schema serviceType but thin in body text |
| memory care Lake Stevens WA | ❌ | Not used as phrase — missed long-tail |
| 24/7 senior care WA | ✅ | Used on homepage |
| Snohomish County senior care | ❌ | Missing — significant geo expansion opportunity |

### H1/H2 Rendering Artifacts (Critical for Search Snippets)
The `data-pretext` text layout engine splits words for optical sizing. In the DOM, this produces run-together text:

- `index.html` H1: `"Exceptional care in awarm, family environment"` (missing space before "warm")
- `index.html` H2: `"Is Lake Stevens AFHthe right fit"` (missing space before "the")
- `gallery.html` H2: `"Beautiful spaces make a real difference"` ✅ clean
- `contact.html` H1: `"We'd love toshow you our home"` (missing space before "show")

Google uses DOM text for search result titles/descriptions. These will appear garbled in SERPs.

### Content Gaps
- ❌ No blog or resource section (limits long-tail keyword targeting)
- ❌ No pricing page or cost guidance (high-intent search term: "adult family home cost Lake Stevens")
- ❌ No "how to choose an AFH" guide (excellent FAQ content for featured snippets)
- ❌ Gallery uses stock photos, not actual home photos — undermines authenticity claims
- ⚠️ About page references team but gives no full names — reduces trust for high-stakes decisions

---

## 3. On-Page SEO

**Score: 74/100**

### Title Tags
| Page | Title | Length | Issues |
|------|-------|--------|--------|
| index | Lake Stevens AFH — Adult Family Home in Lake Stevens, WA | 56 chars | ✅ |
| about-us | About Us \| Lake Stevens AFH — Adult Family Home in Lake Stevens, WA | 68 chars | ✅ |
| services | Our Services \| Lake Stevens AFH — Senior Care in Lake Stevens, WA | 66 chars | ✅ |
| gallery | Gallery \| Lake Stevens AFH — Our Home in Lake Stevens, WA | 57 chars | ✅ |
| contact | Contact Us \| Lake Stevens AFH — Schedule a Visit in Lake Stevens, WA | 69 chars | ✅ |

All titles are well-crafted, unique, and include location keywords. Excellent.

### Meta Descriptions
All 5 pages have unique, well-written meta descriptions with location keywords and clear value propositions. All within 120–160 character range.

### Heading Structure
| Page | H1 Count | Issue |
|------|----------|-------|
| All pages | 1 each | ✅ |
| index | Multiple H2s | ✅ Well organized |
| gallery | Only 2 H2s, no H3 | ⚠️ Light structure |
| contact | 2 H2s, no H3 | ⚠️ FAQ section not sub-headed |

### Internal Linking
- ✅ All 5 pages link to all other pages via nav
- ✅ Footer links include service section anchors
- ✅ Service cards link to `services.html#dementia`, `#daily`, etc.
- ⚠️ Nav uses `index.html` but canonical is `/` — minor inconsistency
- ❌ No breadcrumb navigation on inner pages
- ❌ Gallery page has no links to specific services mentioned

### Open Graph & Social
- ✅ All pages have `og:title`, `og:description`, `og:image`, `og:url`
- ✅ Twitter Card on all pages
- ⚠️ OG images are Unsplash URLs — third-party, could become unavailable
- ❌ No `og:locale` specified

---

## 4. Schema / Structured Data

**Score: 68/100**

### Current Implementation
All 5 pages include a `LocalBusiness` + `MedicalBusiness` JSON-LD block with:
- ✅ `name`, `alternateName`, `url`, `telephone`, `email`
- ✅ `address` (PostalAddress with full street address)
- ✅ `geo` (GeoCoordinates with lat/lng)
- ✅ `openingHoursSpecification` (24/7, Monday–Sunday)
- ✅ `serviceType` array
- ✅ `areaServed`
- ✅ `ContactPoint` on contact page

### Issues with Existing Schema
| Issue | Severity |
|-------|----------|
| `@id` uses `#organization` — should be `#local-business` for LocalBusiness | Medium |
| `priceRange` only on homepage, absent on inner pages | Low |
| `image` field absent on about-us, services, gallery, contact schemas | Medium |
| `sameAs` array absent — no GBP, Facebook, DSHS registry links | High |
| Gallery schema stripped down — missing `openingHours`, `priceRange` | Low |
| No `numberOfRooms` or resident capacity stated in schema | Medium |

### Missing Schema (Highest Impact First)
| Schema Type | Priority | Page | Impact |
|-------------|----------|------|--------|
| `FAQPage` | **High** | contact.html | AI citation, featured snippet eligibility |
| `AggregateRating` / `Review` | **High** | index.html | Star ratings in SERPs, CTR boost |
| `BreadcrumbList` | **Medium** | All inner pages | Breadcrumb display in SERPs |
| `Service` | **Medium** | services.html | Individual service targeting |
| `WebPage` + `speakable` | **Medium** | All pages | Google Assistant / AI voice readiness |
| `Person` for staff | **Low** | about-us.html | E-E-A-T signal |

---

## 5. Performance (Estimated)

**Score: 54/100**  
*(Note: Site not live — CrUX field data unavailable. Estimates based on static analysis.)*

### Core Web Vitals Risk Factors
| Metric | Risk | Cause |
|--------|------|-------|
| **LCP** | ⚠️ Medium | Hero images served from Unsplash CDN (external, no preload) |
| **CLS** | ❌ High | No `width`/`height` on any `<img>` — browser can't reserve space, layout shifts on load |
| **INP** | ✅ Low | Minimal JS interaction; scroll listeners are passive |
| **TTFB** | ⚠️ Depends | Static file hosting — depends on CDN/hosting choice |

### Resource Loading Issues
| Resource | Issue | Fix |
|----------|-------|-----|
| Google Fonts | No `font-display: swap` | Add `&display=swap` to Fonts URL |
| Unsplash hero images | No `<link rel="preload">` | Add `preload` for first hero image |
| Google Fonts / Unsplash | No `<link rel="preconnect">` | Add preconnect hints in `<head>` |
| esm.sh CDN | External module import | If fails, pretext layout breaks (nav fix already applied) |

### Estimated Lighthouse Scores
| Category | Estimated Score |
|----------|----------------|
| Performance | 65–75 (desktop), 45–60 (mobile) |
| Accessibility | 78–85 (hero alt="" issues drag it down) |
| Best Practices | 80–90 |
| SEO | 85–92 |

---

## 6. Images

**Score: 48/100**

### Missing Alt Text (Critical)
Every hero/banner image on all 5 pages has `alt=""`:

| Page | Image | Alt Status |
|------|-------|------------|
| index.html | Hero img 1 (Unsplash room) | ❌ Empty |
| index.html | Hero img 2 (Unsplash room) | ❌ Empty |
| about-us.html | Page hero bg | ❌ Empty |
| services.html | Page hero bg | ❌ Empty |
| gallery.html | Page hero bg | ❌ Empty |
| contact.html | Page hero bg | ❌ Empty |

These images are in `<img aria-hidden="true">` markup in most cases — if truly decorative, `alt=""` + `aria-hidden="true"` is acceptable (WCAG compliant). However, the hero images carry significant visual weight and some are NOT purely decorative (they show the home environment). Recommended: use descriptive alt on the most meaningful hero image.

### Missing Width/Height (High — CLS)
Zero `<img>` elements across all 5 pages have `width` and `height` attributes. This causes the browser to reserve no space, causing layout shift as images load.

### Stock Photo Risk
All images are Unsplash stock photography. For an adult family home positioning as "our real home," actual interior/exterior photography would dramatically increase trust, conversion, and E-E-A-T signals. This is a business recommendation, not purely an SEO one.

### Format & Size
- All images use `?auto=format` via Unsplash CDN — this serves modern formats (WebP/AVIF) automatically where supported. ✅
- Image sizes are appropriate (600–1800px depending on context). ✅

---

## 7. AI Search Readiness

**Score: 58/100**

### GEO / Generative Engine Optimization
| Signal | Status |
|--------|--------|
| llms.txt | ❌ Missing |
| robots.txt (AI crawler access) | ⚠️ Missing (currently fully open, which is good, but unintentional) |
| FAQPage schema | ❌ Missing |
| Speakable schema | ❌ Missing |
| Passage-level citability | ✅ Moderate — key facts (address, phone, services) in clear prose |
| Brand + location co-mention | ✅ Good — "Lake Stevens AFH" + "Lake Stevens, WA" co-mentioned 20+ times |
| Structured data depth | ✅ Good base schema |

### AI Citation Readiness
The site has good raw material for AI citations:
- Clear service descriptions in prose format
- FAQ accordion on contact page (6 questions/answers)
- Specific details: "maximum 4 residents," "11921 24th PL NE," "(206) 383-3109"

Missing:
- FAQPage JSON-LD to signal the FAQ structure to crawlers
- Speakable markup for voice/AI assistant access
- No pricing guidance (most common AI-cited metric for care decisions)

---

## 8. Local SEO

**Score: 65/100** *(not weighted in main score)*

### NAP Consistency
NAP (Name, Address, Phone) is consistent across all pages via shared footer:
- Name: Lake Stevens AFH LLC ✅
- Address: 11921 24th PL NE, Lake Stevens, WA 98258 ✅
- Phone: (206) 383-3109 ✅

### Google Business Profile
- ❌ No GBP claimed/linked — most critical local SEO asset for a brick-and-mortar business
- ❌ No GBP URL in schema `sameAs`
- ❌ No review schema linked to GBP

### Citation Opportunities
The following platforms are high-priority for adult family home citations:

| Platform | Priority | Type |
|----------|----------|------|
| Google Business Profile | **Critical** | Primary local signal |
| WA DSHS AFH Registry | **Critical** | Authority citation, license verification |
| Caring.com | **High** | Senior care directory, high DA |
| SeniorAdvisor.com | **High** | Senior care directory, review platform |
| A Place for Mom | **High** | High-intent referral traffic |
| Yelp | **Medium** | General local citation |
| Healthgrades | **Medium** | Medical business citation |
| AgingCare.com | **Medium** | Senior care community |
| Facebook Business Page | **Medium** | Social signal, sameAs |
| Better Business Bureau | **Low** | Trust signal |

### Local Content Opportunities
- ❌ No "Lake Stevens, WA" neighborhood page
- ❌ No Snohomish County coverage mention
- ❌ No nearby city targeting (Everett, Marysville, Arlington, Monroe, Bothell)
- ❌ No comparison content ("adult family home vs assisted living vs nursing home")

---

## 9. Backlinks

**Score: N/A (brand new domain)**

- Domain: `lakestevenafh.com`
- Common Crawl (Jan–Mar 2026): **0 referring domains**
- No PageRank, no Harmonic Centrality established
- DA/PA: Not measurable (new domain)
- Google APIs: Not configured

**Expected baseline:** A newly launched local service site. Zero backlinks is normal at launch. Priority after launch: claim citations, GBP, and DSHS registry listing.

---

## Scoring Summary

| Category | Raw Score | Weight | Contribution |
|----------|-----------|--------|-------------|
| Technical SEO | 52 | 22% | 11.4 |
| Content Quality | 61 | 23% | 14.0 |
| On-Page SEO | 74 | 20% | 14.8 |
| Schema | 68 | 10% | 6.8 |
| Performance | 54 | 10% | 5.4 |
| AI Search | 58 | 10% | 5.8 |
| Images | 48 | 5% | 2.4 |
| **Total** | | | **60.6 / 100** |

---

*Report generated by claude-seo:seo-audit v1.8.1 · Pre-launch static analysis · No Google API / Moz credentials configured · CrUX data unavailable (site not live)*
