
<style>
  .md-wrap { font-family: var(--font-mono); font-size: 13px; line-height: 1.6; color: var(--color-text-primary); background: var(--color-background-secondary); border-radius: var(--border-radius-lg); border: 0.5px solid var(--color-border-tertiary); padding: 1.5rem; white-space: pre-wrap; word-break: break-word; position: relative; }
  .copy-btn { position: absolute; top: 1rem; right: 1rem; font-family: var(--font-sans); font-size: 12px; padding: 4px 12px; background: transparent; border: 0.5px solid var(--color-border-secondary); border-radius: var(--border-radius-md); cursor: pointer; color: var(--color-text-secondary); }
  .copy-btn:hover { background: var(--color-background-primary); color: var(--color-text-primary); }
</style>
<div style="padding: 0.5rem 0;">
  <div class="md-wrap" id="mdblock">
    <button class="copy-btn" onclick="copyMd()">Copy</button>
    <span id="mdtext"># CLAUDE.md — CompSF IT &amp; Cyber Solutions Website

## Project Overview
- **Business:** CompSF IT &amp; Cyber Solutions
- **Site type:** IT Services &amp; Cybersecurity business website
- **Pages:** Home / Landing, Services, About, Contact
- **Tone &amp; feel:** Friendly, approachable, trustworthy — warm tech energy, not cold corporate
- **Audience:** Small-to-mid businesses seeking IT support and cyber protection in the SF Bay Area

---

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

---

## Brand Assets
- Always check the `brand_assets/` folder before designing.
- It may contain: logo, color palette, style guide, photography, icons.
- If assets exist, **use them** — do not use placeholders where real assets are available.
- If a logo is present, use it in the header and footer.
- If a color palette is defined, use those exact values — do not invent brand colors.
- If no color palette is found, derive a warm-but-professional custom palette — avoid default Tailwind colors entirely.

---

## Page Structure

### Home / Landing
- Hero with headline, subheadline, and a clear CTA ("Get a Free Consultation" or similar)
- Brief value proposition (3 pillars: e.g. Fast Response, Friendly Support, Secure Systems)
- Services preview (3–4 cards linking to Services page)
- Trust indicators (years in business, clients served, certifications, testimonials)
- Final CTA section

### Services
- Intro headline and short paragraph
- Service cards (each with icon, title, short description)
- Include categories such as: IT Support, Cybersecurity, Network Setup, Cloud Solutions, Managed Services
- CTA at the bottom of the page

### About
- Company story / mission statement
- Team section (photos or illustrated avatars with names/roles)
- Values section (friendly, local, expert)
- CTA to Contact

### Contact
- Contact form (Name, Email, Phone, Message, Submit)
- Business address, phone, email
- Optional: embedded map or service area note (SF Bay Area)
- Response time expectation copy ("We respond within 1 business day")

---

## Reference Images
- If a reference image is provided: match layout, spacing, typography, and color exactly. Use placeholder content only where real assets are absent.
- If no reference image: design from scratch with high craft (see guardrails below).
- Screenshot output, compare against reference, fix mismatches, re-screenshot. Do at least 2 comparison rounds. Stop only when no visible differences remain or user confirms.

---

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL.
- Start the dev server: `node serve.mjs` (serves the project root at `http://localhost:3000`)
- `serve.mjs` lives in the project root. Start it in the background before taking any screenshots.
- If the server is already running, do not start a second instance.

---

## Screenshot Workflow
- Puppeteer is installed — update path to match your local machine before first use.
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots auto-save to `./temporary screenshots/screenshot-N.png` (never overwritten).
- Optional label: `node screenshot.mjs http://localhost:3000 label`
- After screenshotting, read the PNG with the Read tool and analyze it directly.
- Be specific in comparisons: "heading is 32px but reference shows ~24px", "card gap is 16px but should be 24px"
- Check: spacing/padding, font size/weight/line-height, colors (exact hex), alignment, border-radius, shadows, image sizing

---

## Output Defaults
- Single `index.html` file per page, all styles inline, unless instructed otherwise
- Tailwind CSS via CDN: `&lt;script src="https://cdn.tailwindcss.com"&gt;&lt;/script&gt;`
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Mobile-first responsive

---

## Anti-Generic Guardrails
- **Colors:** Never use default Tailwind palette (indigo-500, blue-600, etc.). Use brand colors from `brand_assets/` or derive a custom palette.
- **Shadows:** Never flat `shadow-md`. Use layered, color-tinted shadows with low opacity.
- **Typography:** Never use the same font for headings and body. Pair a display/serif with a clean sans. Apply tight tracking (`-0.03em`) on large headings, generous line-height (`1.7`) on body.
- **Gradients:** Layer multiple radial gradients. Add grain/texture via SVG noise filter for depth.
- **Animations:** Only animate `transform` and `opacity`. Never `transition-all`. Use spring-style easing.
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states. No exceptions.
- **Images:** Add a gradient overlay (`bg-gradient-to-t from-black/60`) and a color treatment layer with `mix-blend-multiply`.
- **Spacing:** Use intentional, consistent spacing tokens — not random Tailwind steps.
- **Depth:** Surfaces should have a layering system (base → elevated → floating) — not all at the same z-plane.
- **Friendly tone in copy:** Avoid jargon-heavy headlines. Write like a helpful neighbor, not a sales brochure.

---

## Hard Rules
- Do not add sections, features, or content not in the reference
- Do not "improve" a reference design — match it
- Do not stop after one screenshot pass
- Do not use `transition-all`
- Do not use default Tailwind blue/indigo as primary color
- Do not use cold, sterile corporate aesthetics — CompSF is warm and human</span>
  </div>
</div>
<script>
function copyMd() {
  const raw = document.getElementById('mdtext').innerText;
  navigator.clipboard.writeText(raw).then(() => {
    const btn = document.querySelector('.copy-btn');
    btn.textContent = 'Copied!';
    setTimeout(() => btn.textContent = 'Copy', 2000);
  });
}
</script>
