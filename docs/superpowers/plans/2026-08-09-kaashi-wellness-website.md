# Kaashi Wellness Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build the two-page static Kaashi Wellness site (home + pricing) in the approved Misty Rose direction, SEO-optimized for massage/spa/wellness queries in Rishikesh, Tapovan, and Laxman Jhula.

**Architecture:** Hand-written static HTML/CSS (no frameworks, no build step). One shared stylesheet carries the Misty Rose token system from the approved mockup. Each page is a complete semantic document with its own meta tags and JSON-LD.

**Tech Stack:** HTML5, CSS3, minimal vanilla JS (mobile nav only). Python one-liners for verification (word count).

## Global Constraints

- Business name: **Kaashi Wellness** (double a) everywhere.
- Address: Secret Waterfall Road, Near Arista Haven, Tapovan, Rishikesh, Uttarakhand 249192.
- Phones: +91 95484 79582 and +91 82793 29007 — always tap-to-call `tel:` links.
- Hours: open every day, 10:00 AM – 8:00 PM.
- NO "signature Chakra Balancing" feature — Shirodhara (₹2,999/60 min) is the featured treatment; Chakra Balancing appears only as a Premium Package pricing row.
- All prices exactly as in the brochure (see price data in Task 3).
- Copy voice: human, owner's voice. Banned phrases: "nestled in", "look no further", "unwind and rejuvenate", "immerse yourself", "haven of tranquility", "embark on a journey", "elevate your experience". Vary sentence lengths; concrete local detail (Laxman Jhula, waterfall trail, Ganga, post-trek soreness).
- Homepage body copy ≥ 2,000 words (verified by script).
- SEO keyword targets woven naturally: massage in Rishikesh / Tapovan / Laxman Jhula; spa in Rishikesh / Tapovan / Laxman Jhula; wellness massage in Rishikesh / Tapovan / Laxman Jhula; yoga packages in Rishikesh.
- Misty Rose tokens (from approved mockup): gradient #f2d9de → #e9d9e8 → #dce0ee; ground #f6f4f7; ink #3c4356; ink-soft #6f7488; accent #b57e93; accent-ink #96617a; line #e4e2ec; display serif Baskerville stack; body Seravek stack; circles/pill radius language.
- Accessibility floor: one H1 per page, visible focus states, reduced-motion respected, alt text on all images, contrast ≥ 4.5:1 for body text.

---

### Task 1: Repo scaffold + shared stylesheet

**Files:**
- Create: `.gitignore`, `css/style.css`
- Test: manual — open a bare test page, confirm tokens render

**Interfaces:**
- Produces: class names used by both pages: `.wrap`, `.eyebrow`, `.btn`, `.btn.ghost`, `.hero`, `.orb`, `.svc-grid`, `.svc`, `.quotes`, `.quote`, `.visit`, `.hours`, `.price-table`, `.sticky-call`, `nav`, `footer` — all styled via the Misty Rose custom properties on `:root`.

- [ ] **Step 1:** `git init` in project root; add `.gitignore` (`.DS_Store`, `scratchpad/`).
- [ ] **Step 2:** Port the mockup's Misty Rose CSS (dir-mist tokens promoted to `:root`, drop the other two directions and switcher styles) into `css/style.css`; add pricing-page styles: `.price-table` (full-width, zebra-free, hairline rows, right-aligned tabular-nums prices), `.policy` sections, `.sticky-call` (fixed bottom call bar, visible ≤760px), sticky top nav (solid on scroll via small JS class toggle).
- [ ] **Step 3:** Commit: `feat: scaffold with Misty Rose stylesheet`.

### Task 2: Homepage (`index.html`) — structure + 2000+ words of copy

**Files:**
- Create: `index.html`
- Test: word-count script + manual render at 360/768/1280px

**Interfaces:**
- Consumes: `css/style.css` classes from Task 1.
- Produces: anchor ids `#services`, `#shirodhara`, `#yoga`, `#location`, `#faq`, `#visit` (linked from pricing page and nav).

Sections in order (word budgets): hero (H1 "Massage & Wellness Spa in Tapovan, Rishikesh" — visually styled as two lines; ~60 words), about/welcome (~280), services overview — 6 category cards each linking to `pricing.html#<section>` (~450 total), Shirodhara feature (~180), yoga packages (~230), location/"finding us" (~280), testimonials ×3 (~120), FAQ 8 questions (~550), visit/hours (~100), footer with locality description line (~60). Total ≈ 2,300.

- [ ] **Step 1:** Write full `index.html` per section list, meta title `Kaashi Wellness — Massage & Spa in Tapovan, Rishikesh | Near Laxman Jhula`, meta description ≤160 chars with keywords, canonical, OG/Twitter tags.
- [ ] **Step 2:** Verify word count: `python3 -c` script stripping tags counts ≥ 2000. Expected: ≥ 2000.
- [ ] **Step 3:** Scan for banned phrases: `grep -iE 'nestled|look no further|unwind and rejuvenate|immerse yourself|haven of tranquility|embark|elevate your'` → no matches.
- [ ] **Step 4:** Commit: `feat: homepage with 2000+ words of local SEO copy`.

### Task 3: Pricing page (`pricing.html`) — complete brochure menu

**Files:**
- Create: `pricing.html`
- Test: cross-check every row against brochure data below

