---
name: Easy Memory Item
description: Memory items that stick — and make you better.
colors:
  brand: "#1466D6"
  brand-deep: "#0E4EA8"
  brand-lift: "#4C93EF"
  brand-tint: "#EAF0FA"
  ink: "#131A21"
  ink-2: "#5A6672"
  ink-muted: "#8A97A4"
  line: "#DDE2E8"
  line-soft: "#ECEFF3"
  surface: "#FFFFFF"
  canvas: "#EEF1F4"
  hover: "#F7F9FB"
  inset: "#F2F3F5"
  tint-cool: "#EFF3F7"
  ok: "#17A673"
  caution: "#EBB236"
  alert: "#E4483B"
  band-ok: "#37A56A"
  rank-gold: "#E7A614"
  rank-bronze: "#C08457"
typography:
  fs-3xl:
    fontFamily: "Inter, sans-serif"
    fontSize: "25px"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: "-0.02em"
  fs-2xl:
    fontFamily: "Inter, sans-serif"
    fontSize: "22px"
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  fs-xl:
    fontFamily: "Inter, sans-serif"
    fontSize: "18px"
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: "-0.015em"
  fs-lg:
    fontFamily: "Inter, sans-serif"
    fontSize: "15px"
    fontWeight: 600
    lineHeight: 1.35
    letterSpacing: "-0.01em"
  fs-md:
    fontFamily: "Inter, sans-serif"
    fontSize: "14px"
    fontWeight: 600
    lineHeight: 1.35
    letterSpacing: "-0.01em"
  fs-sm:
    fontFamily: "Inter, sans-serif"
    fontSize: "12px"
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "normal"
  fs-xs:
    fontFamily: "Inter, sans-serif"
    fontSize: "11px"
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: "normal"
  fs-2xs:
    fontFamily: "Inter, sans-serif"
    fontSize: "9px"
    fontWeight: 700
    lineHeight: 1.15
    letterSpacing: "0.14em"
rounded:
  r-xs: "4px"
  r-sm: "8px"
  r-md: "12px"
  r-lg: "16px"
  r-xl: "20px"
  r-glass: "28px"
  r-pill: "999px"
spacing:
  sp-1: "4px"
  sp-2: "8px"
  sp-3: "12px"
  sp-4: "16px"
  sp-5: "20px"
  sp-6: "24px"
  sp-8: "32px"
  sp-12: "48px"
components:
  button-primary:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.surface}"
    typography: "{typography.fs-lg}"
    rounded: "{rounded.r-lg}"
    padding: "16px"
  button-primary-hover:
    backgroundColor: "{colors.brand-deep}"
  button-primary-pill:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.surface}"
    typography: "{typography.fs-sm}"
    rounded: "{rounded.r-pill}"
    padding: "10px 18px"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    typography: "{typography.fs-lg}"
    rounded: "{rounded.r-lg}"
    padding: "16px"
  button-secondary-hover:
    backgroundColor: "{colors.hover}"
  button-confirm:
    backgroundColor: "{colors.ok}"
    textColor: "{colors.surface}"
    typography: "{typography.fs-lg}"
    rounded: "{rounded.r-lg}"
    padding: "16px"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.r-lg}"
    padding: "16px"
  card-canvas:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.r-xl}"
    padding: "16px"
  chip:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink-2}"
    typography: "{typography.fs-sm}"
    rounded: "{rounded.r-pill}"
    padding: "7px 13px"
  chip-selected:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.surface}"
    typography: "{typography.fs-sm}"
    rounded: "{rounded.r-pill}"
    padding: "7px 13px"
  checklist-row:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    typography: "{typography.fs-lg}"
    rounded: "{rounded.r-lg}"
    padding: "16px"
  checkbox:
    backgroundColor: "{colors.surface}"
    rounded: "{rounded.r-sm}"
    size: "26px"
  checkbox-checked:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.surface}"
    rounded: "{rounded.r-sm}"
    size: "26px"
  icon-tile:
    backgroundColor: "{colors.tint-cool}"
    textColor: "{colors.brand}"
    rounded: "{rounded.r-sm}"
    size: "30px"
  tab-item:
    textColor: "{colors.ink-2}"
    typography: "{typography.fs-xs}"
    rounded: "22px"
    padding: "7px 15px"
  tab-item-active:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.brand}"
    typography: "{typography.fs-xs}"
    rounded: "22px"
    padding: "7px 15px"
