# CLAUDE.md — Legal Media & Content Co. Website Project

This file provides full context for the Claude extension in VS Code to continue building and maintaining the Legal Media & Content Co. website.

---

## Business Overview

**Business name:** Legal Media & Content Co.
**Domain:** legalmediacontent.com
**Owner:** Aharon, business development analyst at Cleveland Clinic, night law student at the University of Akron graduating in approximately one year.

**What the business does:** Law firm web design, content creation, and media management for solo practitioners and small law firms. Services include website builds, monthly content packages (case articles, legal updates, thought leadership), social media management, and press placement.

**Core pitch to attorneys:** Articles are compounding assets. Unlike a one-time ad, a published article lives on the internet forever, builds search presence, and accelerates referrals by keeping the attorney's name visible to potential clients and referral sources.

**Target clients:** Solo practitioners and small law firms with no online presence, outdated websites, or attorneys who want to publish but don't have time.

---

## Service Packages & Pricing

Pricing is NOT displayed on the website. These are internal reference only.

- **Starter:** $400/mo — 2 articles/mo, 4-6 social posts
- **Growth:** $750/mo — 4 articles/mo, 12-15 social posts, monthly strategy call
- **Authority:** $1,200/mo — 6 articles/mo, full social management 20+ posts, newsletter, quarterly strategy, press placement coordination
- **Add-ons:** Press placement ($300-500), video ($400/mo), social only ($200-400/mo), website content updates ($150/update)

**Editorial policy:** Articles are one-and-done. No revision rounds offered.

---

## Website File

**Filename:** `index.html`
**Type:** Single self-contained HTML file — all CSS and JavaScript are inline. No separate stylesheets, scripts, or asset folders. No build process required. Pure static site.

**Google Fonts used:** Playfair Display, DM Sans (loaded via CDN in the `<head>`)

**External dependencies:** Google Fonts CDN only. No other external libraries or frameworks.

---

## Design System

### Color Palette
```css
--navy: #1a2744;
--gold: #c9a84c;
--cream: #f8f6f1;
--cream-dark: #ede9e0;
--white: #ffffff;
--text: #2d3748;
--gray: #6b7280;
```

### Typography
- **Headings:** Playfair Display (serif) — used for h1, h2, h3, section titles
- **Body:** DM Sans (sans-serif) — used for all body copy, labels, navigation
- **Eyebrow labels:** DM Sans, uppercase, letter-spacing 0.18em, gold color

### Key CSS Classes
- `.section-eyebrow` — gold uppercase label above section titles (font-size: 1.05rem)
- `.section-title` — main section heading (Playfair Display, navy, clamp 2.2rem to 2.75rem)
- `.section-sub` — subtitle below section title (DM Sans, gray)
- `.section-inner` — max-width 1200px centered container for all sections
- `.btn-primary` — navy background, white text, primary CTA button
- `.btn-outline` — outlined navy button, secondary CTA
- `.hero-eyebrow` — gold uppercase label in hero section (font-size: 1.05rem)

---

## Website Sections (in order)

1. **Navigation** — fixed top nav, logo left, links right, "Get in touch" CTA button
2. **Hero** — full viewport, courtroom background image, headline "Your cases deserve to be told.", subheadline, CTA button, hero card with stats
3. **Why (The Problem We Solve)** — cream background, explains the visibility problem attorneys face
4. **Content Types (What We Write)** — cream background, grid of content service cards
5. **About** — navy background, two-column layout: text left, credentials right (Legal Training, Marketing Experience, Niche Focus with SVG icons)
6. **Blog/Resources** — white background, 3 article cards that open in modal overlays on click
7. **Contact** — cream background, contact form (first name, last name, email, firm name, practice area dropdown, message)
8. **Footer** — navy background, logo, nav links, copyright

---

## Article Modal System

Three blog articles open in modal overlays when their cards are clicked. The system uses:

```javascript
function openArticle(id) {
  document.getElementById(id).classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeArticle(id) {
  document.getElementById(id).classList.remove('open');
  document.body.style.overflow = '';
}
```

- Modal IDs: `article1`, `article2`, `article3`
- CSS class `.article-overlay` is `display: none` by default
- `.article-overlay.open` sets `display: flex`
- Clicking outside the modal or pressing Escape closes it
- All modal CSS is in the main `<style>` block in `<head>` — NOT in a separate mid-body style block

### Article 1
- **Tag:** Content Strategy
- **Title:** Why attorneys who publish regularly win more referrals
- **Date:** March 2025

### Article 2
- **Tag:** Attorney Marketing
- **Title:** The case article formula: turning a win into a client magnet
- **Date:** February 2025

### Article 3
- **Tag:** Legal Updates
- **Title:** Bar rules on attorney advertising: what your content can and can't say
- **Date:** January 2025 — written to be jurisdiction-neutral, references ABA Model Rules 7.1, 7.2, 7.3

---

## Copy & Content Rules

These rules must be followed in ALL copy written for this website:

1. **No em dashes anywhere** — restructure sentences instead. Never use — in any copy.
2. **No hyphens used as dashes** — restructure sentences instead.
3. **No geographic references** — do not mention Ohio, Cleveland, or any specific location in website copy.
4. **No pricing on the website** — pricing is never displayed publicly.
5. **No revision rounds language** — do not mention or imply revision rounds are offered.
6. **No "solo practitioners" alone** — always say "law firms and solo practitioners" or just "law firms."
7. **Straight apostrophes only in JavaScript** — curly/smart apostrophes break JS functions. Always use straight apostrophes (`'`) inside any JavaScript strings.
8. **Articles are one-and-done** — this editorial policy should never be contradicted in copy.

