---
version: alpha
name: Valley Real Life
description: A warm, atmospheric dark-first design system anchored by a single luminous green. Built on a three-tier token architecture (primitives → semantic → components), OKLCH color, and the Montserrat typeface. Avoids pure black and pure white in favor of a faintly green-tinted neutral ramp.

colors:
  # --- Primitives: v-green scale (11 stops; brand anchor at 500) ---
  v-green-50:  "#F5FCE9"
  v-green-100: "#E6F6CA"
  v-green-200: "#D2EE9C"
  v-green-300: "#B7E541"
  v-green-400: "#AFDA42"
  v-green-500: "#9BC93C"   # brand · #9BC93C
  v-green-600: "#81A032"
  v-green-700: "#617E2A"
  v-green-800: "#415622"
  v-green-900: "#2D3B18"
  v-green-950: "#161E0C"

  # --- Primitives: v-neutral scale (warm gray-greige, faint green undertone) ---
  v-neutral-50:  "#F7F9F6"
  v-neutral-100: "#F0F2EF"
  v-neutral-200: "#DFE2DE"
  v-neutral-300: "#C2C5C0"
  v-neutral-400: "#8D918B"
  v-neutral-500: "#60655E"
  v-neutral-600: "#3F443C"
  v-neutral-700: "#2B2F28"
  v-neutral-800: "#181C16"
  v-neutral-900: "#10130E"
  v-neutral-950: "#08090A"

  # --- Semantic roles (point to primitives via the prose; flat hex per spec) ---
  primary:    "#9BC93C"   # = v-green-500
  secondary:  "#3F443C"   # = v-neutral-600
  tertiary:   "#B7E541"   # = v-green-300 (highlight / bright accent)
  neutral:    "#F0F2EF"   # = v-neutral-100
  surface:    "#181C16"   # = v-neutral-800 (dark theme bg-elevated)
  on-surface: "#F0F2EF"   # = v-neutral-100 (dark theme text)
  on-primary: "#10130E"   # very dark green-black for text on brand fills
  error:      "#F4514F"
  success:    "#6ED274"
  warning:    "#FFB330"
  info:       "#3BB9ED"

typography:
  display-lg:
    fontFamily: Montserrat
    fontSize: 64px
    fontWeight: 800
    lineHeight: 1.05
    letterSpacing: -0.02em
  display-md:
    fontFamily: Montserrat
    fontSize: 48px
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.015em
  h1:
    fontFamily: Montserrat
    fontSize: 32px
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: -0.01em
  h2:
    fontFamily: Montserrat
    fontSize: 24px
    fontWeight: 700
    lineHeight: 1.25
  h3:
    fontFamily: Montserrat
    fontSize: 20px
    fontWeight: 600
    lineHeight: 1.3
  h4:
    fontFamily: Montserrat
    fontSize: 18px
    fontWeight: 600
    lineHeight: 1.4
  body-lg:
    fontFamily: Montserrat
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontFamily: Montserrat
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontFamily: Montserrat
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.55
  caption:
    fontFamily: Montserrat
    fontSize: 12px
    fontWeight: 500
    lineHeight: 1.4
  label-eyebrow:
    fontFamily: Montserrat
    fontSize: 12px
    fontWeight: 600
    lineHeight: 1
    letterSpacing: 0.25em
  label-button:
    fontFamily: Montserrat
    fontSize: 14px
    fontWeight: 600
    lineHeight: 1
    letterSpacing: 0.01em

rounded:
  none: 0px
  xs:   4px
  sm:   8px
  md:   12px
  lg:   16px
  xl:   24px
  2xl:  32px
  full: 9999px
  # Squircle is an SVG mask-image, not a numeric radius — see Shapes section.

spacing:
  3xs:  2px
  2xs:  4px
  xs:   8px
  sm:   12px
  md:   16px
  lg:   24px
  xl:   32px
  2xl:  48px
  3xl:  64px
  4xl:  96px
  base: 16px
  gutter: 24px

