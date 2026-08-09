# Kaashi Wellness — Website Design Spec

**Date:** 2026-08-09
**Status:** Awaiting user approval

## What we're building

A two-page static website for **Kaashi Wellness** (spa, massage, and yoga center), Secret Waterfall Road, Near Arista Haven, Tapovan, Rishikesh, Uttarakhand. Visual direction: the approved **Misty Rose** mockup (rose-to-lilac-mist gradients, slate ink, Baskerville-style serif, circular/pill shape language).

Goals, in order:
1. Rank for local search: *massage in Rishikesh / Tapovan / Laxman Jhula*, *spa in Rishikesh / Tapovan / Laxman Jhula*, *wellness massage in Rishikesh / Tapovan / Laxman Jhula*, plus yoga-related queries.
2. Get visitors to call one of the two numbers (+91 95484 79582 / +91 82793 29007).
3. Present the full menu and policies clearly on a dedicated pricing page.

## Pages

### 1. Home (`index.html`) — 2000+ words
- **Hero** — Misty Rose gradient, H1: "Massage & Wellness Spa in Tapovan, Rishikesh" styled elegantly; sub-line mentioning Laxman Jhula and Secret Waterfall Road; call CTA + "View treatments & pricing" CTA.
- **Welcome / About** (~250 words) — who Kaashi Wellness is, the setting near the Secret Waterfall trail, genuine Ayurvedic and internationally recognized therapies.
- **Services overview** — six category cards (Full body massage, Ayurveda, Premium rituals, Facials, Scrubs & express care, Yoga & meditation) with starting prices, each ~60–80 words, linking to the pricing page sections.
- **Featured treatment** — Shirodhara (₹2,999 / 60 min): warm oil stream on the forehead, the classic Ayurvedic centerpiece. (User confirmed there is NO "signature Chakra Balancing" offering — do not present Chakra Balancing as a signature; it remains only a regular Premium Package line item on the pricing page.)
- **Yoga packages section** (~200 words) — asanas, alignment, pranayama, Yoga Nidra, dhyana; one-to-one instruction framing.
- **Why Kaashi / location section** (~250 words) — walkable from Laxman Jhula, in the heart of Tapovan's yoga district, on the Secret Waterfall trail; trained therapists, hygiene, draping standards.
- **Testimonials** — 3 quotes (placeholder until real reviews supplied).
- **FAQ** (~500 words, 7–9 questions) — "Which massage is best after trekking/yoga?", "Do you take walk-ins?", "How do I book?", price ranges, couples sessions, what to expect first visit. Doubles as FAQPage schema.
- **Visit** — address, both phones (tap-to-call), hours, Google Maps link.
- **Footer** — nav, keywords-bearing description line, service areas.

Word budget: ~2,200–2,500 words of real, readable copy (no keyword stuffing — locality keywords woven into headings, intro, location section, FAQ, footer).

### 2. Pricing & Treatment Guide (`pricing.html`)
Complete menu as clean, mobile-friendly tables matching the brochure exactly:
- Full Body Massages (5 treatments, 60/90-min prices) with the brochure's per-treatment descriptions (wintergreen, Balinese, lavender aromatherapy, Swedish, rosemary–spearmint).
- Parcel Body Massage (4 × ₹999/30 min), Body Scrub (4 items), Facial (5 × ₹1,999), Premium Package (5 items), Ayurveda (10 items), Yoga (6 items).
- Important Notice, Appointments & Etiquette, Professional Conduct sections (verbatim intent from brochure, lightly copy-edited).
- Sticky "Call to book" bar on mobile.

## Copy voice — must read human, not AI
- Write like the owner talking to a guest: plain sentences, specific details (wintergreen oil, the walk up from Laxman Jhula, monsoon season, post-trek sore calves), occasional imperfect rhythm.
- Banned: AI-tell phrases ("nestled in", "look no further", "unwind and rejuvenate", "immerse yourself", "haven of tranquility", "embark on a journey", "elevate your experience"), em-dash overuse, triadic "X, Y, and Z" sentence stacking, every-paragraph-same-length structure.
- Vary sentence length; use concrete local references (Tapovan cafés, the Ganga, waterfall trail dust, Rishikesh traffic) instead of generic spa language.
- FAQ answers sound like a person who answers this phone daily, including practical quirks (e.g. "call the second number if the first is busy").

## SEO implementation
- Per-page `<title>` + meta description with locality keywords; canonical URLs.
- One H1 per page; H2s carry service + locality terms naturally.
- JSON-LD: `DaySpa` (LocalBusiness) with name, address, geo (Tapovan approx), phones, hours, priceRange; `FAQPage` on home; `Service`/offers on pricing.
- Semantic HTML5 (`header/main/section/article/footer`), descriptive alt text, `loading="lazy"` images.
- Internal linking home ↔ pricing with keyword-bearing anchor text.
- Open Graph + Twitter card tags; sitemap.xml + robots.txt.
- No frameworks — hand-written HTML/CSS/JS for fast load (Core Web Vitals).

## Out of scope (for now)
- Online booking/payment, blog, multi-language, real photography (gradient placeholders until photos are provided), hosting/domain setup (decide after build).

## Confirmed business facts
- Name: **Kaashi Wellness** (double a).
- Address: Secret Waterfall Road, Near Arista Haven, Tapovan, Rishikesh, Uttarakhand.
- Phones: +91 95484 79582, +91 82793 29007.
- Hours: **open every day, 10:00 AM – 8:00 PM**.

## Open items
- Real guest reviews and photos — placeholders used, clearly swappable.

## Verification
- Both pages validate (no broken HTML), render correctly at 360px/768px/1280px.
- Word count of home page body copy ≥ 2,000 (verified by script).
- JSON-LD passes Google's Rich Results test structure (validated locally).
- All prices cross-checked against the brochure images.
