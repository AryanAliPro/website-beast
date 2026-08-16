# Motion Recipes

Concrete, copy-adaptable patterns for the motion layer of a web-beast build. Pick the ones that fit the art direction from Step 1 of SKILL.md — don't use all of them on every project. Two or three well-executed moments beat ten scattered ones.

## CDN imports

```html
<!-- GSAP core + ScrollTrigger -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js"></script>

<!-- Lottie -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/bodymovin/5.12.2/lottie.min.js"></script>
```

Register the plugin once at the top of your script:

```js
gsap.registerPlugin(ScrollTrigger);
```

## Hero entrance: staggered mask reveal

Use for the first viewport. Feels premium because elements arrive in sequence rather than all fading in together.

```js
const heroTl = gsap.timeline({ defaults: { ease: "power3.out" } });

heroTl
  .from(".hero-eyebrow", { y: 20, opacity: 0, duration: 0.6 })
  .from(".hero-title .line", {
    y: "110%",
    duration: 0.9,
    stagger: 0.08,
  }, "-=0.3")
  .from(".hero-subtext", { y: 16, opacity: 0, duration: 0.7 }, "-=0.4")
  .from(".hero-cta", { y: 16, opacity: 0, duration: 0.6 }, "-=0.4")
  .from(".hero-media", { scale: 1.08, opacity: 0, duration: 1.1 }, "-=0.9");
```

For `.hero-title .line`, wrap each line of the headline in a `<span class="line">` inside an `overflow: hidden` container so the `y: "110%"` slide-up is masked.

## Scroll-triggered section reveals

Standard pattern for content sections — fade/rise into place as they enter the viewport, batched so multiple elements in a section animate together.

```js
gsap.utils.toArray(".reveal-section").forEach((section) => {
  gsap.from(section.querySelectorAll(".reveal-item"), {
    y: 40,
    opacity: 0,
    duration: 0.8,
    stagger: 0.12,
    ease: "power2.out",
    scrollTrigger: {
      trigger: section,
      start: "top 80%",
      toggleActions: "play none none reverse",
    },
  });
});
```

## Pinned/scrubbed section

Use sparingly — one pinned moment per page is usually the ceiling. Good for a process walkthrough, a before/after, or a product feature reveal tied to scroll position.

```js
gsap.timeline({
  scrollTrigger: {
    trigger: ".pin-section",
    start: "top top",
    end: "+=1500",
    scrub: 1,
    pin: true,
  },
})
  .to(".pin-step-1", { opacity: 0, y: -40 })
  .to(".pin-step-2", { opacity: 1, y: 0 }, "<")
  .to(".pin-step-2", { opacity: 0, y: -40 })
  .to(".pin-step-3", { opacity: 1, y: 0 }, "<");
```

On mobile (viewport under ~768px), consider disabling pin behavior and falling back to a normal stacked scroll reveal — pinning is easy to get wrong on small screens.

```js
ScrollTrigger.matchMedia({
  "(min-width: 768px)": function () {
    // pinned timeline goes here
  },
  "(max-width: 767px)": function () {
    // simple fade/rise fallback for the same elements
  },
});
```

## SVG stroke-draw animation

For logos, custom icons, dividers, or diagrams. Requires the path to have a visible stroke.

```css
.draw-path {
  stroke-dasharray: 1000;
  stroke-dashoffset: 1000;
}
```

```js
document.querySelectorAll(".draw-path").forEach((path) => {
  const length = path.getTotalLength();
  gsap.set(path, { strokeDasharray: length, strokeDashoffset: length });

  gsap.to(path, {
    strokeDashoffset: 0,
    duration: 1.6,
    ease: "power2.inOut",
    scrollTrigger: {
      trigger: path,
      start: "top 85%",
    },
  });
});
```

## Magnetic button

A small cursor-follow effect on primary CTAs — one of the highest-impact, lowest-cost micro-interactions.

```js
document.querySelectorAll(".magnetic-btn").forEach((btn) => {
  const strength = 0.35;

  btn.addEventListener("mousemove", (e) => {
    const rect = btn.getBoundingClientRect();
    const x = (e.clientX - rect.left - rect.width / 2) * strength;
    const y = (e.clientY - rect.top - rect.height / 2) * strength;
    gsap.to(btn, { x, y, duration: 0.4, ease: "power2.out" });
  });

  btn.addEventListener("mouseleave", () => {
    gsap.to(btn, { x: 0, y: 0, duration: 0.5, ease: "elastic.out(1, 0.4)" });
  });
});
```

Skip this on touch devices — check `window.matchMedia("(pointer: fine)").matches` before binding it.

## Lottie integration

Load a Lottie JSON for a single branded moment (a process animation, a small hero accent, a success state) — not as a substitute for real content.

```js
lottie.loadAnimation({
  container: document.querySelector(".lottie-accent"),
  renderer: "svg",
  loop: true,
  autoplay: true,
  path: "https://assets.example.com/animation.json", // use a real, working asset URL
});
```

If no vetted Lottie asset URL is available, it's better to skip Lottie for that project than to reference a broken path — fall back to a well-crafted CSS/SVG animation instead.

## Parallax layer (subtle, readability-safe)

```js
gsap.utils.toArray(".parallax-layer").forEach((layer) => {
  const depth = layer.dataset.depth || 0.2;
  gsap.to(layer, {
    yPercent: -20 * depth * 10,
    ease: "none",
    scrollTrigger: {
      trigger: layer.closest("section"),
      start: "top bottom",
      end: "bottom top",
      scrub: true,
    },
  });
});
```

Keep parallax offsets small (roughly 10–30% of scroll distance) — large offsets cause text/image misalignment and motion sickness on some users.

## Cursor-reactive hero tilt (optional, high-impact for portfolio/agency sites)

```js
const heroMedia = document.querySelector(".hero-media");
document.querySelector(".hero").addEventListener("mousemove", (e) => {
  const { innerWidth, innerHeight } = window;
  const xRatio = (e.clientX / innerWidth - 0.5) * 2;
  const yRatio = (e.clientY / innerHeight - 0.5) * 2;
  gsap.to(heroMedia, {
    rotationY: xRatio * 6,
    rotationX: -yRatio * 6,
    duration: 0.6,
    ease: "power2.out",
    transformPerspective: 800,
  });
});
```

## General motion discipline

- Respect `prefers-reduced-motion`: wrap non-essential animation in a media query check and provide a static fallback.
- Never animate `width`/`height`/`top`/`left` for performance-sensitive motion — animate `transform` and `opacity`.
- Set `will-change: transform` sparingly on actively-animating elements, and remove it after the animation completes if it's a one-shot entrance.
- Test that scroll-triggered animations don't fire before content is laid out (wait for fonts/images to load, or set explicit dimensions to avoid layout shift).