Price data (verbatim from brochure):
- **Full Body Massages** (60/90 min): Deep Tissue w/ Wintergreen 2499/3499 · Balinese w/ Wintergreen, Bayleaf & Clove 2299/3299 · Relaxing Aromatherapy w/ Lavender 2499/3499 · Swedish w/ Wintergreen, Bayleaf & Clove 1999/2999 · Energizing Aromatherapy w/ Rosemary & Spearmint —/2999. Include the brochure's descriptions for each.
- **Parcel Body Massage** (30 min, ₹999 each): Comforting Back w/ Wintergreen Oil, Bayleaf & Clove · Comforting Back Massage · Refreshing Foot Reflexology · Soothing Head, Neck and Shoulder.
- **Body Scrub** (30 min): Exfoliation & Rejuvenation (Walnut & Apricot) 1499 · Exfoliation & Rejuvenation (Coffee & Cane sugar) 1499 · Nourishing Body Masque (Charcoal) 1999 · Nourishing Body Masque (Sandalwood) 1999.
- **Facial** (60 min, ₹1999 each): Hydrating (Normal/Dry) · Purifying (Combination/Oily) · Lightening · Age-Defying · Healing (Acne-prone).
- **Premium Package** (90 min unless noted): Revitalizing Thai 2999 · Hot Stone 3499 · Potli (Hot Herbal Poultice) 3499 · Udwarthanam 3499 · Chakra Balancing with Sound Healing 3999 (120 min).
- **Ayurveda:** Abhiyanga 3499 (90) · Kumkumadi Facial 2499 (60) · Shirodhara 2999 (60) · Reviving Mitti 2499 (60) · Nasyam 1999 (30) · Akshayatarpan (Netra Vasti) 1999 (45) · Janu Vasthi 1999 (45) · Katee Vasthi 1999 (45) · Greeva Vasti 1999 (45) · Gharshana (Neem & Rose Scrub) 1499 (40).
- **Yoga:** Asanas (Body Posture) 2999 (75) · Yoga Alignment 2999 (60) · Pranayama 1999 (45) · Advanced Pranayama with Bandhas 1999 (45) · Yoga Nidra 1499 (45) · Dhyanas (Meditation) 1499 (45).
- Policy sections: Important Notice (5 bullets), Appointments & Etiquette (5 bullets), Professional Conduct (3 bullets) — brochure intent, lightly copy-edited to house voice.

**Interfaces:**
- Consumes: Task 1 classes; anchors `#full-body`, `#express`, `#scrubs`, `#facials`, `#premium`, `#ayurveda`, `#yoga` (targets of homepage card links).

- [ ] **Step 1:** Write `pricing.html`: H1 "Spa Menu & Pricing — Kaashi Wellness, Rishikesh", intro paragraph (~120 words, human voice), seven price-table sections with the data above, policy sections, sticky call bar, meta/OG/canonical tags.
- [ ] **Step 2:** Cross-check all 35 price rows against this task's data table. Expected: exact match.
- [ ] **Step 3:** Commit: `feat: complete pricing page from brochure`.

### Task 4: Structured data, sitemap, robots

**Files:**
- Modify: `index.html` (add `DaySpa` + `FAQPage` JSON-LD), `pricing.html` (add `DaySpa` reference + `OfferCatalog` JSON-LD)
- Create: `sitemap.xml`, `robots.txt`

- [ ] **Step 1:** Add JSON-LD `DaySpa`: name Kaashi Wellness, address (streetAddress "Secret Waterfall Road, Near Arista Haven, Tapovan", locality Rishikesh, region Uttarakhand, postal 249192, country IN), geo ≈ 30.135, 78.325, both phones, `openingHoursSpecification` Mo–Su 10:00–20:00, priceRange ₹₹, areaServed Rishikesh/Tapovan/Laxman Jhula.
- [ ] **Step 2:** Add `FAQPage` JSON-LD mirroring the 8 on-page FAQs exactly; `OfferCatalog` on pricing with the seven categories.
- [ ] **Step 3:** `sitemap.xml` with both URLs (placeholder domain `https://kaashiwellness.com/`, noted for swap); `robots.txt` allowing all + sitemap line.
- [ ] **Step 4:** Validate JSON-LD parses: `python3 -c "import json,re..."` extracting script blocks. Expected: all parse.
- [ ] **Step 5:** Commit: `feat: structured data, sitemap, robots`.

### Task 5: Verification pass + preview publish

- [ ] **Step 1:** Word count re-check (≥2000), banned-phrase grep on both pages, keyword presence grep (each of the 3 localities appears in body copy of home).
- [ ] **Step 2:** Check both pages render at 360/768/1280 (browser or visual read-through of CSS); confirm no horizontal scroll, focus states visible.
- [ ] **Step 3:** Publish both pages as separate preview artifacts for user review (inter-page links won't navigate inside artifact previews; note this to user).
- [ ] **Step 4:** Commit any fixes: `fix: verification pass`.

## Self-review notes
- Spec coverage: all spec sections map to Tasks 1–5 (hosting/domain explicitly out of scope). ✓
- No placeholders beyond the deliberate domain placeholder in sitemap (flagged to user). ✓
- Class/anchor names consistent across Tasks 1–3. ✓