components:
  # ---------- BUTTONS ----------
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.full}"
    padding: 11px 20px
    typography: "{typography.label-button}"
  button-primary-hover:
    backgroundColor: "{colors.tertiary}"
    textColor: "{colors.on-primary}"
  button-primary-active:
    backgroundColor: "#81A032"
    textColor: "{colors.on-primary}"
  button-secondary:
    backgroundColor: "transparent"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.full}"
    padding: 11px 20px
    typography: "{typography.label-button}"
  button-secondary-hover:
    textColor: "{colors.primary}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.v-neutral-300}"
    rounded: "{rounded.full}"
    padding: 11px 20px
    typography: "{typography.label-button}"
  button-ghost-hover:
    backgroundColor: "{colors.v-neutral-700}"
    textColor: "{colors.on-surface}"
  button-sparkle:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.full}"
    padding: 14px 24px
    typography: "{typography.label-button}"
    # Visual extras: rotating conic-gradient border ring + pulsing radial glow.
    # See Components prose below for the animated specification.

  # ---------- CARDS ----------
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: 16px
  card-action-tile:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    padding: 32px 16px
  card-event:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.lg}"
    # Thumbnail aspect-ratio: 7/3 (events), 16/9 (video)

  # ---------- INPUTS ----------
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: 12px 16px
    typography: "{typography.body-md}"
  input-search-pill:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.full}"
    padding: 4px

  # ---------- TAGS / CHIPS ----------
  tag:
    backgroundColor: "{colors.neutral}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.full}"
    padding: 4px 10px
    typography: "{typography.caption}"
  tag-brand:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
  tag-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.v-neutral-400}"

  # ---------- BREADCRUMBS ----------
  breadcrumb:
    textColor: "{colors.v-neutral-400}"
    typography: "{typography.body-sm}"
  breadcrumb-active:
    textColor: "{colors.on-surface}"

  # ---------- PAGE HEADERS ----------
  page-title:
    textColor: "{colors.on-surface}"
    padding: 48px 0 32px
  page-hero:
    backgroundColor: "{colors.v-neutral-950}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.xl}"
    padding: 48px

  # ---------- TOGGLE / THEME SWITCH ----------
  toggle:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.full}"
    height: 26px
    width: 44px
  toggle-checked:
    backgroundColor: "{colors.primary}"
---

# Valley Real Life — Design System

## Overview

Warm, atmospheric, and grounded. Valley Real Life's interface evokes a quiet evening — deep, faintly green-tinted darks that feel organic rather than clinical, broken open by a single luminous green that glows wherever it lands. The aesthetic is photographic and welcoming, not flat or sterile; surfaces have layered depth from subtle gradients and soft brand-tinted glows.

The system is dark-first but ships a light theme via a single semantic-token override. Both modes share the same primitive scales — light mode flips which stops the semantic tokens point at. **No pure black, no pure white.** Even the darkest backgrounds carry a hint of green undertone (hue 135); even the brightest text sits a step below pure white.

The voice should feel like a trusted invitation. Headlines are large and slightly tracked-in; body copy is comfortable, never crowded. Eyebrow labels — uppercase, heavily tracked, brand-colored — are the system's signature, reinforcing a hierarchical, sectioned reading experience inspired by church bulletins and editorial design.

Architecture is three-tier and cascading:

1. **Primitives** — raw color scales (`v-green-50…950`, `v-neutral-50…950`), theme-stable.
2. **Semantic** — contextual tokens (`primary`, `surface`, `on-surface`, etc.) reference primitives.
3. **Components** — consume semantic tokens only. Components do not reference primitives directly.

To re-skin: change a primitive, every semantic token cascades, every component updates. To override locally: change a semantic token at any scope.

## Colors

The palette is built from two OKLCH-derived scales. A single saturated green carries the entire brand identity; everything else is a warm gray-greige with a faint green undertone (OKLCH hue 135) that keeps the neutrals from feeling cold.

### Primitives

