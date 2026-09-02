---
name: Jan Style
description: Elegant black-and-gold salon site with the real logo as a permanent, low-opacity background watermark.
colors:
  bg: "#100d0a"
  bg-panel: "#1b160f"
  bg-panel-2: "#221b12"
  gold: "#b9922f"
  gold-bright: "#d9b869"
  gold-dim: "#8a6d24"
  ink: "#f1ead9"
  ink-dim: "#b7ab94"
  ink-faint: "#85795f"
typography:
  display:
    fontFamily: "Marcellus, 'Iowan Old Style', Georgia, serif"
    fontSize: "clamp(2.5rem, 5.6vw, 4rem)"
    fontWeight: 400
    lineHeight: 1.12
  headline:
    fontFamily: "Marcellus, 'Iowan Old Style', Georgia, serif"
    fontSize: "clamp(1.85rem, 3.1vw, 2.5rem)"
    fontWeight: 400
  subhead:
    fontFamily: "Marcellus, 'Iowan Old Style', Georgia, serif"
    fontSize: "1.25rem"
    fontWeight: 400
  stat:
    fontFamily: "Marcellus, 'Iowan Old Style', Georgia, serif"
    fontSize: "2rem"
    fontWeight: 400
  body:
    fontFamily: "Jost, 'Helvetica Neue', Arial, sans-serif"
    fontSize: "16px"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Jost, 'Helvetica Neue', Arial, sans-serif"
    fontSize: "0.88rem"
    fontWeight: 400
rounded:
  sm: "8px"
  md: "14px"
  lg: "20px"
  full: "999px"
spacing:
  section: "clamp(4.5rem, 9vw, 7.5rem)"
  section-tight: "clamp(2.5rem, 5vw, 4rem)"
  inline: "clamp(1.25rem, 4vw, 3.5rem)"
components:
  button-primary:
    backgroundColor: "{colors.gold-bright}"
    textColor: "#17130b"
    rounded: "{rounded.full}"
    padding: "0.9rem 1.85rem"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.full}"
    padding: "0.9rem 1.85rem"
---

# Design System: Jan Style

## Overview

**Creative North Star: "The Watermark"**

This is the third visual system for Jan Style, and it is the client's own explicit direction rather than a generated concept. Round 1 drenched the whole page in near-black with a glowing hexagon motif (rejected: too dark, too much contrast). Round 2 went fully light and modern (rejected: felt generic, not enough of the real salon's identity, "too abgespaced" in a different way, and — separately — the layout and copy needed real refinement). For round 3 the client asked directly for an elegant black-and-gold world with the real logo permanently visible in the background, then, after seeing three concept sketches (Wasserzeichen / Seitenpanel / Auftakt & Wiederkehr), picked **Wasserzeichen** and asked for it to be refined so it never gets busy once real running text is on the page.

The mechanism that answers both halves of that brief at once: the real logo sits in a `position: fixed` layer behind the entire page, at very low opacity, desaturated to a soft grey rather than full gold, and lightly blurred. It never scrolls, so it reads as permanently present. Every section's own background stays transparent so the mark shows through consistently everywhere, not just the hero — but every actual content surface (cards, avatars, buttons) is fully opaque, so no line of body copy ever has to compete with the logo's detail for contrast.

**Key Characteristics:**
- One fixed, viewport-anchored watermark layer (`.watermark`) carries the "always present" brand requirement; nothing else on the page tries to repeat that job.
- Deep, warm near-black ground throughout (`#100d0a`), never a lit or glowing black — matte gold accent (`#b9922f`/`#d9b869`), never a shining metallic gradient.
- One serif (Marcellus) for every heading, one grotesque (Jost) for everything else — a classic two-face pairing, not a single do-everything family.
- Sections are transparent; only discrete surfaces (cards, pills, avatars) are opaque. This is the whole trick behind "visible but never busy."

### Named Rules
**The Opacity Discipline Rule.** The watermark's opacity (currently `0.08`) is a tuned value, not a placeholder — it was raised once already (from an initial `0.05` that read as barely-there) and checked against the densest real text section (the services cards' intro paragraph) before settling. Raise it further only after checking it against that same paragraph; never raise it while only looking at the empty hero, where any opacity looks fine.

