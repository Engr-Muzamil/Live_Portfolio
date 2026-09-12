# Portfolio

Personal site for Muhammad Muzammil, AI engineer. One HTML file, one image, no build step.

Live on GitHub Pages: enable Pages on this repo, branch `main`, folder `/ (root)`.

## Design

The layout follows an editorial motorsport-instrument system: a near-white ground (`#f7fafb`), pure black copy, one cyan accent (`#02d2e3`), and near-black panels that appear per section. Two typefaces only — Oswald for display and figures, Space Grotesk for everything conversational.

Tokens are declared in three tiers in `:root`. Tier 1 holds every literal, tier 2 maps them to roles (`--background`, `--accent`, `--surface-dark`), and nothing below that uses a raw hex value.

## What is hand-written

No framework, no animation library, nothing from a CDN except two Google Fonts.

- **Spring solver** — a damped spring with tension, friction and mass 1, stepped at 1ms substeps. Every moving thing on the page is one of these.
- **Shared ticker** — one `requestAnimationFrame` loop with reference-counted subscribers, each with its own frame budget. It starts on the first subscriber and cancels on the last.
- **Text engine** — headings split into words or letters, each unit running its own spring with a stagger. A visually hidden plain copy stays for screen readers and the animated spans are `aria-hidden`.
- **Contour backdrop** — marching squares over an analytic four-sine field, drawn on canvas. Used behind the hero, the capabilities block and the footer.
- **Chequered dissolve** — the seam between a light block and a dark one. Solid rows at the top break into a chequerboard and burn off as you scroll, with a few squares coming through in the accent.
- **Sticky stack** — the first two blocks pin and recede, scaling to 0.9 and darkening to 55%, while the next one comes out over them.
- **Node graph** — the animated field behind the work section: crawling dashed axes, hub rings, a slow ping, and connections out to the nodes.

Everything respects `prefers-reduced-motion`: the reveals land instantly, the canvases draw one static frame, and nothing loops.

## Before you publish

Search `index.html` for `#REPLACE_WITH_REPO_URL`. Three project cards point at it. Replace all three with the real repository links.

Without them, every project on the page is an unverifiable claim, which is the one thing this layout is built to avoid.

## Contact

The phone number is gone as plain text. It now sits behind a WhatsApp button (`wa.me/923058091324`) alongside email and LinkedIn. To change the number, update both `wa.me` links.

## Accessibility

One `h1`, every block a `section` with an `h2`, `nav` landmarks labelled, the mobile menu a `role="dialog"` with focus management and Escape to close, the loading veil a `role="status"`. Every canvas is `aria-hidden`. Visible keyboard focus everywhere. Responsive from 320px up.

## Local preview

```
python3 -m http.server 8000
```