---

# Design System: Easy Memory Item

## Overview

**Creative North Star: "The Flight Deck Companion"**

EMI is not an instrument and not a game. It is a calm, professional colleague who happens to know the aircraft cold. That single idea resolves every tension in the system: the app speaks in a human voice — *"Welcome on Board"*, "Ready when you are" — while every mechanism underneath it behaves with the exactness a checklist demands. Warmth in the copy and the corners; zero ambiguity in the controls.

Materially, the world is a cool grey airframe field (`#EEF1F4`) carrying white panels held down by a hairline border rather than a shadow. This inversion — grey ground, white content — is the system's core material idea and the thing most likely to be undone by accident, since almost every UI kit assumes the opposite. Type is Inter, almost universally at weight 600: 210 uses against 9 of weight 500. Regular-weight body text does not exist here. It reads as steady rather than shouty because the sizes stay small (11–15px for everything but titles) and the hierarchy is carried by a three-step ink ramp — `#131A21` → `#5A6672` → `#8A97A4` — instead of by weight contrast. One blue carries every interactive affordance. Green, amber and red appear only as readouts of real state.

The single piece of theatre in the whole system is the floating tab bar: a liquid-glass capsule with `blur(26px) saturate(180%)`, a translucent white fill, and a genuinely deep shadow, riding above a masked blur gradient. It is the one element allowed to feel like hardware. Everything else stays flat and printed, which is exactly what makes it work.

The confirmed anti-reference is the **consumer gamified study app**. EMI has streaks, achievements, ranks and a leaderboard, and none of them may drift toward mascots, confetti, bouncy oversized shapes, or a candy palette. Gamification here is presented the way an airline presents currency and recency: as a professional record.

**Implementation.** The product is built on **HeroUI**. `heroui.theme.ts` at the project root is the normative theme override — it maps every token below onto HeroUI's model and marks each deliberate divergence from HeroUI's defaults with its reason. Read it before generating a component; four of its overrides (inverted background, opaque divider, 16px large radius, and the much lighter shadow scale) will otherwise be silently reverted to HeroUI defaults, and each one is load-bearing.

**Key Characteristics:**
- Cool grey field, white panels, hairline borders — depth is earned, not applied
- Inter semibold as the resting weight; hierarchy carried by size and a three-step ink ramp
- One blue for every live control; semantic colour reserved for real state
- Warm, human copy over instrument-grade mechanics
- Exactly one glass element — the floating tab bar — and nothing else imitates it
- 16 is the system number: 16px radius, 16px padding, 16px gutter
- Aviation content typeset with checklist discipline: label left, response right

## Colors

A cool, low-saturation slate-and-white field with one authoritative blue and a tightly rationed semantic set. The token names below are the project's own, declared in the `:root` block of `index.html`.

### Primary
- **Brand** (`#1466D6`, `--brand`): every live control. Primary buttons, selected chips, checked checkboxes, progress fills, links, active icon tiles, the active tab glyph. If something responds to touch and needs to say so, it says so in this blue. 68 uses.
- **Brand Deep** (`#0E4EA8`, `--brand-deep`): the committed state — hover and pressed on every primary button, the top stop of hero gradients, and the manifest `theme_color` / `background_color`. Also the blue of the EMI mark.
- **Brand Lift** (`#4C93EF`): the bottom stop of hero gradients only (`linear-gradient(160deg, #0E4EA8, #1466D6 70%, #4C93EF)`). Never a fill or a text colour on its own.
- **Brand Tint** (`#EAF0FA`, `--brand-tint`): faint blue backing for informational callouts and selected list rows.

### Secondary
- **OK** (`#17A673`, `--ok`): correct answers, completed checklists, the "you are current" state, and the confirm button fill. Deeper and less neon than a stock success green — deliberately clinical.
- **Caution** (`#EBB236`, `--caution`) and **Alert** (`#E4483B`, `--alert`): skipped items, wrong answers, missed-item counts, and status dots. These are readouts, not decoration.
- **Band OK** (`#37A56A`): the *data-visualisation* green, used only in the proficiency and heat-map band trio alongside Caution and Alert — the currency bar, its legend, `pctColor`, `fitnessColor`, and quiz score colours. Deliberately softer and less saturated than OK, because it fills large areas rather than marking a single state. Never use it on a control, and never use OK in a band.

