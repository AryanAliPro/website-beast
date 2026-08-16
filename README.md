# Web Beast

An Anti-gravity IDE skill for Gemini models that designs and builds distinctive, production-ready websites.

Web Beast is a practical design-direction and implementation system for landing pages, marketing sites, portfolios, product pages, and other frontend surfaces. It pushes each build toward a specific visual point of view instead of a reusable template: industry-grounded art direction, deliberate typography, real imagery, restrained motion, responsive behavior, and a final quality pass.

[View the live demo](https://aryanalipro.github.io/website-beast/) · [Open the demo source](examples/atelier-vanguard-demo.html)

## What it covers

- Brief interpretation: business, audience, tone, offer, and constraints
- Industry-specific art direction, palette, typography, and layout motifs
- Complete HTML/CSS/JS delivery rather than placeholder wireframes
- Real, relevant public imagery with loading verification
- GSAP, ScrollTrigger, SVG, Lottie, parallax, and micro-interaction patterns
- Responsive and reduced-motion considerations
- A pre-delivery checklist for visual quality and interaction completeness

## Install in Anti-gravity IDE

1. Download or clone this repository.
2. Copy `skills/web-based-anti-gravity/` into the skills directory used by your Anti-gravity IDE setup.
3. Keep `SKILL.md` at the root of the skill directory and preserve the `references/` directory beside it.
4. Restart or reload Anti-gravity IDE so it discovers the skill.
5. Ask Gemini to design or build a website. The skill is intended to activate for website, landing-page, homepage, portfolio, product-page, and frontend-surface requests.

### Direct CLI installation

With Node.js 18+ installed, install only this skill globally for Antigravity:

```bash
npx skills add AryanAliPro/website-beast --skill web-based-anti-gravity --agent antigravity --global --yes
```

For a project-local installation instead:

```bash
npx skills add AryanAliPro/website-beast --skill web-based-anti-gravity --agent antigravity --yes
```

If you prefer a manual install, copy `skills/web-based-anti-gravity/` into either `~/.gemini/antigravity/skills/` for global use or `<your-project>/.agents/skills/` for project use, then restart or reload Antigravity.

## Gemini guidance

This skill is written for Gemini-powered workflows inside Anti-gravity IDE. Give the model a concrete brief and let it complete the full design-to-build loop. Useful inputs include the business, audience, desired action, brand constraints, required sections, and preferred stack. The skill's instructions are intentionally opinionated so Gemini has enough direction to make strong visual decisions while still adapting to the project.

The skill is self-contained and has no build step or package installation requirement. Its motion recipes reference browser CDNs for optional GSAP, ScrollTrigger, and Lottie integrations.

## Repository layout

```text
skills/
└── web-based-anti-gravity/
    ├── SKILL.md
    └── references/
        ├── motion-recipes.md
        └── visual-system.md
examples/
└── atelier-vanguard-demo.html  # Optional reference/demo page
```

The root `index.html` mirrors the demo so GitHub Pages can render it directly.

## Usage guidance

For best results, provide the business or product, target audience, desired action, brand constraints, and any required sections or technology. When some details are missing, Web Beast is designed to make sensible assumptions and continue.

The `examples/atelier-vanguard-demo.html` file is an optional architectural-remodelling demo. It is not required for installing or using the skill.

## Design principles

Web Beast avoids generic AI-site patterns such as default SaaS gradients, glassmorphism, repetitive card grids, decorative blobs, and unverified placeholder imagery. It favors a coherent visual system, varied composition, purposeful motion, accessibility-minded responsiveness, and interactions that work as well as they look.

## License

Released under the [MIT License](LICENSE).
