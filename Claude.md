# Walk Tokyo with Masa — Project Brief

## Overview

A mobile-first, single-page website for **Brother Masa**, a private local guide based in Tokyo, Japan. The site targets English-speaking tourists who want a relaxed, personal Tokyo experience — not a corporate group tour.

**Live URL:** https://saengsawat.github.io/tokyo-with-masa/
**Repo:** https://github.com/saengsawat/tokyo-with-masa
**File structure:** Single file — `index.html` (HTML + CSS + JS all bundled)

---

## Brand

| | |
|---|---|
| **Site name** | Walk Tokyo with Masa |
| **Tagline** | Explore Tokyo like a local friend. |
| **Tone** | Warm, friendly, calm, personal, authentic |
| **NOT** | Corporate, pushy, formal, rushed |

---

## Target Audience

- English-speaking tourists visiting Tokyo
- First-time visitors to Japan
- Couples, solo travelers, families
- People who want a local experience, not a packaged tour

---

## About Masa (for copy reference)

- Lives in Japan
- Enjoys yoga, jogging, food, city walking
- Speaks Japanese + conversational English
- Patient, friendly, thoughtful
- Guided his brother-in-law Andy (USA) around Tokyo for 2 nights / 3 days
- Handles: transportation, restaurant picks, cultural context, pacing

---

## Design System

### Colors
```
--cream:      #FAF8F3   (page background)
--ivory:      #F2EDE3   (card/section backgrounds)
--charcoal:   #252523   (primary text, dark sections)
--red:        #B84131   (accent — torii gate red)
--tan:        #C9A97A   (secondary accent)
--tan-light:  #E8DABD   (borders, dividers)
--muted:      #7A766E   (body/secondary text)
--white:      #FFFFFF
```

### Typography
```
Display / headings:  Cormorant Garamond (serif)
Body:                Nunito (sans-serif)
Japanese accents:    Shippori Mincho
Japanese mode (body.lang-ja headings): Shippori Mincho
```

### Layout
- Mobile-first, max-width 480px → 900px → 1100px
- Rounded cards: `border-radius: 16px`
- Shadows: `--shadow-sm`, `--shadow-md`
- Scroll reveal: `.reveal` + IntersectionObserver

---

## Current Sections

| # | Section ID | Description |
|---|---|---|
| 1 | `#home` | Hero with full-bleed Tokyo photo, headline, 2 CTAs |
| 2 | `#about` | Masa's photo, bio, personality tags |
| 3 | `#tours` | 4 tour cards (Classic, Food, Modern, Custom) |
| 4 | `#why` | 8 benefit cards on dark background |
| 5 | `#sample` | Timeline itinerary for a sample day |
| 6 | `#testimonial` | Andy's quote + star rating |
| 7 | `#contact` | Info chips + booking inquiry form (non-functional) |

---

## Features Already Built

- ✅ Mobile-first responsive layout
- ✅ Sticky nav with scroll shadow
- ✅ Smooth scroll navigation
- ✅ Scroll-reveal animations
- ✅ Hover effects on cards and buttons
- ✅ Bilingual toggle: English / 日本語 (full translation)
- ✅ Japanese font swap when `body.lang-ja` is active
- ✅ Fade transition on language switch
- ✅ All images from Unsplash (no local assets)
- ✅ Contact form (non-functional — UI only)

---

## i18n System

All translatable strings use `data-i18n="key"` on HTML elements.
Placeholders use `data-i18n-placeholder="key"`.

Translation dictionary is in the `<script>` block at the bottom of `index.html`:
```js
const T = {
  en: { ... },
  ja: { ... }
}
```

To add a new translated string:
1. Add `data-i18n="your_key"` to the HTML element
2. Add `your_key: "English text"` to `T.en`
3. Add `your_key: "日本語テキスト"` to `T.ja`

---

## Known Limitations / To-Do

- [ ] Contact form is non-functional (needs a backend or form service like Formspree / Netlify Forms)
- [ ] No real photos of Masa (using Unsplash placeholders)
- [ ] No actual pricing information
- [ ] No booking/calendar integration
- [ ] Meta tags / SEO not yet optimized
- [ ] No favicon
- [ ] No Open Graph tags (for link previews when sharing)

---

## Improvement Ideas (Future)

### Easy wins
- Add favicon (a simple torii gate or Masa's initial)
- Add Open Graph meta tags so the link looks good when shared on LINE, WhatsApp, iMessage
- Add a WhatsApp or LINE contact button (Masa likely uses these)
- Optimize meta description for SEO

### Medium effort
- Connect contact form to Formspree (free, no backend needed — just swap the form action)
- Add a real photo of Masa when available
- Add a FAQ section (common tourist questions)
- Add a simple pricing section or "from $X" indicator

### Bigger features
- Add a second language: Simplified Chinese (大きな市場 for Tokyo tourism)
- Add Google Maps embed showing key tour stops
- Add a photo gallery section
- Custom domain: `walktokyowithmasa.com`

---

## How to Work on This with Claude Code

When asking Claude Code to make changes, give context like:

> "This is a single-file HTML site. All CSS and JS are inside index.html. The design uses CSS variables defined at the top of the `<style>` block. The i18n system uses data-i18n attributes and a T object in the script block."

**Example prompts:**
- *"Add a favicon using a torii gate emoji SVG"*
- *"Add Open Graph meta tags so the site previews nicely when shared on WhatsApp"*
- *"Connect the contact form to Formspree — the endpoint is [your formspree URL]"*
- *"Add a WhatsApp contact button that links to Masa's number"*
- *"Add a new section for FAQ between the testimonial and contact sections"*
- *"Add Simplified Chinese as a third language option"*

---

## Deployment

Hosted on **GitHub Pages**.

To deploy changes:
```bash
git add .
git commit -m "describe what you changed"
git push origin main
```

GitHub Pages auto-deploys within ~1 minute of a push.

---

*Last updated: June 2025*
*Built by Andy Saengsawat with Claude (Anthropic)*