### Tertiary
- **Rank Gold** (`#E7A614`), **Rank Silver** (`#8A97A4`), **Rank Bronze** (`#C08457`): leaderboard podium and achievement medals, in that fixed order. The only place in the system where colour is ornamental, and it is bounded to the ranking components.

### Neutral
- **Ink** (`#131A21`, `--ink`): all substantive content — screen titles, checklist item labels, card titles, list rows. The default text colour, 123 uses.
- **Ink 2** (`#5A6672`, `--ink-2`): secondary text, eyebrows, unselected chips, inactive tab labels, subtitles. 79 uses.
- **Ink Muted** (`#8A97A4`): tertiary metadata — categories under search results, timestamps, counts.
- **Line** (`#DDE2E8`, `--line`): the border on every resting surface. 64 uses; the load-bearing structural device of the entire system.
- **Line Soft** (`#ECEFF3`, `--line-soft`): inner rules inside a card, and the softest fills.
- **Surface** (`#FFFFFF`, `--surface`): every card, sheet, row and panel.
- **Canvas** (`#EEF1F4`, `--canvas`): the app background behind everything. Floating footers fade to this exact value.
- **Hover** (`#F7F9FB`, `--hover`): the hover state for every tappable white surface.
- **Inset** (`#F2F3F5`, `--inset`): recessed wells and grouped sub-content.
- **Tint Cool** (`#EFF3F7`): icon tile backgrounds and inert chip fills.

### Named Rules

**The One Blue Rule.** `#1466D6` means "this is interactive" and means nothing else. Never use it as a decorative fill, a heading colour, or a brand flourish on a non-control. When a screen looks flat and needs energy, the answer is hierarchy, not more blue.

**The Earned Colour Rule.** OK, Caution and Alert are readouts of real state — a checklist completed, a proficiency band, an answer graded. Never use a semantic colour to categorise, to decorate, or to add variety to a list.

**The QRH Tab Exception.** The one sanctioned exception to the rule above. A printed quick-reference handbook colour-codes its tabs — Normal, Abnormal, Emergency — and pilots already navigate by that coding. The five Flight category tiles reproduce it, using the `--qrh-*` token family rather than the semantic palette, so a reader recognises the category before reading the label.

The exception is deliberately narrow, and its boundary is what keeps it from swallowing the rule:

- It applies to the five Flight category tiles and nothing else. A list row, chip, badge or icon tile does not get a QRH fill.
- `--qrh-*` never encodes state. A tile is amber because it is the Abnormal section, not because something needs attention. Anything reporting *progress* — a phase dot, a completion count, a proficiency band — uses `--ok` / `--caution` / `--alert`, and the two families never appear in the same component.
- The blues (`--qrh-lim`, `--qrh-sop`) are tab stock, not Brand, and do not imply interactivity. The One Blue Rule still governs `#1466D6`.

A second screen wanting category colour is a signal to re-examine the exception, not to extend it.

**The Two Greens Rule.** `#17A673` is the *state* green: a control, a completed checklist, a correct answer. `#37A56A` is the *band* green: a filled region in a chart, bar or heat map. They are not interchangeable, and a screen showing both is correct as long as each is in its own role.

**The Flat Field Rule.** `#EEF1F4` is never gradient-filled, and it is the page background rather than white. Floating footers mask to that exact value; any gradient behind them renders as a visible band. A UI kit that assumes a white `background` must be overridden, not accommodated.

## Typography

**Font:** Inter (with `sans-serif` fallback), vendored locally in `vendor/inter.css` — no network fetch, ever.

**Character:** One family, one dominant weight, doing all the work. Inter at 600 is the resting weight (210 uses); the tone comes from restraint in size and from the three-step ink ramp rather than from weight contrast. The result reads as competent and unhurried — a colleague stating facts, not an interface performing.

### Hierarchy
Sizes are the project's own `--fs-*` scale. Negative tracking tightens as size grows.