**v-green** is the brand scale, anchored at `v-green-500` (#9BC93C). The 300 stop is the brightest highlight; the 600 stop is the natural hover step-down; the 800–950 stops are reserved for pressed states and deep backgrounds.

**v-neutral** is a 22-stop neutral ramp. It is not pure gray — every stop carries `chroma ≈ 0.008–0.016` at hue 135, giving the system a subtle warm-green undertone that ties the neutrals to the brand without competing with it.

### Semantic Roles

- **Primary (#9BC93C):** "Valley Green." Brand. The single accent. Used for primary actions, focus rings, active states, eyebrow labels, link text, and the signature glow. Use exactly once per visual unit — never two primary buttons stacked.
- **Secondary (#3F443C):** "Slate Greige." Borders, dividers, secondary outlines. Quiet structural color.
- **Tertiary (#B7E541):** "Lime Highlight." A brightened brand for hover lifts on primary actions and for elements that need to glow against deep darks.
- **Neutral (#F0F2EF):** "Limestone." The page background in light theme and the inverse-tag background in dark theme.
- **Surface (#181C16):** "Forest Floor." Cards, elevated panels, nav bar. The default container surface in dark theme.
- **On-Surface (#F0F2EF):** Body and heading text in dark theme. Sits one step below pure white.
- **On-Primary (#10130E):** Text and icons placed on primary fills. A very dark green-black, not pure black, so it harmonizes with the green rather than fighting it.

### Theme Behavior

Both themes pull from the same primitive scales. The light theme override only changes which stops the semantic tokens reference (e.g. `surface` swaps from `v-neutral-800` → `v-neutral-100`). Brand stays identical in both modes for instant recognition.

For brand-colored text on light backgrounds (e.g. eyebrow labels in light theme), use `v-green-700` instead of `v-green-500` to maintain WCAG AA contrast. The system token `brand-text` handles this swap automatically.

### Status Colors

`success`, `info`, `warning`, and `error` are tuned to read clearly on dark surfaces without competing with brand green for attention. They are currently one-offs; when a second use case appears, promote them into full `v-amber`, `v-blue`, `v-red` primitive scales using the same 50-950 pattern.

## Typography

**Montserrat** carries the entire system — headings, body, labels. Weight and tracking do the work that a second typeface would normally do. Six weights ship: 300 (sparingly, very large display only), 400 (body), 500–600 (UI), 700–800 (headings).

The type scale is fully `rem`-based and modulated by a single `--font-scale` multiplier (default `1.0625`, ≈ 17px root). Changing that one value lifts or shrinks every size proportionally while remaining compatible with the user's browser font-size preference.

### Roles

- **display-lg / display-md:** Hero pages, marketing screens. Slightly tracked-in (`-0.02em`) at extra-bold weight for impact without shouting.
- **h1–h4:** Document and section headings. Bold for h1–h2, semibold for h3–h4. Line height tightens with size.
- **body-lg:** Lede paragraphs, intros to important content.
- **body-md:** Default paragraph, the workhorse.
- **body-sm:** UI text, secondary detail, dense card bodies.
- **caption:** Timestamps, metadata, image captions. Slightly heavier weight (500) to compensate for small size.
- **label-eyebrow:** The system's signature. Uppercase, brand-colored, 0.25em letter-spacing. Used above section headings and inside hero kickers ("FEATURED EVENTS", "OTHER LINKS", "CONTACT US"). Treat it as a section divider, not a heading.
- **label-button:** All button text. Slightly tracked-out (`0.01em`) and weighted 600.

### Tracking

Headings get `-0.02em` to `-0.01em` (`tracking-tight`). Body stays neutral. UI labels get `+0.01em` to `+0.04em`. Eyebrow labels get `+0.25em` (`tracking-widest`) and `text-transform: uppercase`.

## Layout

The page is centered in a `1180px` max-width container with `24px` side gutters. Inside, a rem-based spacing scale anchors a consistent vertical rhythm.

The spacing scale runs `3xs` (2px) through `4xl` (96px) on a roughly Fibonacci-ish curve. Most UI uses `md` (16px) for internal padding and `lg` (24px) for the gap between related blocks. Use `2xl` (48px) or `3xl` (64px) between distinct page sections. Always prefer logical properties (`padding-inline`, `margin-block`) for future-proofing.

### Aspect Ratios

Two ratios cover nearly all imagery:

- **Thumbnail ratio: 7 / 3.** Events, programs, ministry cards, blog posts. The signature card thumb shape.
- **Video ratio: 16 / 9.** Sermons, livestream, video thumbs.

Apply via `aspect-ratio: var(--thumb-ratio)` or `aspect-ratio: var(--video-ratio)`. Never crop content inside these — always `object-fit: cover` the image and let the ratio drive the box.

### Grid

No strict grid system. Cards and tiles use `display: grid` with `grid-template-columns: repeat(auto-fit, minmax(240px, 1fr))` to flex naturally without breakpoint juggling. Tile grids commonly use 4 columns wide, 3 columns, or 2 columns depending on density.

## Elevation & Depth

Elevation comes from two layers: **tonal layering** (surfaces stack from `bg` → `bg-elevated` → `surface` → `surface-hover` → `surface-active`, each ~3-5% lighter in dark mode, darker in light mode), and **shadow + glow** on top.

### Shadow Scale

- `shadow-xs` — subtle lift on tags and small chips.
- `shadow-sm` — resting state on cards.
- `shadow-md` — floating elements like popovers.
- `shadow-lg` — hover states, dropdown menus, dialogs.
- `shadow-xl` — modals, sheets.
- `shadow-inset` — pressed buttons (rarely used).

All shadows use `oklch(0 0 0 / α)` for true neutrality and reduce ~3× in opacity in light mode.

### Brand Glow

The signature elevation effect. A soft radial glow in brand green, used on:

- Primary buttons (default state).
- The logo mark in heroes and offline pages.
- Focus rings on inputs (a 4px tinted `box-shadow` ring at `oklch(from primary l c h / 0.2)`).
- The hero kicker text.
- The toggle knob on the theme switch.

Two glow tokens: `shadow-glow` (default) and `shadow-glow-lg` (hover). Both auto-derive from the brand color via the relative color syntax — change the brand once and every glow updates.

## Shapes

Generously rounded, with **pill shapes** as the signature for any interactive element.

### Radius Scale

- `rounded-xs (4px)` — code blocks, very small inset chips.
- `rounded-sm (8px)` — inputs nested inside larger containers, tabs.
- `rounded-md (12px)` — text inputs, dropdown items, smaller cards.
- `rounded-lg (16px)` — **default for cards.** Most cards and thumbnails.
- `rounded-xl (24px)` — heroes, large containers, modals.
- `rounded-2xl (32px)` — extra-large display containers.
- `rounded-full (9999px)` — **default for buttons, inputs, tags, badges, breadcrumb pills, the theme toggle.** The system's signature shape.

### Squircle

A separate shape primitive — an iOS-style superellipse, "square but not square." Implemented as a CSS `mask-image` (inline SVG) rather than a numeric border-radius, because superellipses can't be expressed with `border-radius` alone. Use the `.squircle` utility class or `mask-image: var(--squircle-mask)`. Note: `mask-image` clips outer `box-shadow`, so wrap the element if you need a drop shadow, or use `filter: drop-shadow()` on the parent.

## Components

Component styling consumes semantic tokens only. The component layer never references primitives or hex values directly — change `primary` and every primary-based component updates.

### Buttons

Pill-shaped (`rounded-full`), generously padded, with `label-button` typography. Five variants:

- **Primary** — Brand fill, `on-primary` text, brand glow (`shadow-glow` default, `shadow-glow-lg` on hover). Hover steps up to `tertiary` (brighter); active steps down to `v-green-600` (the deepest stop still passing WCAG AA against `on-primary`). Used for the single most important action per visual unit.
- **Secondary** — Transparent fill, `border-strong` outline, `on-surface` text. Hover swaps border and text to `primary`. Used for paired secondary actions next to a primary.
- **Ghost** — No background, no border, muted text. Hover fills with `surface` and brightens text. Used for tertiary or destructive-but-safe actions, icon-only buttons.
- **Brand Soft** — A 12% brand wash fill with `brand-text` color. Subtle but unmistakably branded. Used for "soft" CTAs inside detail cards.
- **Sparkle (Special)** — The high-stakes CTA. Animated conic-gradient border ring (4s linear spin via `@property --sparkle-angle`) over a pulsing radial brand glow. Used sparingly — "I'm New", "Get Started", major onboarding moments. Respects `prefers-reduced-motion`.

Sizes: `sm`, default, `lg`. Icon-only variant collapses padding to a square shape (`aspect-ratio: 1`).

### Cards

All cards use `rounded-lg` (16px) by default. Three primary patterns:

- **Action Tile** — Centered icon + label. Vertical gradient from `surface` to `bg-elevated`. Used for "Next Steps" entry points.
- **Row Link** — Icon + label + chevron. Horizontal. Brand-colored icon, neutral label, chevron picks up brand on hover. Used for long lists like "Other Links."
- **Event Card** — 7/3 thumbnail with a floating date badge in the top-right and title below. Hover lifts and shadows. The workhorse for events, programs, and content.
- **Detail Card** — Image header (7/3) with overlay tags bridging the seam (`transform: translateY(50%)` puts them half on the image, half on the body), title, meta line with brand icon, body, and a split-action footer (two buttons sharing a horizontal bar at the bottom).

### Inputs

`rounded-md` (12px) for most fields. Border defaults to `border-strong`; hover lifts to `border-strong-hover` (a step up); focus removes the outline and replaces it with a 1px brand border plus a 4px tinted ring (`oklch(from primary l c h / 0.2)`).

**Search Pill** — A signature input shape. `rounded-full` container with a 4px padding gap and an embedded circular brand-filled button on the right. Used for filter/browse at the top of list views.

**Selection Controls** — Custom-styled checkboxes (square + animated checkmark), radio buttons (circle + filled dot), and toggle switches (pill with brand-filled knob when on). All built with the native input hidden and a styled adjacent element.

### Tags / Chips

Tiny pill labels (`caption` typography). Default variant inverts per theme — dark pill on light surfaces, light pill on dark surfaces — for guaranteed contrast. Brand variant uses the full primary fill. Ghost variant has a transparent background and a thin border.

### Breadcrumbs

Compatible with Rock RMS markup (`<ol class="breadcrumb">` with `<li>` items, `.active` or `aria-current="page"` on the current page). Three variants:

- **Default** — Chevron separator (CSS-rotated square corner). Most pages.
- **Slash** — Classic forward-slash separator. Admin and CMS contexts.
- **Enclosed** — Wrapped in a `rounded-full` pill container with a surface background. Used inside hero headers.

### Page Headers

Two patterns for internal pages (the homepage gets its own treatment):

- **Simple (`.page-title`)** — Text-only. Optional eyebrow kicker, h1, lede, and right-aligned actions. Border-bottom rule. Most internal pages.
- **Hero (`.page-hero`)** — Image background with a brand-tinted radial overlay in the bottom-left plus a vertical dark gradient. Breadcrumb, kicker, large headline, lede, action buttons. Always treated as a dark surface regardless of page theme — the image and overlay provide their own context. Three modifiers: `--short` (220px min), `--tall` (420px min), `--centered` (text-align center).

### Theme Toggle

A pill-shaped track containing a brand-filled circular knob that translates horizontally between sun and moon icons. The knob carries the brand glow. State persists in `localStorage`; initial state respects `prefers-color-scheme`.

## Do's and Don'ts

- **Do** use the brand color (`primary`) exactly once per visual unit. Never stack two primary actions.
- **Do** use eyebrow labels (`label-eyebrow`) to introduce sections, not as standalone headings.
- **Do** preserve the green undertone in neutrals — never substitute true gray (chroma 0).
- **Do** use pill shapes (`rounded-full`) for all interactive elements — buttons, inputs, tags, breadcrumb pills.
- **Do** maintain WCAG AA contrast (4.5:1 for body, 3:1 for large text). Use `v-green-700` for brand text on light backgrounds.
- **Do** wrap brand glows around primary CTAs and the logo mark — but only on truly important actions.
- **Do** use the 7/3 aspect ratio for event/program thumbs and 16/9 for video.
- **Do** consume semantic tokens in components. If you need a primitive directly, that's a signal to add a new semantic token.

- **Don't** use pure white (#FFFFFF) or pure black (#000000) anywhere. Use `on-surface` and `v-neutral-950` instead.
- **Don't** mix shape languages. Don't put `rounded-xs` and `rounded-full` elements next to each other.
- **Don't** use the sparkle button more than once per screen. It loses its emphasis.
- **Don't** use more than two font weights on a single screen of body content. Headings + body, that's it.
- **Don't** reference primitives (e.g. `v-green-500`) directly in components. Always go through a semantic token (`primary`).
- **Don't** add a third typeface. Montserrat carries display, body, and labels — weight and tracking do the differentiation.
- **Don't** use the brand glow on more than one element per visual unit. Glow draws the eye; multiple glows compete.
- **Don't** apply the squircle mask without testing for `box-shadow` clipping — wrap the element or use `filter: drop-shadow()`.
- **Don't** crop imagery inside the 7/3 or 16/9 boxes manually. Let `object-fit: cover` do the work so different image sizes degrade gracefully.
