# Design System: eUprava (eds-angular)
**Source:** `eds-angular` — Official eUprava Design System components for Angular (`@angular/material` 21 + Material 3 styling).

## 1. Visual Theme & Atmosphere

**Official, government-grade, and quietly confident.** Built on the Material 3 (M3) design language, adapted to the visual identity of the Republika Srbija's eUprava portal. The overall mood is **institutional clarity** — trustworthy, accessible, and calm — without feeling cold. Dense information (tables, steppers, forms) is made digestible through generous whitespace, a restrained four-accent extended palette, and soft, elevation-based layering.

The aesthetic philosophy is **functional polish over decoration**: every color, corner radius, and shadow traces back to a semantic role (primary action, surface, error, state). Components speak the same visual language whether they are low-level primitives (buttons, chips, inputs) or assembled page blocks (header, hero, footer, card lists). The system favors **whisper-soft depth**: elevation is communicated with subtle, diffused drop shadows on pure-white to near-white "surface container" fills, never heavy hard shadows. Emphasis is achieved through **color density** (filled containers vs. transparent text buttons) and **typographic scale** rather than decoration.

## 2. Color Palette & Roles

All colors are Material 3 palette-derived. Core semantic roles:

### Core / Brand
- **Deep Government Blue — Primary** (`#36618E`) — The system's anchor. Used for primary filled buttons, active navigation, links, focus indicator, selected checkboxes, and the step-counter's strong "active" state. Darker than a typical M3 primary, giving the interface a distinctly civic, serious tone.
- **Brand Deep Navy** (`#003964`) — eUprava brand mark core color (logo/templates, `$core-primary`). Appears in hero blocks and branding, distinct from the interactive `#36618E` primary.
- **Brand Red** (`#E31E30`) — eUprava brand mark secondary color (`$core-secondary`), used sparingly for accent stripes and identity marks. Not a general UI error color.

### Semantic (M3 scheme)
- **Primary** (`#36618E`) / **On-Primary** (`#FFFFFF`) — Primary actions; white text on blue fill.
- **Primary Container** (`#D1E4FF`) / **On-Primary Container** (`#1A4975`) — Tonal primary surfaces (tonal buttons, selected chips, active stepper counters, status "pending").
- **Secondary** (`#904A47`) / **On-Secondary** (`#FFFFFF`) — A muted terracotta used for secondary filled actions and tonal chips.
- **Secondary Container** (`#FFDAD7`) / **On-Secondary Container** (`#733331`) — Tonal secondary surfaces.
- **Tertiary** (`#186584`) / **On-Tertiary** (`#FFFFFF`) — A deep teal-cyan for tertiary actions and accents.
- **Tertiary Container** (`#C1E8FF`) / **On-Tertiary Container** (`#004D67`) — Tonal tertiary surfaces.

### Error & Status
- **Error** (`#BA1A1A`) / **On-Error** (`#FFFFFF`) — Validation errors, destructive actions, error toasts.
- **Error Container** (`#FFDAD6`) / **On-Error Container** (`#93000A`) — Tonal error surfaces (error chips, status labels).
- **Warning / Notice** (`#FFC107`) — Amber notice accent.
- **Info** (`#64B5F6`) / **On-Info** (`#00315A`) — Informational actions & accents.
- **Success** (`#81C784`) / **On-Success** (`#1B370C`) — Positive confirmation accents.

### Extended (UI) Accent Families (eUprava `extended (ui)`)
Four accent families, each carrying the same container/on-container roles so they drop into any M3-aware component:
- **Green** (`#476730`, container `#C8EEA8`, on-container `#304F1A`) — Stepper "done" state, success status labels.
- **Cyan** (`#00696D`, container `#9CF1F5`, on-container `#004F52`) — Info/neutral status labels.
- **Orange** (`#835415`, container `#FFDDBA`, on-container `#663D00`) — Warning status labels.
- **Rose** (`#864B6F`, container `#FFD8EB`, on-container `#6B3456`) — Decorative/focus accent.

### Neutral & Surface (Light)
- **Background / Surface** (`#F8F9FF`) — Cool, near-white page canvas (`$light-background`).
- **On-Surface / On-Background** (`#191C20`) — Near-black ink for body text and primary borders.
- **Surface Container Lowest** (`#FFFFFF`) — Pure white for elevated cards and form-field backgrounds.
- **Surface Container Low** (`#F2F3FA`) / **Container** (`#ECEEF4`) / **High** (`#E6E8EE`) / **Highest** (`#E1E2E8`) — The tonal stair-step for filled cards, chips, and tonal surfaces.
- **Surface Variant** (`#DDE3EA`) / **On-Surface Variant** (`#41484D`) — Muted grey-blue; secondary text, placeholder, neutral status background.
- **Outline** (`#71787E`) / **Outline Variant** (`#C1C7CE`) — Divider lines, outlined buttons, form-field borders, table rules.
- **Inverse Surface** (`#2E3135`) / **Inverse On-Surface** (`#EFF0F7`) — Dark chips/snackbars on light surfaces.