- **`fs-3xl`** (600, 25px, 1.05, −0.02em, Ink): the screen title, once per screen, top-left. "Welcome on Board", "Flight", "Learn".
- **Hero display** (600, 38px greeting / 34px statistic, −0.025em, white): the Start hero at canvas width only, where the card is 1180px wide and 400px tall. This tier lives above the ramp and is bounded to that one element — the phone hero's 25px/26px pair is the same two roles at phone scale. No other surface may reach past `fs-3xl`.
- **`fs-2xl`** (600, 22px, −0.02em, Ink): large statistics — a proficiency percentage, a streak count.
- **`fs-xl`** (600, 18px, 1.15, −0.015em, Ink): card titles and section heads inside a screen.
- **`fs-lg`** (600, 15px, −0.01em, Ink): checklist item labels, list-row primaries, full-width button labels. The workhorse.
- **`fs-md`** (600, 14px, −0.01em, Ink): descriptive text and secondary rows. 53 uses.
- **`fs-sm`** (600, 12px, Ink 2): metadata, checklist responses, chip text, captions. The most-used size in the app (71 uses).
- **`fs-xs`** (600, 11px, Ink 2): dense secondary metadata, tab and rail labels. 65 uses.
- **`fs-2xs`** (700, 9px, `letter-spacing: 0.14em`, uppercase): the smallest status labels and eyebrows. Uppercase eyebrows track between `0.08em` and `0.18em` — the smaller the type, the wider the tracking, and never below `0.08em`.

### Named Rules

**The Semibold Default Rule.** Inter 600 is the resting weight. 700 is reserved for uppercase status labels and rank numerals; 500 appears only on the widest-tracked eyebrows. Do not introduce 400 body text — it reads as a different product. Note this inverts the usual convention: emphasis is achieved by *size and ink*, never by going bolder.

**The Checklist Typesetting Rule.** A procedure line is always *label left, response right, nothing between them*. The label is `fs-lg`/600/Ink and `text-transform: capitalize`; the response is `fs-sm`/600, right-aligned, coloured by state. Never centre a checklist line, never put the response on a second row, and never restyle the response to match the label.

**The Verbatim Content Rule.** Aviation strings are set exactly as written — `V1, VR, V2 / FLEX`, `max +54 °C · min −43 °C`, `SOP 5.02`. Never sentence-case, expand, re-space, or "clean up" a procedure string, a limitation value, or an SOP number for visual rhythm.

## Layout

The spacing scale is `--sp-1..12` — 4 · 8 · 12 · 16 · 20 · 24 · 32 · 48 — all multiples of 4.

**Phone (default).** A full-screen shell (`.emi-app` / `.emi-shell`), edge-to-edge, capped at **440px** and centred so it looks intentional on a wide screen. There is no simulated device bezel in the deployed app. Height uses the `100vh → 100dvh → var(--app-h)` cascade to survive iOS toolbar behaviour. Screens are a flex column: a header block (eyebrow + title + right-aligned aircraft chip) over a scrolling body (`.emi-scroll`, hidden scrollbars, `padding-bottom: calc(118px + env(safe-area-inset-bottom))` to clear the tab bar). Gutter is 20px; vertical rhythm runs on a 28px section gap with 8–16px inside groups.

**Canvas** (`min-width: 700px and min-height: 700px`, or `min-width: 1100px`). There are exactly two designs — phone below the switch, iPad above it — and the layout changes shape rather than stretching:

- The floating tab bar is replaced by a fixed **88px left rail**, always expanded, icons over labels.
- Gutters open from 20px to **32px**; content caps at **1180px** and centres.
- Multi-card screens switch to `repeat(auto-fit, minmax(330px, 1fr))` at a 16px gap, hero card spanning full width. Short cards take `align-self: start` so a one-line card is never stretched to a tall neighbour.
- Single-column screens (`.emi-narrow`) cap at **772px** — applied to the whole screen, not just the scroll body, so header and content share a left edge.
- Cards soften: radius `--r-lg` (16px) → `--r-xl` (20px), and the hairline shadow is replaced by `0 10px 26px -16px rgba(19,26,33,0.22)`.
- The checklist becomes master/detail: a 300px left column holding the phase list and a limitations card.

**Start on iPad — the hero leads, and the cards keep their own height.** Start is a fixed, non-scrolling glance surface on every iPad, in both orientations. The composition is the same idea turned ninety degrees: the hero takes the slack, and every card is the height of what is inside it.