---

## About Section — Credentials (Right Column)

Three credential items with inline SVG icons in gold (#c9a84c):

1. **Legal Training** — Juris Doctor. We write with the knowledge of an attorney, not a generalist copywriter.
2. **Marketing Experience** — Background in institutional content strategy and business development
3. **Niche Focus** — We work exclusively with law firms. No diluted attention from other industries.

The right column has `padding-top: 9.2rem` to align the credentials with the paragraph text on the left rather than the eyebrow/heading.

---

## Contact Form Fields

- First name
- Last name
- Email
- Firm name
- Practice area (dropdown with 18 options)
- Tell us about your firm (textarea)

No email address is displayed publicly on the site. Form uses a `handleSubmit` JavaScript function that shows a confirmation message on submit.

---

## Known Issues & Notes

- **Courtroom hero image** (`https://cdn.loc.gov/service/pnp/highsm/03400/03427v.jpg`) does not load on mobile due to LOC hotlink blocking. The site uses a Pexels image as a CSS background fallback. Permanent fix is to self-host the image. When deployed to a live domain this may resolve itself — test after deployment.
- **All article modal CSS** must remain in the main `<style>` block in `<head>`. A previous bug was caused by a `<style>` block in the body which rendered as a grey overlay.
- **Blog card body** has `background: var(--navy)` so the white/cream text is visible.
- **"From the blog" heading** uses `color: #f0ece4 !important` (ivory) and the subtitle uses `color: #c9c0b0`.

---

## Deployment

- **Hosting:** GitHub Pages (free, public repository)
- **Domain:** legalmediacontent.com (registered on Namecheap)
- **DNS:** Managed through Namecheap, pointed to GitHub Pages
- **SSL:** Provided automatically by GitHub Pages

---

## Future Work / On the Horizon

- Fix courtroom hero image for mobile (self-host the image file)
- Build out law firm client website templates (Template 1 warm/family-friendly is partially built at `law-firm-template-1.html`)
- Add Formspree or similar to contact form so submissions actually arrive via email
- Cold outreach script for calling attorneys
- Client proposal/one-pager template
- Service agreement/contract template
- Begin cold outreach to attorneys with weak online presence

---

## What Not To Do

- Do not add a `<style>` block anywhere in the `<body>` — all CSS goes in `<head>`
- Do not use em dashes or hyphens as dashes in any copy
- Do not display pricing
- Do not reference specific states or cities in website copy
- Do not use curly apostrophes inside JavaScript strings
- Do not add external JavaScript libraries unless absolutely necessary — keep the site self-contained
- Do not break the single-file structure — all CSS, JS, and HTML stays in one `index.html` file

---

## Frontend Design Skill

When building or modifying any UI element on this site, follow these principles:

### Design Thinking
Before writing any code, commit to a clear aesthetic direction. This site uses a **luxury/refined editorial** aesthetic. Dark navy backgrounds, gold accents, cream tones, serif display typography paired with clean sans-serif body text. Every design decision should reinforce that this is a premium, attorney-grade service — not a generic marketing agency.

Ask before coding:
- Does this feel consistent with the navy/gold/cream palette?
- Does this use Playfair Display for headings and DM Sans for body?
- Does this have intentional spacing and hierarchy?
- Would an attorney trust a firm that looked this way?

### Typography Rules
- **Display/headings:** Playfair Display — used for all h1, h2, h3, section titles, article titles
- **Body/UI:** DM Sans — used for all body copy, labels, buttons, nav, form fields
- Never use Arial, Inter, Roboto, or system fonts
- Eyebrow labels: DM Sans, uppercase, letter-spacing 0.18em, 1.05rem, gold color

### Color Rules
Always use CSS variables. Never hardcode colors that exist as variables.
```css
--navy: #1a2744;      /* primary dark background */
--gold: #c9a84c;      /* accent, CTAs, highlights */
--cream: #f8f6f1;     /* light section backgrounds */
--cream-dark: #ede9e0; /* borders, card backgrounds */
--white: #ffffff;     /* pure white backgrounds */
--text: #2d3748;      /* primary body text */
--gray: #6b7280;      /* secondary/muted text */
```

### Motion & Interaction
- Use CSS animations for page load reveals (fadeUp keyframe already defined in the file)
- Hover states on cards: subtle translateY(-2px) and box-shadow
- Hover states on buttons: background color shift, subtle transform
- Keep animations fast (0.2s for hovers, 0.6s for page load reveals)
- Use `animation-delay` for staggered reveals on grouped elements

### Spatial Composition
- Generous padding on sections: 6rem 5% default
- Max-width 1200px centered containers via `.section-inner`
- Two-column grids for content that benefits from side-by-side layout
- Cards use subtle borders (1px solid var(--cream-dark)) rather than heavy shadows
- Border-radius: 4px on cards (keep it sharp, not rounded — this is a law firm aesthetic)

### What Makes This Site Memorable
The single most important thing: the combination of the dark navy sections with gold accents and cream typography feels authoritative and premium in a way that most law firm sites do not. Every new element should reinforce that contrast and that premium feel. When in doubt, ask: does this look like it belongs on a BigLaw firm's site?

### Things to Avoid
- Purple gradients, rounded pill shapes, pastel colors — wrong aesthetic entirely
- Generic icon libraries that look like every other site
- Overcrowded layouts — generous whitespace is intentional
- Multiple font weights creating visual noise — stick to the defined type scale
- Animations that are slow, bouncy, or call too much attention to themselves