### Dark Mode (defined but secondary)
A full dark-scheme token set exists (`$dark-*`): **Primary** (`#A1CAFD`), **Surface** (`#111418`), **On-Surface** (`#E1E2E8`), plus dark variants of every accent family. Application is **not yet fully shipped** (Figma gaps remain on Orange/Rose on-colors) — dark theming should be treated as *in progress*.

## 3. Typography Rules

- **Display / Brand Font:** **Orto RNIDS** (custom licensed font, `$font-family-sans`), with `system-ui / Roboto / Arial` fallbacks. This is a distinctive humanist sans-serif, the signature voice of the eUprava system.
- **Weights:** A full numeric axis from Thin (100) through Black (900) is registered. In practice: **Regular (400)** for body text, **Medium (500)** for buttons/chips/labels/tab text, **Semibold (600)** for detail labels and small uppercase markers, **Bold (700)** for headings and prominent labels, **Thin (100)** for large hero subtitles.
- **Type Semantics (M3 scale):** Labels (11/12/14px) → Body (12/14/16px) → Title (14/16/22px) → Headline (24/28/32px) → Display (36/45/57px). Headings (h1–h6) scale from 56px down to 20px with line-heights 64px→28px and Bold/Medium weights.
- **Letter-spacing:** Tight and controlled — `0.02857em` global, `0.4–0.6px` on button labels, up to `0.6px` on tiny uppercase status markers. Achieves a refined, slightly spaced modern look without feeling airy.
- **Line-height:** Comfortable — body ~1.4–1.6, headings 1.1–1.25, small labels 1.0–1.2.
- **Disabled:** Set to `opacity 0.38` per M3.

## 4. Component Stylings

* **Buttons:** Gently rounded (`4–8px` radius). **Filled** (primary/secondary/tertiary/error/success/info) with white text and a subtle darkened hover fill; **Tonal** using container/on-container pairs with a brightness-dipped hover; **Outlined** with a transparent fill, a 1px `outline` border, and primary text that thickens the border (2px) and darkens on hover; **Text** buttons with primary-colored label and a faint primary ripple on press. Sizes: small (32px min-height), medium (36px), large (44px). Focus states use a crisp 1–2px primary outline offset 2px. Icon variants center 18px Material icons; icon-only buttons are pill-shaped (999px). Disabled: `opacity 0.38`.

* **Cards / Containers:** Subtly rounded (`8px` radius, `--eds-card-border-radius`). Three variants — **Elevated** (pure white `surface-container-lowest` fill with a soft `elevation-1` shadow), **Filled** (slightly darkened `surface-container` fill, borderless), and **Outlined** (transparent fill with a 1px `outline-variant` border, no shadow). Interactive cards lift to a whisper-soft elevated shadow (`0 4px 8px 3px rgba(0,0,0,.15)`) and scale 1.02 on hover; disabled cards fade to `0.6` opacity. Titles use primary-medium weight at 18px; content at 14px with ~1.6 line height. Padding scales by size (small/medium/large: 12/16/24px). Every card is a full-height flex column with actions right-aligned or start/center/end configurable.

* **Inputs / Forms:** **Form fields** have a default height of **48px**, a **6px** rounded container, and a **1px** `outline-variant` border. Enabled border is grey (`#71787E`), hover darkens toward near-black, focus turns **primary blue** with a 2px inset ring (total 3px visual, no layout reflow), error turns **red** (`#BA1A1A`) with an equal 2px inset ring. Background is pure white (`surface-container-lowest`); a `--fill` variant uses a container tint. Labels (12px) sit above, tracking the border color (blue on focus, red on error); required fields are marked with a solid red dot (not an asterisk). Readonly fields render borderless on a faint `#eaf1ff` tint; disabled fields fade to `0.72` opacity. Error `!` icons and clear `X` buttons are circular and inherit state color. Native inputs are transparent and borderless inside the field container.

* **Stepper:** Square, tonal counters (42px, 8px radius) — unvisited steps are grey `surface-variant` with primary ordinals; the active step is filled with the primary container; done steps turn **green** container; error steps turn the error container. A `--full` (strong) variant uses the fully saturated primary/green/error fills with white text. Small steps collapse to 32px circles. Steps connect with 2px tracks (grey → primary as completed).

* **Chips:** Rounded (`8px`), 32px min-height, `gap: 8px`, with a subtle 0.2s ease transition and active press-scale `0.98`. **Filled** (primary/secondary/tertiary/warn container colors) and **Outlined** (1px border, transparent fill, tinted hover `rgba(primary, 0.08)`); **elevated** chips carry a faint `0 1px 3px` shadow. Selected chips use the selected container fill or a tinted primary state; error chips use error container with red text. Trailing remove icons have circular hover/active state layers.