- **Landscape** (`min-width: 1180px and min-height: 800px and orientation: landscape`): a full-bleed hero over two card rows — Activity | Leaderboard | Fleet, then Weakest area | Currency. Grid rows are `minmax(200px, 1fr) auto auto`, so the cards take their content height and the hero absorbs what is left: ~400px on a 13" (1024pt), ~210px on an 11" (834pt). The 1180px threshold leaves ~340px per column after the 88px rail and 32px gutters, comfortably past the ~278px a full leaderboard row needs.
- **Portrait** (`min-width: 700px and min-height: 1000px and orientation: portrait`): hero, then Weakest area full width, then Activity | Leaderboard and Currency | Fleet. Rows are `minmax(280px, 1fr) auto auto auto` — again the hero alone takes the slack, giving it 341px on a mini and 574px on a 13".
- Blocks are grouped by **shape, not by topic**: lists and charts share the tall row because they can spend height on rows; single lines of state share the short one because they cannot.
- Anything that does not clear those thresholds — an iPad window inside Safari chrome, a mini in landscape — keeps the two-column scrolling layout, where the same pairing applies but cards sit at natural height and the hero is capped at `min(34vh, 360px)`.

**The hero at canvas scale.** The artwork is drawn for a 400px-wide card; at 1180px every mark is redrawn rather than transform-scaled, so the 1px attitude ladder stays 1px: 108px rungs, a 78px wing symbol, 46px epaulettes, and a 38px greeting. Above `min-height: 940px` (landscape) or `1000px` (portrait) the hero clears 300px and takes that full cinematic scale; between 800 and 940 it runs a moderate tier — 74px rungs, a 54px wing — because at ~210px tall the enlarged wing crowds "Next check in 96 days".

**Touch targets.** `--tap: 44px` is enforced on compact pills via `.emi-tap::after` — an invisible pseudo-element that extends the hit area vertically without growing the visual box. Any control smaller than 44px in either axis must carry this treatment.

### Named Rules

**The Glance Surface Rule.** On any iPad canvas, in either orientation, Start must fit the viewport. If content is added to that dashboard, something else gives up space — the user never scrolls to reach the leaderboard. The height budgets in the stylesheet are measured, not guessed; adding a block means re-measuring them and raising the `min-height` gate.

**The Hero Takes the Slack Rule.** When a fixed dashboard has more height than its content, the surplus goes to the hero, never to the cards. A card stretched past its content opens a hole — a 26px number, a bar and a legend spread down a 330px cell, or month labels pulled off the heat map they label. Cards get `auto` rows; the hero gets the `1fr`. Where a card must be levelled with a taller neighbour, pin its last line with `margin-top: auto` rather than spreading every line with `space-between`; a list card levels honestly by letting its rows grow (`flex: 1 0 auto`).

**The Rail Replaces the Bar Rule.** The glass tab bar and the left rail are the same navigation in two forms; they never appear together, and the rail carries the brand mark so the header drops its logo (`.emi-hbrand img { display: none }`).

**The 44 Rule.** Nothing tappable is smaller than 44px of hit area. When the design calls for a visually small control, extend the target with `.emi-tap`; never shrink the target to match the paint.

## Elevation & Depth

**Flat by default; depth means "floating".** Resting surfaces are white, defined by a 1px `#DDE2E8` border and `--sh-1`, a shadow so faint it is effectively a border-softener (41 uses). Depth is not decoration in this system — it signals that an element has genuinely left the content plane. Only three things qualify: the tab bar, sheets and overlays, and hero cards.

### Shadow Vocabulary
- **`--sh-1`** (`0 1px 2px rgba(19,26,33,0.03)`): the default on every resting white surface. Pairs with the 1px border; neither is optional.
- **`--sh-2`** (`0 14px 34px -20px rgba(19,26,33,0.40)`): raised cards and floating clusters that sit above a scrolling list.
- **`--sh-3`** (`0 24px 56px -20px rgba(19,26,33,0.45)`): completion cards, result sheets, and modals overlaying content.
- **Canvas lift** (`0 10px 26px -16px rgba(19,26,33,0.22)`): replaces `--sh-1` on cards at canvas width, where the larger surface can carry it.
- **Hero bloom** (`0 18px 40px -24px rgba(14,78,168,0.7)`): under blue gradient hero cards only. Tinted with the brand blue, not neutral.
- **CTA lift** (`0 10px 22px -12px rgba(14,78,168,0.8)`): under full-width primary buttons only.
- **Glass** (`0 14px 34px -10px rgba(19,26,33,0.34), 0 2px 8px rgba(19,26,33,0.08), inset 0 1px 0 rgba(255,255,255,0.6)`): the tab bar and search button. The inset top highlight is what makes the glass read as glass; never drop it.

