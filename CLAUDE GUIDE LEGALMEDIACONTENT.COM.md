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
**Type:** Single HTML file with all CSS and JavaScript inline. No build process. Pure static site.

**Images:** Photos live in the `images/` folder (`hero-consultation.jpg`, `about-signing.jpg`). All are free Pexels photos, cropped and compressed. The "Content that works for you" visual is a CSS mockup of a law firm social post, not a photo.

**Google Fonts used:** Source Serif 4 (headings) and Jost (body)

**External dependencies:** Google Fonts and Formspree (contact form) only.

---

## Design System

Redesigned October 2026: open editorial layout, hairline dividers instead of boxed cards, photo hero, animated SEO search illustration.

### Color Palette
```css
--navy: #15213b;
--navy-2: #1d2b4b;
--gold: #c6a456;
--gold-deep: #85691f;   /* gold text on light backgrounds */
--paper: #fbfaf7;       /* main light background */
--linen: #f2eee6;       /* alternate light sections */
--line: #e2dccf;        /* hairline dividers */
--ink: #1c2332;         /* body text */
--muted: #4b5263;       /* secondary text */
--on-navy: #f1ede4;
--on-navy-muted: #c4cad7;
```

### Typography
- **Headings:** Source Serif 4, weight 600 (blog titles 700)
- **Body:** Jost, 1.15rem, line height 1.72
- No uppercase eyebrow labels; sections lead with the heading

### Key Layout Rules
- `.wrap` is the max 1200px container with responsive side gutters
- Lists are separated by 1px hairlines (`var(--line)`), not cards
- No faces in the hero; the About photo shows hands signing documents at a table (no faces)

---

## Website Sections (in order)

1. **Navigation** over the hero: logo, SEO, Content, About, Blog, "Get started"
2. **Hero** with consultation photo, headline "Marketing by lawyers, for lawyers.", free SEO callout with explanation, CTA
3. **What we deliver** strip: Websites, Articles, Social media, Newsletters
4. **SEO** section with animated search results where "Your firm" climbs to first
5. **Why** ("Too many lawyers & firms are invisible online"), with pull quote, example wins list, three points with icons
6. **Content that works for you**: social post mockup plus six content types
7. **One article becomes many assets**: diagram from an article to LinkedIn, Facebook, newsletter, website
8. **About** ("We speak your language because we know it") with photo and credentials
9. **Blog**: three articles as a list with bold titles; clicking opens the full article
10. **Contact** form (Formspree) and footer

---

## Article Modal System

Each blog row is a `<button class="post" data-article="articleN">`. Clicking it removes the `hidden` attribute from `#articleN` (`.article-overlay`). Close button, clicking outside, or Escape closes it. Modal IDs: `article1`, `article2`, `article3`.

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

- **Hero image** is self-hosted in `images/`, so it loads on mobile.
- **All CSS** must remain in the main `<style>` block in `<head>`. A previous bug was caused by a `<style>` block in the body which rendered as a grey overlay.
- **Class names:** the blog rows use `.post`; the social mockup uses `.sm-*` classes. Keep them separate.

---

## Deployment

- **Hosting:** GitHub Pages (free, public repository)
- **Domain:** legalmediacontent.com (registered on Namecheap)
- **DNS:** Managed through Namecheap, pointed to GitHub Pages
- **SSL:** Provided automatically by GitHub Pages

---

## Future Work / On the Horizon

- Build out law firm client website templates (Template 1 warm/family-friendly is partially built at `law-firm-template-1.html`)
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
Before writing any code, commit to a clear aesthetic direction. This site uses a **refined, modern editorial** aesthetic. Navy and gold with warm off-white sections, open layouts separated by hairlines instead of boxes, real photography, and a serif display face paired with an elegant sans body. Every design decision should reinforce that this is a premium, attorney-grade service — not a generic marketing agency.

Ask before coding:
- Does this feel consistent with the navy/gold/paper palette?
- Does this use Source Serif 4 for headings and Jost for body?
- Does this have intentional spacing and hierarchy?
- Would an attorney trust a firm that looked this way?

### Typography Rules
- **Display/headings:** Source Serif 4 for all h1, h2, h3, section titles, article titles
- **Body/UI:** Jost for body copy, labels, buttons, nav, form fields
- Never use Arial, Inter, Roboto, or system fonts as the primary face

### Color Rules
Always use the CSS variables listed under Design System above. Never hardcode colors that exist as variables.

### Motion & Interaction
- Motion: hero entrance and a slow photo drift; the SEO search results loop while visible and "Your firm" pops at first place; gold pulses travel along the "One article becomes many assets" lines; the social post rotates notifications and taps Like every few seconds; the example wins list fades in
- Motion runs only when the small script in `<head>` adds the `motion` class to `<html>`, and is skipped for visitors who prefer reduced motion
- Hover states on cards: subtle translateY(-2px) and box-shadow
- Hover states on buttons: background color shift, subtle transform
- Keep animations fast (0.2s for hovers, 0.6s for page load reveals)

### Spatial Composition
- Generous padding on sections: 6rem 5% default
- Max-width 1200px centered containers via `.section-inner`
- Two-column grids for content that benefits from side-by-side layout
- Prefer open lists with 1px hairlines (var(--line)) over boxed cards
- Keep corners sharp (2px to 4px radius); this is a law firm aesthetic

### What Makes This Site Memorable
The single most important thing: the combination of the dark navy sections with gold accents and cream typography feels authoritative and premium in a way that most law firm sites do not. Every new element should reinforce that contrast and that premium feel. When in doubt, ask: does this look like it belongs on a BigLaw firm's site?

### Things to Avoid
- Purple gradients, rounded pill shapes, pastel colors — wrong aesthetic entirely
- Generic icon libraries that look like every other site
- Overcrowded layouts — generous whitespace is intentional
- Multiple font weights creating visual noise — stick to the defined type scale
- Animations that are slow, bouncy, or call too much attention to themselves
