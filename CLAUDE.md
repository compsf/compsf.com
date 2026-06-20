# CLAUDE.md — CompSF IT & Cyber Solutions Website

## Project Overview
- **Business:** CompSF IT & Cyber Solutions
- **Domain:** compsf.com
- **Repo:** https://github.com/compsf/compsf.com (branch: main)
- **Hosting:** GitHub Pages — push to main = live in ~1–2 min
- **Site type:** IT Services & Cybersecurity business website (SF Bay Area)
- **Tone:** Friendly, approachable, warm tech energy — not cold corporate
- **Audience:** Small-to-mid businesses seeking IT support and cyber protection

---

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

---

## Brand Colors (exact tokens — use these, never invent)
```
--black:        #1c1c1c
--charcoal:     #2d2d2d
--orange:       #e07020   ← primary CTA color
--blood-orange: #bf3500   ← hover states, accents
--sf-red:       #9b1520
--white:        #ffffff
--off-white:    #f8f8f8
--light-grey:   #f2f2f2
--border:       #e0e0e0
--text-muted:   #666666
--text-light:   #999999
```

## Typography
- **Headings:** `WildanCar` (file: `Wildan carFont - Adegoke.ttf` in project root & `brand_assets/`)
- **Body:** `Inter`, sans-serif
- Heading tracking: `-0.03em` on large headings; body line-height: `1.7`
- Never use the same font for headings and body

---

## Key Files
- `index.html` — single-file site (~77KB), all styles inline, Tailwind via CDN
- `serve.mjs` — local dev server (port 3000)
- `screenshot.mjs` — Puppeteer screenshots → `./temporary screenshots/`
- `brand_assets/` — logos, style guide, custom font, photography
- `thank-you.html` — form submission success page
- `404.html` — custom 404
- `og-image.html` / `og-image.png` — social share image
- `CompSF_Quote_Generator.html` — standalone internal tool
- `email-signature.html`, `shahar-signature-standalone.html`, `dareyl-signature-standalone.html`
- `internal/` — internal tools (not part of public site)

## Sub-pages (each has its own folder with index.html)
- `about/` and `about-us/` — About page
- `services/` and `what-we-do/` — Services page
- `contact/` and `contact-us/` — Contact page

---

## Team Members (with photo filenames)
| Name | Role | Photo file |
|------|------|------------|
| Shahar Geva | Founder & CEO | `Shahar-ProPic.jpg` |
| Tommy R. | Helpdesk & Support Lead | `Tommy.jpg` |
| David Kim | Systems & Automation Engineer | `David.Kim.png` |
| Sarah Chen | Cloud Solutions Specialist | `Sarah.C.png` |
| Avi G. | Cybersecurity & Special Projects Advisor | `Avi.Gold.png` |
| Nissim Buzaglo | Senior Web Developer | `Nissim.B.png` |

---

## Contact & Business Info
- **Address:** 548 Market Street, San Francisco CA 94104
- **Service area:** SF Bay Area (on-site + remote)
- **Hours:** Mon–Fri 9am–5pm

---

## Logo Files (in root and brand_assets/)
- `Logo_CompSF_wTagline_Color_01_RGB.png` — primary color logo
- `Logo_CompSF_wTagline_Color_02_RGB.png` — alternate color
- `Logo_CompSF_wTagline_White_02_RGB.png` — white (for dark backgrounds)
- `Logo_CompSF_wTagline_Black_02_RGB.png` — black (for light backgrounds)
- `CompSF Image Logo.png` — image-only logo (no tagline)
- `compsf-logo-v3.png` — latest logo version
- `CompSF-single-LOGO symbol.jpg` — symbol only

---

## Hero Video
- Primary: `Homepage-CompSF-Video_v2.mp4`
- Poster: `Homepage-Video-Poster.png`
- Mobile: `display:block; width:100%` (never `display:none` at mobile breakpoints)
- Add `preload="auto"` + IntersectionObserver fallback for mobile autoplay

---

## Google Reviews (live slider)
- **API Key:** `AIzaSyCmqX39_2MSwPE-1j72wiV7GIprUQYJzlg` (restricted to compsf.com — won't work on localhost)
- **Place ID:** `ChIJf9p5e2KAhYAR1gVravhN_to`
- **Use:** legacy `google.maps.places.PlacesService.getDetails()` — returns `review.text` as a plain string
- **Do NOT use:** new Places JS library (`Place.fetchFields`) — silently drops review text
- **Do NOT use:** REST API `fetch()` — fails due to CORS on GitHub Pages
- Sort: written text + non-Hebrew first → written text + Hebrew second → star-only excluded
- Hebrew names detected with `/[֐-׿]/`; no-photo Hebrew reviewers get a generic SVG icon
- Slider: prev/next buttons, auto-scrolls every 5s, pauses on hover, responsive (3/2/1 cards)

---

## Local Dev Server
- Start: `node serve.mjs` (serves project root at `http://localhost:3000`)
- Always start before taking screenshots
- Never screenshot a `file:///` URL

## Screenshot Workflow
- Command: `node screenshot.mjs http://localhost:3000 label`
- Screenshots auto-save to `./temporary screenshots/` (never overwritten)
- After screenshotting, read the PNG with the Read tool and analyze directly
- Check: spacing/padding, font size/weight, colors (exact hex), alignment, border-radius, shadows, image sizing
- Do at least 2 comparison rounds; stop only when no visible differences remain

---

## Output Defaults
- Single `index.html` per page, all styles inline, unless told otherwise
- Tailwind CSS via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Mobile-first responsive

---

## Anti-Generic Guardrails
- **Colors:** Use the token list above. Never use default Tailwind palette (indigo-500, blue-600, etc.)
- **Shadows:** Never flat `shadow-md`. Use layered, color-tinted shadows with low opacity
- **Typography:** WildanCar headings + Inter body — never swap or mix up
- **Gradients:** Layer multiple radial gradients. Add grain/texture via SVG noise filter for depth
- **Animations:** Only animate `transform` and `opacity`. Never `transition-all`. Use spring-style easing
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states
- **Images:** Add gradient overlay (`bg-gradient-to-t from-black/60`) and color treatment with `mix-blend-multiply`
- **Spacing:** Intentional, consistent spacing tokens — not random Tailwind steps
- **Depth:** Surfaces should layer (base → elevated → floating) — not all at same z-plane
- **Copy tone:** Write like a helpful neighbor, not a sales brochure. No jargon-heavy headlines

---

## Hard Rules
- Do not add sections, features, or content not in the reference
- Do not "improve" a reference design — match it
- Do not stop after one screenshot pass
- Do not use `transition-all`
- Do not use default Tailwind blue/indigo as primary color
- Do not use cold, sterile corporate aesthetics — CompSF is warm and human
- Do not hide the hero video on mobile

---

## Stable Restore Point
- Git tag: `v1.0-reviews-working` (tagged on GitHub — safe fallback if things break)