### Named Rules

**The Earned Shadow Rule.** A shadow deeper than `--sh-1` requires the element to actually float above content. If it sits in the flow, it gets a border and `--sh-1` — no exceptions for emphasis. HeroUI's `shadow-small` is roughly twice `--sh-1`'s weight; using it on cards would quietly undo this rule across all 41 resting surfaces.

**The One Glass Element Rule.** Full backdrop blur belongs to the navigation cluster alone (`blur(26px) saturate(180%)`). Lighter blurs (`blur(3px)`, `blur(9px)`, `blur(14px)`) exist only as scrim and mask layers behind floating content. No card, sheet, modal or header may use a glass treatment; the tab bar's distinctiveness depends on being the only one.

## Shapes

A soft-rectangle language on the project's own radius scale, `--r-*`. The bigger and more structural the surface, the rounder its corners.

- **`--r-lg` 16px** is the system radius — cards, checklist rows, list items, full-width buttons, icon tiles. 61 uses; when in doubt, 16px. Card padding is also 16px, so the corner and the gutter are the same number.
- **`--r-xl` 20px** for hero cards and for all cards at canvas width.
- **`--r-md` 12px** for compact controls inside a header — the aircraft chip, small tiles.
- **`--r-sm` 8px** for checkbox squares and small inner tiles.
- **`--r-xs` 4px** for progress bars, thin rules, and chips nested inside other components.
- **`--r-pill` 999px** for pills: chips, filter rows, small pill buttons, avatars.
- **28px** for the glass tab bar capsule — the only element at that radius, and part of why it reads as a separate object.

Borders are uniformly `1px solid #DDE2E8` at rest. State borders shift colour, never width — except the checkbox, which uses `1.8px` so its outline survives at 26px.

### Named Rules

**The Radius Ladder Rule.** 4 · 8 · 12 · 16 · 20 · 28 · 999. Pick from the ladder; don't interpolate a new value because a component "looks slightly off". Note that 14px — HeroUI's `large` default — is *not* on this ladder; the override in `heroui.theme.ts` is what keeps it off.

## Components

### Buttons
- **Shape:** `--r-lg` (16px) for full-width actions; `--r-pill` for inline and secondary actions.
- **Primary:** Brand fill, white label, `fs-lg`/600, `padding: 16px`, no border. Full-width primaries add the CTA lift shadow; pill primaries add `inset 0 1px 0 rgba(255,255,255,0.28)` for a subtle top sheen.
- **Hover:** background shifts to Brand Deep over `0.18s`. No transform, no scale, no lift.
- **Secondary:** white fill, `#DDE2E8` border, Ink label, same geometry as primary. Hover fills to `--hover`.
- **Confirm:** OK fill, white label — reserved for completing a checklist or a run.

### Chips
- **Style:** pill, `padding: 7px 13px`, `fs-sm`/600. Unselected is white on a `#DDE2E8` border with Ink 2 text; selected is Brand fill, white text, matching border.
- **Behaviour:** chips live in a horizontally scrolling row with hidden scrollbars, `gap: 8px`, `white-space: nowrap`. They are phase/filter selectors, never actions. Carry `.emi-tap` — at 30px tall they are under the 44px minimum.

### Cards / Containers
- **Corner style:** 16px on phone, 20px on canvas and hero cards.
- **Background:** Surface white. Hero cards use `linear-gradient(160deg, #0E4EA8 0%, #1466D6 70%, #4C93EF 100%)` with white content.
- **Shadow strategy:** `--sh-1` at phone width, Canvas lift at canvas width, Hero bloom under gradient cards. See Elevation & Depth.
- **Border:** `1px solid #DDE2E8`, always, on white cards. Gradient cards carry no border. Inner divisions use `1px solid #ECEFF3`.
- **Internal padding:** 16px standard; 20–24px for hero and sheet cards.

### Inputs / Fields
The prototype has no free-text input other than search, which is a tappable card rather than a styled field. If a real input is added, it inherits the card treatment: white fill, `1px solid #DDE2E8`, `--r-lg`, `padding: 16px`, `fs-lg`/600, with focus expressed as a border shift to Brand plus a `0 0 0 3px rgba(20,102,214,0.16)` ring. Do not introduce an inset or grey-filled field style, and do not accept HeroUI's default `bordered`/`faded` input variants without re-styling them to this.