**The Transparent-Section, Opaque-Surface Rule.** `.section`, `.hero`, and `.wrap` never receive a background color. Only actual UI surfaces — `.svc`, `.review`, `.trust__item`, `.person__avatar`, `.hero__badge`, `.btn` — do. Breaking this in either direction breaks the concept: an opaque section hides the watermark and quietly reintroduces "not visible enough"; a transparent card puts body text directly over the logo's linework and reintroduces "too busy."

## Colors

Deep matte black with a single restrained antique-gold accent.

### Primary
- **Gold** (`#b9922f`): default accent — borders, dividers, icon strokes. ~6.6:1 against the ground, safe for small text.
- **Gold Bright** (`#d9b869`): emphasis — headline highlight word, prices, ratings, button fill (paired with dark text, so its own contrast against the ground doesn't gate it). ~10:1 against the ground.
- **Gold Dim** (`#8a6d24`): scrollbar and other barely-there chrome.

### Neutral
- **Ground** (`#100d0a`): the page background — the only place the watermark is visible.
- **Panel** (`#1b160f`) / **Panel 2** (`#221b12`): opaque card surfaces and their hover state.
- **Ink** (`#f1ead9`) / **Ink Dim** (`#b7ab94`) / **Ink Faint** (`#85795f`): warm off-white through faint text steps.

### Named Rules
**The Matte Rule.** Gold is flat or very softly toned — never a glossy multi-stop gradient, never an animated shine sweep on hover. That treatment belonged to round 1's "too much" feedback; this round reads as restrained/expensive instead of loud.

## Typography

**Display:** Marcellus — an inscriptional, slightly condensed serif with real presence at heading size, used at regular weight only (it has no bold cut; size and letter-spacing carry hierarchy, not weight).
**Body:** Jost — a geometric grotesque in the Futura family, set at 400/500 weight for running text and UI labels.

### Hierarchy
- **Display** (Marcellus, `clamp(2.5rem, 5.6vw, 4rem)`, line-height 1.12): hero headline only, with the closing phrase set in `--gold-bright` via `<em>` (never a gradient fill).
- **Headline** (Marcellus, `clamp(1.85rem, 3.1vw, 2.5rem)`): section titles. `.cta-band h2` (`clamp(1.95rem, 3.8vw, 2.7rem)`) and `.legal h1` (`clamp(1.9rem, 4vw, 2.4rem)`) are the same role tuned to their own section's width, not separate roles.
- **Subhead** (Marcellus, `1.2–1.3rem`): component-level headings smaller than a section title — the header wordmark, mobile nav links, service-card `h3`, `.legal h2`.
- **Stat** (Marcellus, `clamp(1.7rem, 2.6vw, 2.2rem)` down to `1rem`, always `--gold-bright`): standalone numerals used as visual anchors rather than reading text — the trust-strip numbers, the hero rating badge, team initials for members without a photo.
- **Body** (Jost, `1rem`/`0.94–1.03rem`, line-height 1.65): running copy — the generous line-height is deliberate, it's part of what keeps text calm over the watermark. The hero lede (`clamp(1.02rem, 1.5vw, 1.15rem)`) is the same role at slightly larger size for its role as the page's opening sentence.
- **Label** (Jost, `0.8–0.95rem`): the working band for every piece of UI/meta text that isn't running prose — nav links, buttons, ratings, hours, footer, card meta. Values inside this band are tuned per component (denser for footer/meta, roomier for buttons/hours) rather than snapped to a single number; treat any new UI text as belonging here unless it is genuinely reading prose (→ Body) or a standalone numeral (→ Stat).

## Layout

Centered `1240px` container, same rhythm scale as prior rounds (`clamp(4.5rem, 9vw, 7.5rem)` section padding). The page is a single continuous dark field from hero to footer — no alternating light/dark or panel-tinted sections; only a 1px `var(--line)` hairline marks each section boundary. Services and reviews use even `auto-fit` grids (not an asymmetric cluster) since nothing about this round's brief asked for compositional novelty — the watermark is the visual event, everything else should stay quiet around it.

Mobile (`≤860px` nav, `≤900px` visit/reviews): grids collapse to one column; the watermark scales up (`min(120vw, 520px)` vs `min(60vw, 620px)` desktop) so it keeps a similar felt presence on a narrow, tall viewport instead of shrinking to a speck.

## Elevation & Depth

Soft shadows only on opaque surfaces (`--shadow-sm` at rest, `--shadow-md` on hover for services). The watermark itself carries no shadow or glow — it is meant to read as printed/embossed into the page, not as a lit object floating above it.

### Named Rules
**The No-Backdrop-Filter-On-Fixed-Ancestors Rule (carried over from round 2).** `.site-header` must keep a solid (non-blurred) background. A `backdrop-filter` on an ancestor of `.nav__links` creates a new containing block and collapses the fixed-position mobile nav panel to the header's own height. This has broken the mobile menu twice already in this project; do not reintroduce `backdrop-filter`, `filter`, `transform`, or `perspective` on `.site-header`.

## Shapes

Soft rounding throughout — `--radius-sm` (8px, icon tiles) through `--radius-lg` (20px, cards) and full circles/pills for avatars and buttons. No hexagons, no diagonal clips this round; the watermark itself is the one distinctive geometric device, so component shapes stay plain.

## Components

### Buttons
Full pill, `--gold-bright` fill with dark ink text (primary) or transparent with a soft gold-line border (ghost). Hover: 2px lift plus a flat color shift to `--gold` — no gradient sweep animation.

### Cards (trust, services, reviews)
Opaque `--bg-panel` on `--radius-lg` (or `--radius-md` for the trust strip), 1px hairline border, soft shadow. Services cards are full links to Treatwell; hover lifts the card, shifts it to `--bg-panel-2`, and fades in a "Bei Treatwell buchen →" affordance.

### Avatars (team)
Circle, 84px standard / 100px for the two lead stylists (Jan, Falah — brighter gold ring, not a filled gold disc this round, to stay matte). Real photos (6 of 7 team members, sourced from the salon's own Treatwell profile, self-hosted at `assets/team/`) fill the circle; the one team member without a Treatwell photo (Ali) keeps a typographic initial — never a fabricated photo. Whole card is a link to Treatwell (see PRODUCT.md: Treatwell has no per-stylist deep link, so every team and service card intentionally points to the same general listing URL).

### Watermark (signature component)
`position: fixed` full-viewport flex container centered on the real logo image, `opacity: 0.08`, `filter: grayscale(1) brightness(1.9) blur(0.5px)`. Present on every page (index, Impressum, Datenschutz) via the same markup fragment, immediately after `<body>`. See the two Named Rules above before changing any of its values.

### Hero Mark (title-image accent, hero only)
A second, un-dimmed rendition of the logo (`.hero__mark`, `clamp(150px, 19vw, 230px)` wide, full gold color, drop-shadow only) sits above the headline in the hero, layered on top of the ambient watermark. This gives the opening viewport a proper "title page" moment — borrowed, at the client's request, from the declined "Auftakt & Wiederkehr" concept sketch — while every other section and page keeps only the faint fixed watermark. Do not add this crisp, full-opacity mark anywhere outside the hero; that was deliberately scoped to one place so the rest of the page stays quiet.

## Do's and Don'ts

### Do:
- **Do** keep every `.section` background transparent; only individual card/pill/avatar surfaces get `--bg-panel`.
- **Do** check any watermark-opacity change against the services-intro paragraph, not just the hero.
- **Do** keep gold matte and flat; reach for `--gold` vs `--gold-bright` for contrast, never a gradient.
- **Do** use `Marcellus` only for headings and `Jost` for everything else.

### Don't:
- **Don't** give `.hero`, `.section`, or `.wrap` an opaque background — that hides the watermark and undoes the client's explicit ask.
- **Don't** raise the watermark opacity without re-checking it over real body text; "visible in the hero" is not the same test.
- **Don't** add `backdrop-filter`/`filter`/`transform`/`perspective` to `.site-header` (breaks the mobile nav — see Elevation & Depth).
- **Don't** reintroduce a glowing/animated gold gradient (round 1's failure mode) or a fully light page (round 2's rejected direction).
- **Don't** fabricate a team photo for Ali or anyone else without a real Treatwell photo.