* **Status Labels:** Pill-shaped (`9999px`), with an optional status dot. Colored via container/on-container pairs — **success** (green), **info** (cyan), **neutral** (surface-variant), **error** (error), **pending** (primary), **warning** (orange), plus outlined (transparent with `currentColor` border) and elevated (soft shadow) modifiers. Sizes tiny→small→medium→large; the tiny variant is uppercase bold with wide tracking.

* **Tabs:** Underline/primary-indicator tabs (secondary variant) with a 2px rule; active tab is primary colored with the primary underline. Primary variant fills the active tab with a light tint. 4px border radius, 500-weight labels at 12/14/16px by size.

* **Table:** Dense, borderless by default with subtle row dividers; density tiers (compact 40px / standard 48px / comfortable 56px rows). Variants: **striped** (even rows faintly tinted), **bordered** (1px outline-variant borders between cells), **hoverable** (soft `rgba(0,0,0,0.04)` row hover). Header rows carry a faint `rgba(0,0,0,0.04)` container tint with 500-weight text; number/date columns right/center-align with tabular figures (`tnum`). Empty state centers a dimmed icon with muted text; loading overlays a translucent white veil.

* **Toast / Snackbar:** Rounded (`8px`), `14px` text, close + action buttons. Type colors: **success** (`#2e7d32`), **info** (`#0288d1`), **warning** (`#f57c00`), **error** (`#d32f2f`) — all with white text and tinted action-button colors. Min-width 344px, max 672px (full-width below 600px). Deep multi-layer M3 elevation shadow.

* **Checkbox / Radio:** M3-square checkbox (18px, 3px radius) tinted primary when selected with a white checkmark; unselected border uses on-surface-variant. Hover/focus/pressed expose a 40px circular state layer at M3 opacities (0.08/0.12/0.12). Labels are body-medium (14px, 20px line-height).

* **Icons:** Material Symbols (Outlined/Rounded/Sharp). Sizes 16 / 24 / 32 / 48px. Interactive icons round to 4px with hover/focus/pressed state layers; disabled fades to 0.38. Variable font weight (normal/medium/bold) and fill/grade/optical-size settings supported.

* **Hero:** Full-width brand block on solid primary (`#004b87` fallback) with a background image darkened (`contrast 0.9 brightness 0.6`) under a subtle black overlay. Centered bold title (up to 4rem on `lg`) with a thin-weight large subtitle and a row of actions. Sizes sm/md/lg (padding 2/3/6rem) and left/center/right alignment.

* **Page Blocks (Header / Footer / Stats / Card-list / Page-header / Page-content):** Assembly-level components that compose the primitives above into full page sections, sharing the common typography, spacing, and elevation language.

## 5. Layout Principles

* **Whitespace Strategy:** A strict 4px-base spacing scale (`--eds-space-*`: 0, 4, 8, 12, 16, 20, 24, 32, 40, 48) and matching gap scale, with aliases xs/sm/md/lg/xl (4/8/16/24/32). Content is given room — cards use 16px internal padding baseline, page sections use 24–32px rhythm, hero blocks breathe at 3–6rem padding. Generous spacing is the primary tool for making dense government data legible.

* **Grid & Containers:** Fluid 12-column grid (4 columns on mobile, 8 on tablet, 12 on desktop) with gaps that widen from 16px (mobile) to 32px (large desktop). Max content width **1200px** (`--eds-container-max-width`). Breakpoints follow Material 3: **xs** 0, **sm** 600px, **md** 905px, **lg** 1240px, **xl** 1440px.

* **Responsive:** A Tailwind-inspired utility layer (`eds-*`, `sm:eds-*` … `xl:eds-*`) covers display, flexbox, grid, spacing (padding/margin per side), typography, colors, borders/radii, sizing, elevation (0–5), overflow, position, z-index, opacity, and transitions — each available per breakpoint, so responsive laydowns are expressed inline.

* **Elevation:** Graduated 0–5 scale (`--eds-elevation-*`) built from soft `rgba(0,0,0,…)` shadows. Level 1–2 for resting cards/controls, higher levels for popovers/overlays; elevated cards and chips use level 1, toasts/menus use the deeper multi-layer M3 shadow. Elevation is reserved for signals of depth, never default decoration.

* **Motion:** M3 standard easing (`cubic-bezier(0.2, 0, 0, 1)`) with durations of 120ms (fast) / 200ms (medium) / 320ms (slow). Transitions are applied to background-color, color, box-shadow, border-color, and transform for smooth state changes. `prefers-reduced-motion` disables non-essential transitions; `prefers-contrast: high` adds explicit borders for filled/outlined controls.

* **Accessibility:** 40px touch targets on all interactive controls (icon buttons, checkboxes), visible 1–2px primary focus rings offset 2px everywhere, `focus-visible` gating, uppercase screen-reader-only utility, `::ng-deep`-exposed semantic tokens for consumer override, and M3 state-layer opacity model. Disabled states uniformly render at 0.38 opacity with `pointer-events: none`.