### Navigation
- **Phone:** a floating liquid-glass capsule, 239px wide, 53px tall, 28px radius, `rgba(255,255,255,0.62)` fill, `backdrop-filter: blur(26px) saturate(180%)`, `1px solid rgba(255,255,255,0.75)`, Glass shadow. Behind it sits a full-width 130px blur layer masked with `linear-gradient(to top, #000 45%, transparent)` so content dissolves rather than clips. Three tabs — Start, Flight, Learn — plus a detached 66×62px circular Search button to its right.
- **Tab item:** icon (22px, 1.8 stroke) over an 11px label, `padding: 7px 15px`, 22px radius. Inactive is Ink 2 with no fill; active is Brand on a white pill, cross-fading over `0.18s`. Labels are always visible — never icon-only.
- **Canvas and up:** an 88px fixed left rail, same icon-over-label composition, carrying the brand mark.

### Checklist Row (signature component)
The component the whole product is built around, and the one to get right before anything else.

A 16px-radius white row, `padding: 16px`, `gap: 16px`, containing three parts in fixed order: a 26px checkbox (`--r-sm`, `1.8px` border — Brand fill with a white 3.4-stroke tick when checked, a `#C8892B` dash when skipped), the item label (`fs-lg`/600/Ink, capitalized), and the response (`fs-sm`/600, right-aligned, state-coloured). Rows sit in a 10px-gap stack over a 6px `--r-xs` progress track with a Brand fill that transitions `width 0.25s ease`.

The current row is tracked via `data-cur` and auto-scrolled to the vertical centre of the list (minus a 150px bottom inset) with smooth behaviour — the list follows the pilot's position rather than making them hunt for it. A 150px spacer terminates the stack so the last item clears the floating action cluster.

### Named Rules

**The Position Follows the Pilot Rule.** In any procedure list, the app keeps the current item centred. Never make the user scroll to find where they are in a checklist.

## Do's and Don'ts

### Do:
- **Do** start from `heroui.theme.ts`. It is the normative mapping of these tokens onto HeroUI, and its four marked overrides — inverted background, opaque divider, 16px large radius, lighter shadow scale — are load-bearing.
- **Do** use `#1466D6` for interactivity and nothing else; hover to `#0E4EA8` over `0.18s` with no transform.
- **Do** give every resting white surface both a `1px solid #DDE2E8` border and `--sh-1` — they are one treatment.
- **Do** pick radii from the ladder (4 · 8 · 12 · 16 · 20 · 28 · 999) and default to 16px, with 16px padding to match.
- **Do** set procedure lines as label-left / response-right, and reproduce every aviation string verbatim, including spacing, symbols and SOP numbering.
- **Do** keep Inter 600 as the resting weight and carry hierarchy in size and the ink ramp (`#131A21` → `#5A6672` → `#8A97A4`).
- **Do** change layout *shape* at canvas width — rail instead of tab bar, grid instead of column, 32px gutters, 20px card radius — rather than stretching phone layouts.
- **Do** guarantee 44px of hit area on every control, using `.emi-tap` when the visual box is smaller.
- **Do** keep the current checklist item scrolled to centre.

### Don't:
- **Don't** drift toward the consumer gamified study app. Streaks, ranks, medals and achievements stay in the professional register — no mascots, no confetti, no bouncy oversized shapes, no candy palette.
- **Don't** let HeroUI's defaults through unexamined: a white `background`, a translucent `divider`, a 14px `large` radius, or `shadow-small` on a card each break a named rule above.
- **Don't** apply a glass treatment to anything but the navigation cluster.
- **Don't** use a shadow deeper than `--sh-1` on an element that sits in the content flow.
- **Don't** use OK, Caution or Alert for categorisation, variety or emphasis — only as a readout of real state.
- **Don't** introduce Inter 400, a second typeface, or an italic. Emphasis comes from size and ink, never from a heavier weight.
- **Don't** invent, round, or reformat a limitation value, checklist response, or SOP number to improve visual rhythm. Content accuracy outranks layout.
- **Don't** render navigation as icons without labels at any breakpoint.
- **Don't** add a network-dependent asset — no CDN font, script, icon set or image. Everything ships vendored and works offline.
- **Don't** create a second copy of the app to edit. `index.html` is the deployed app and the design authority; a parallel Claude Design export used to exist, drifted, and was mistaken for the authority — it has been deleted. Generate an export on demand instead (procedure in the README).
