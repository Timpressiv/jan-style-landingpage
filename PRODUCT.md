# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Static HTML/CSS/JS. Delegated to the assistant: no build process needed for a single landing page, easy to host on any standard web host, and matches the sibling project praxis-magheli-landingpage's proven approach for this same client/workflow.

## Users

- **Local residents of Kaltenkirchen and the surrounding area (Schleswig-Holstein)** looking for a full-service hair salon for the whole family — men, women, and children — in one place.
- **Existing Jan Style customers** who currently book and leave reviews only through Treatwell, checking hours, services, or the fastest way to book their next appointment.
- **Prospective new customers** discovering the salon via search or word of mouth, deciding whether to trust and book based on reputation and range of services.

## Product Purpose

A new landing page for "Jan Style" that replaces having no own web presence at all — today the salon exists only as a Treatwell listing. The page should establish Jan Style's own brand identity online, present the salon's full service range and team credibly, and drive visitors straight into booking via Treatwell (the salon's only booking system). Success = a visitor quickly understands what Jan Style offers, trusts it (rating/reviews), and reaches the Treatwell booking flow with minimal friction.

## Positioning

A full-service, family-friendly hair salon and barbershop in Kaltenkirchen that serves men, women, and children under one roof — cuts, coloring, beard grooming, and facial/eyebrow treatments — backed by an unusually strong, high-volume trust signal (4.9★ across 4,500+ verified reviews on Treatwell) and a multi-person team of specialists rather than a single stylist. In a small town, combining that breadth of service with that volume of verified proof is the differentiator neighboring single-service or single-stylist salons cannot truthfully claim.

## Operating Context

- Located at Hamburger Straße 49, 24568 Kaltenkirchen, Germany.
- Opening hours: Mo–Fr 09:00–19:00, Sa 09:00–18:00, closed Sundays (source: Treatwell listing; must be confirmed by client before publishing and kept easy to edit).
- All bookings and reviews currently run exclusively through Treatwell — the salon has no independent booking system. Primary CTA throughout the page must route to the Treatwell booking page: https://www.treatwell.de/ort/jan-style/
- Payment at the salon: cash or card (updated 2026-09-10 per client; the page's contact section states this directly).
- Multi-person team confirmed via Treatwell (first names, individually bookable, each with their own rating): Jan, Falah, Reza, Mirela, Ben, Bahast, Ali.

## Capabilities and Constraints

- Services confirmed via the Treatwell listing (categories and starting prices — exact current menu/pricing must be treated as indicative, not contractually fixed, and confirmed by the client before publishing):
  - Herren – Haarschnitte & Stylings (ab 13 €), inkl. Haarschnitt & Bart/Rasur combos
  - Kinder – Haarschnitte & Stylings (ab 17 €, bis 10 Jahre)
  - Damen – Haarschnitte & Stylings (ab 23 €)
  - Damen – Farbe & Coloration
  - Haarkuren & Pflege
  - Augenbrauen & Wimpernbehandlungen
  - Gesichtshaarentfernung mit Fadentechnik
  - Herren-Waxing
- No independent online booking, contact form, or CRM — Treatwell is the single source of truth for availability and bookings. The landing page should link out to Treatwell for booking rather than reimplement it.
- Confirmed technical constraint: Treatwell's own listing has no shareable per-service or per-stylist deep-link URLs — booking runs entirely inside a JS widget (services are "Auswählen" buttons, team members are tabs that just switch content in place), not distinct routes. Every "book this service" / "book with this stylist" click on the landing page therefore goes to the same general listing URL (`https://www.treatwell.de/ort/jan-style/`); this is not a shortcut, it is the only link Treatwell exposes. Re-verified 2026-09-10 by reading Treatwell's own venue-page JS bundle directly: category clicks carry an internal `menuGroupId` used only for analytics, never read from the URL; the only URL parameter the widget reads at all is `rwg_token` (a Google Reserve tracking param, unrelated). No employee/staff selection parameter exists either. If the client asks again, this has been checked at the source-code level, not just by observation.
- No confirmed direct phone number or email independent of Treatwell at this time — do not invent one; if the client supplies one later it can be added.
- Language: German only.
- Open/undecided: exact final service list and prices are Treatwell's live data, not fixed content on the page — either link/embed Treatwell where feasible, or clearly present the on-page list as "ab"-pricing examples that mirror Treatwell rather than a fixed menu the client must manually keep in sync.

## Brand Commitments

- Salon name: **Jan Style**, in Kaltenkirchen.
- Official logo: client supplied both files as opaque PNGs on white (`assets/logo/canvas.png` gold-gradient, `assets/logo/canvassw.png` black/charcoal) — an ornate crown-and-heart-scroll emblem over crossed scissors with flowing hair, "JAN STYLE" wordmark below in a decorative serif. The white background was mechanically keyed to transparency (no artwork redrawn) and saved as `assets/logo/jan-style-logo-gold.png` and `assets/logo/jan-style-logo-bw.png`; the gold transparent version is wired into the site header and hero. The bw version is available but currently unused (it reads low-contrast on the black ground; keep it for any future light-background use, e.g. print or a light card).
- Note: the Treatwell listing's own descriptive copy refers to the salon in places as "Jan Barbershop" (likely a generic Treatwell template artifact) — treat "Jan Style" as the only confirmed brand name; do not use "Jan Barbershop" as a brand name on the page unless the client confirms it.
- **Visual direction history (see DESIGN.md for the current, standing system):** the client first shared a photo of the actual salon interior (black walls, gold ornamental furniture, a hexagonal honeycomb LED ceiling) and asked the site to match it.
  - Round 1: full black ground, gold everywhere, hexagon motif — rejected as too dark/too much contrast/poorly readable.
  - Round 2: zoned light content + two dark "bookend" bands, still hexagon-based — rejected outright, "too abgespaced."
  - Round 3: explicit pivot to light/white, rounded corners, single typeface (Hanken Grotesk), gold as a small accent, plus interactive service/team cards linking to Treatwell and real team photos — accepted, then refined for copy tone (visitor-facing "du", no "aktuell" repetition, corrected an inaccurate "3 Generationen" stat to "3 Zielgruppen") and layout (asymmetric hero, hover corner-cut on cards for more visual "Ecken und Kanten").
  - Round 4 (current): the client asked to go back to black/gold after all — "etwas das mehr zu seinem Salon passt", with the real logo made "quasi dauerhaft im Hintergrund sichtbar" (near-permanently visible in the background). Three concept sketches were presented (Wasserzeichen / Seitenpanel / Auftakt & Wiederkehr, see the published design-proposals artifact from that conversation turn if it needs to be revisited); the client picked **Wasserzeichen** — a fixed, low-opacity, desaturated watermark of the logo behind the whole page — then asked for it to be refined so it stays calm once real running text is on the page. The standing system now: deep matte black (`#100d0a`), restrained antique gold (no glow/gradient), Marcellus + Jost typography, and the fixed watermark layer described in DESIGN.md. Do not reintroduce the hexagon motif, a glowing/animated gold gradient, or a fully light page without a new explicit client request — all were tried and moved away from.

## Evidence on Hand

- Treatwell listing (https://www.treatwell.de/ort/jan-style/) confirms: address, hours, service categories with starting prices, 4.9★ aggregate rating across 4,543 reviews, and a named multi-person team each with individual ratings/specialty tags (e.g., Jan: Professionell, Sympathisch, Freundlich, Gründlich).
- A handful of real, attributable customer review excerpts were observed on Treatwell (e.g., praise for Jan's and Falah's work) — may be used as short, verbatim/attributed quotes if desired, not paraphrased into invented testimonials.
- Team photos: real profile photos for 6 of 7 stylists (Jan, Falah, Bahast, Reza, Ben, Mirela) were sourced directly from the salon's own Treatwell business profile (small 68×68 CDN thumbnails, downloaded and self-hosted at `assets/team/<name>.jpg` — the CDN only serves that fixed thumbnail size, larger sizes 404). Ali has no photo on Treatwell either, so the team grid keeps a typographic initial monogram for Ali only — never fabricate a photo for them. No interior or work photos supplied yet; do not fabricate those.
- Logo: real files in place and wired into the site (see Brand Commitments).

## Product Principles

1. Every path on the page should lead quickly to booking on Treatwell — that is the only functioning conversion mechanism the client has.
2. The 4.9★ / 4,500+ reviews trust signal is the strongest asset available and should be prominent, not buried.
3. The "everything for the whole family, plus beard/face care" breadth is the real differentiator in a small town — make it legible at a glance, not a long scroll to discover.
4. Never fabricate photos, prices, or team facts beyond what Treatwell or the client confirms; use honest placeholders instead.
5. Content the client will want to edit later (hours, prices, team members) should be easy to find and change without breaking layout.

## Accessibility & Inclusion

No formal standard specified by the client. Serves a broad, general local audience across ages (parents booking for children through older adult customers) — default to strong contrast, comfortable text sizing, and clear, unambiguous booking CTAs rather than a minimum-compliance baseline.
