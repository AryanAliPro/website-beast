---
name: web-beast
description: Design and build award-level, fully custom websites for any business or website type (trades, SaaS, restaurants, agencies, portfolios, e-commerce, personal brands, etc.) — the kind of site that feels handcrafted by a top Webflow/Framer studio, never a generic template. Use this skill whenever the user asks to design, build, redesign, or mock up a website, landing page, homepage, portfolio, product page, or any HTML/frontend surface — even if they just say "build me a site for X" without using words like "custom" or "award-winning." Also use it when a client project (e.g. a roofing, HVAC, cleaning, or construction site) needs a real, presentation-ready single-page build rather than a rough draft. Covers art direction, layout systems, real public imagery sourcing, GSAP/ScrollTrigger motion, SVG animation, Lottie micro-interactions, and a pre-delivery quality checklist. Do not use for plain content edits, copywriting-only requests, or non-visual coding tasks.
---

# Web Beast — Custom Website Design System

## The Standard

Every single website built under this skill is an entry into the World's Top and Hardest Web Design Competition — and the prize on the line is $1,000,000,000. Real money, real stakes, full effort, every time, no exceptions. This is not a throwaway mindset — it is the operating standard for how much creative energy, care, and craft goes into every layout, every section, every animation, every pixel.

The design, layout, colors, and animations must never look or feel generic, templated, or "AI-made." Never. Every section, every layout, every element must feel fully custom-built — carefully crafted, deliberately art-directed, as if a world-class design studio spent a week on it. Always avoid glassmorphism, cyber/neon color schemes, and simple glass-panel UI. Always avoid generic layouts, generic grids, generic gradients, and anything that feels reused from a template.

Use full creativity. Go further than the obvious choice. The goal is not "good" — the goal is that when a real person lands on this site, their reaction is an involuntary **"wow."** The site must give them a *vibe*, a *feeling* — something they immediately associate with the industry it represents, delivered through layouts and animations they have not seen a hundred times before. Look and feel like the award-winning Webflow/Framer sites that win real design awards — never like a generated landing page.

Bring real imagery (relevant, public, and actually loading), top-tier GSAP animation, Lottie, SVG animation, and micro-interactions — but never at the expense of a clean, professional hierarchy. Extraordinary and disciplined are not opposites here; the best entries in this competition are both.

## Step 0 — Read the brief before touching code

Identify, in order:

1. **Business/site type and industry** — what do they actually sell or do? A roofing company, a boutique law firm, a SaaS analytics tool, and a tattoo artist's portfolio should never share a visual language.
2. **Audience and tone** — who lands on this page, and what feeling should they leave with (trust, excitement, luxury, urgency, calm authority)?
3. **Core offer / primary action** — what's the one thing the page wants the visitor to do (call, book, buy, sign up, inquire)?
4. **Any constraints given** — brand colors, existing logo, must-have sections, tech stack, single-page vs multi-page.

If any of this is missing, make a reasonable assumption based on the business type stated and move forward — don't stall the build on a clarifying question unless the request is genuinely too vague to start (e.g. "build me a website" with no subject at all).

## Step 1 — Pick an art direction before writing any code

This is the step that separates a $1B-prize-winning entry from a template. Do not skip it, do not rush it, and do not default to the first idea that comes to mind — the first idea is usually the generic one. Push past it. Decide, and briefly note to yourself:

- **Layout rhythm**: asymmetric split, editorial full-bleed, magazine grid, diagonal flow, layered/overlapping — pick something that isn't "centered hero, then three even columns, repeat."
- **Visual motif**: one recurring shape, line, texture, or graphic device tied to the industry (a roofline angle for a roofing site, a stitched seam for a tailor, a topographic line for a landscaper).
- **Color story**: a palette that feels specific to this business, not a generic SaaS gradient. See `references/visual-system.md` for palette-building guidance.
- **Typography pairing**: one distinctive display face + one clean workhorse text face. Avoid the default system-font look.
- **Motion language**: what kind of movement fits this brand — snappy and confident, slow and cinematic, playful and bouncy? Pick before adding effects, not after.
- **One memorable interaction**: a single standout moment (a magnetic CTA, a scroll-scrubbed SVG drawing, a cursor-reactive hero, a Lottie moment) that the visitor will remember.

Never default to glassmorphism, frosted-glass panels, cyber/neon color schemes, random decorative gradient blobs, or stock "AI-generated SaaS" aesthetics unless the user explicitly asks for that specific style.

## Step 2 — Build real structure, not a placeholder

