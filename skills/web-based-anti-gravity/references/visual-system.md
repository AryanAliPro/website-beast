# Visual System Guidance

How to build a color, type, and layout-motif system that reads as specific to the business rather than generic. Use this during Step 1 (art direction) of SKILL.md.

## Building an industry-specific palette

Don't start from "what colors look nice together" — start from "what does this industry/material/mood actually look like in the real world," then refine for contrast and accessibility.

Examples of grounding a palette in the subject rather than a template default:

- **Roofing/construction**: charcoal and slate greys, weathered rust-orange or safety-amber accent, warm off-white — evokes materials (asphalt, metal, timber) rather than a generic blue-gradient "trust" palette.
- **Landscaping/outdoor**: deep forest green, warm terracotta, soft stone beige — avoid neon/lime greens, which read as generic "eco app" rather than actual plant life.
- **Legal/professional services**: deep navy or ink black, a single warm metallic accent (brass, muted gold), cream or paper-white background — signals gravity and permanence, not a SaaS dashboard.
- **Restaurant/hospitality**: palette pulled from the actual cuisine or interior — e.g. a wine-and-charcoal palette for a steakhouse, warm terracotta and olive for Mediterranean, deep lacquer red and black for a ramen bar.
- **Tech/SaaS**: it's fine to use a confident brand color here, but pair it with genuine restraint elsewhere (neutral greys, one accent, no rainbow gradients) and a distinct type choice so it doesn't collapse into the default indigo-to-violet gradient look.

Rule of thumb: one dominant neutral, one deep anchor color, one accent used sparingly for CTAs/highlights. Avoid palettes that could be relabeled and used for a completely different business without anyone noticing.

## Typography pairing

Pick a **display face** (used for headlines, sparingly) with real character — a serif with personality, a condensed display sans, a slab, or a distinctive geometric sans — paired with a **workhorse text face** that's simply excellent at readability (a clean humanist or grotesk sans, or a readable serif for longer editorial copy).

Avoid:
- Using the browser default system font stack as the final choice (fine as a fallback, not as the design).
- Pairing two display faces against each other — pick one voice for headlines and let the body text stay quiet.
- Making every heading the same enormous size as a substitute for genuine hierarchy — vary weight, size, and spacing deliberately across H1/H2/H3/body/caption.

Good free pairings to consider (via Google Fonts or similar), matched loosely to mood:
- Editorial/premium: a serif like Fraunces or Source Serif + a clean sans like Inter or Public Sans.
- Bold/modern: a condensed display sans like Archivo or Bricolage Grotesque + Inter or Work Sans for body.
- Technical/precise: a geometric sans like Space Grotesk for headings + a neutral grotesk like Inter for body.
- Warm/human: a rounded or humanist sans like Nunito Sans or Sora + a readable serif or sans for body.

Whatever is chosen, use it consistently — don't let a single project drift across three unrelated typefaces.

## Layout motifs tied to the industry

A layout motif is a small recurring structural or graphic idea that ties the design to the subject, reinforced across sections rather than used once and abandoned. Examples:

- A diagonal roofline angle used consistently as a section-divider shape for a roofing company.
- A stitched-line SVG motif running along section edges for a tailor or leather goods brand.
- A topographic contour line used as a background/divider element for a landscaping or outdoor brand.
- A blueprint-grid texture used subtly behind content for an architecture or construction firm.
- A subtle underline/highlight stroke that mimics a signature or brushstroke for a personal-brand/creative portfolio.

The motif should show up 2–4 times across the page (e.g. a divider shape, an icon style, a background texture) so it reads as a deliberate system, not a one-off decoration.

## Layout rhythm alternatives to "hero, 3-col grid, repeat"

Rotate through these instead of defaulting to the same section shape every time:

- **Asymmetric split**: large image/media on one side (60–70% width), tightly set content on the other, alternating sides section to section.
- **Full-bleed editorial band**: full-width image or color block with content overlaid or set in a constrained column above/below it.
- **Diagonal/offset grid**: content blocks offset vertically from each other rather than aligned to a strict row, creating visual movement down the page.
- **Layered/overlapping**: a media element that intentionally overlaps into the next section's space (with care taken that it stays readable and doesn't break on mobile).
- **Kinetic divider**: an animated SVG line, wave, or shape between sections instead of a flat color change, used as a transition device.

Keep an underlying consistent system (spacing scale, container widths, corner-radius values, color tokens) even while the surface layout varies — consistency in the system is what keeps variety from feeling chaotic.

## Signals that a design has drifted back to generic/template

Watch for these and correct them before delivery:

- Centered hero text over a gradient blur with a single centered CTA button — the single most common generic-AI-site tell.
- Three-icon feature grid with rounded card backgrounds and a soft shadow, no other layout variety on the page.
- Glassmorphism panels (translucent, blurred-background cards) used as a default UI surface.
- A cyan-to-magenta or purple-to-blue gradient as the primary brand color story.
- Rounded pill buttons with a soft drop shadow as the only interactive element style on the page.
- Stock icon set (outline-style generic icons) used without any custom or industry-specific treatment.
- Testimonial carousel with circular avatar placeholders and star ratings, dropped in without any connection to the rest of the page's visual language.