- Deliver a real, usable, complete page — not a wireframe or a "here's a starting point." If the user asked for a site, HTML/CSS/JS (or the framework already in use in the project) is the primary deliverable.
- Every section should be designed for its specific content, not dropped into a generic card grid. Cards are fine when the content is genuinely repeated items (services, team, pricing) — never nest cards inside cards, and never use cards as a default for everything.
- Keep a professional hierarchy throughout: clear primary heading, supporting text at a sane scale, deliberate spacing rhythm, consistent alignment system. Powerful headlines come from word choice and layout, not from cranking font-size to the max.
- Vary section-to-section composition (full-bleed image band, split content/media, offset columns, kinetic divider) while keeping one consistent design system underneath — variety in layout, consistency in tokens (color, type scale, spacing unit).

## Step 3 — Source real, relevant imagery

Use imagery that actually depicts the product, place, person, service, or material — not vague abstract decoration. Prefer real, inspectable photography over generic illustration.

- If an image-search tool is available, use it to find real, relevant, high-quality photos for the specific industry/subject before falling back to anything else.
- If sourcing image URLs directly for embedding in code, use stable public sources (e.g. Unsplash source/CDN URLs, Pexels, or images the user has provided/uploaded) and pick images that are specific to the business type — actual roofs, actual kitchens, actual product shots — not stock-photo-generic people-in-suits-shaking-hands unless that's genuinely the right fit.
- Never fabricate a broken or placeholder URL. If unsure an image URL will resolve, verify it or choose a source you know is reliable.

## Step 4 — Motion that makes them say "wow"

This is where the site earns its win. Bring the top-tier GSAP animations, Lottie moments, SVG animation, and micro-interactions the competition demands — animations that feel extraordinary, not the same three scroll-fades every generated site uses. Read `references/motion-recipes.md` for concrete GSAP/ScrollTrigger/SVG/Lottie implementation patterns, CDN links, and code recipes before building animations — it has the actual snippets so this file stays focused on judgment calls.

Quick-reference toolkit (details in the reference file):
- **GSAP + ScrollTrigger** for coordinated scroll-based reveals, pinning, and scrubbed timelines.
- **SVG stroke-draw animation** for logos, icons, dividers, and diagrams.
- **Lottie (lottie-web)** for a branded animated moment — a process illustration, loading state, or hero accent. Don't add it just to prove it's available; it should feel intentional.
- **Micro-interactions** on buttons, nav, gallery items, and form fields (magnetic buttons, hover states, cursor/tilt effects).
- **Mask reveals and parallax layers** used sparingly and kept readable — motion must never break layout stability or cause text overlap.

Favor a small number of coordinated, well-timed animations over a large number of disconnected effects. Restraint reads as premium; a page where everything wiggles reads as amateur.

## Step 5 — Technical delivery

- Single-file HTML is the default for a single-page site (CSS + JS inline or in the same file), unless the project already has an established multi-file structure — match whatever environment/skill conventions already apply (e.g. if a `frontend-design` skill or existing project structure is present, follow it).
- Pull GSAP, ScrollTrigger, and lottie-web from a CDN (see `references/motion-recipes.md` for exact links).
- Build mobile-first or verify mobile behavior explicitly: no animation should break, overlap, or become unreadable on a narrow viewport. Simplify or disable heavy scroll-pinning effects on small screens if they'd hurt usability.
- Make sure every interactive element (nav, CTAs, forms, galleries) actually works, not just looks like it does.

## Step 6 — Pre-delivery checklist

Before calling the build done, verify:

- [ ] The first viewport alone communicates the industry/brand — no generic "Welcome to our website" energy.
- [ ] Nothing about the layout, color system, or components reads as a copy-pasted template.
- [ ] Images are real, relevant to the specific business, and actually load.
- [ ] At least one deliberate, well-crafted motion moment exists (GSAP/ScrollTrigger, SVG animation, or Lottie) — and it's coordinated, not scattered.
- [ ] Typography is confident but readable; no oversized filler headlines used as a substitute for real design.
- [ ] Layout is consistent and responsive; nothing breaks or overlaps on mobile.
- [ ] No glassmorphism, cyber-neon palette, decorative gradient blobs, or other generic-AI-site tells are present, unless explicitly requested.
- [ ] Buttons, nav, forms, and hover/interaction states all function.
- [ ] No leftover placeholder text, debug comments, or explanations of the design embedded visibly in the page itself.

If a section fails this checklist, redo it. A $1B prize is not won with an average page — every single section has to earn the "wow," not just the hero.

## Reference files

- `references/motion-recipes.md` — concrete GSAP/ScrollTrigger timelines, SVG stroke-draw setup, Lottie integration, magnetic-button code, and CDN links. Read this before implementing any animation.
- `references/visual-system.md` — guidance for building an industry-specific color palette, type pairing, and layout motif so the site doesn't default to generic SaaS visual language.
