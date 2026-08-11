# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Four audiences, deliberately balanced — no single one wins by default when they conflict. The individual pilot and the organisation are treated as equal halves of the product.

- **Type-rating student pilots.** On a new type, drilling memory items, limitations and SOPs ahead of sim sessions and checkrides.
- **Line pilots staying current.** Qualified crew doing recurrent refresh between rotations, keeping memory items and limits sharp, plus pre-flight review.
- **Airline / ATO training departments.** Push their own SOPs and checklists to crews and track proficiency across them — the Hangars, Organisations and Leaderboard side of the app.
- **Flight instructors & examiners.** Assign practice and review trainee proficiency.

## Product Purpose

Easy Memory Item ("EMI") makes safety-critical cockpit knowledge stick: memory items, abnormal and emergency checklists, aircraft limitations, and operator SOPs. Success is a pilot who can produce the right item, in the right order, under pressure — and an organisation that can see where its crews actually stand.

Tagline in use: *"Memory items that stick — and make you better."*

## Positioning

Four claims a generic aviation study app could not truthfully copy:

- **Study inside the real procedure.** Learn mode hides items in place on the actual checklist and limitations layout the pilot will use in the cockpit, rather than extracting them into detached flashcards.
- **Spaced repetition driven by measured proficiency.** The proficiency radar (Memory Items, Limitation, System, Airspace, Speed, First Aid) drives what gets tested next; practice targets measured weak areas.
- **Operator-specific content.** The material is the organisation's actual SOPs and aircraft configuration, not generic manufacturer text.
- **Flight-mode companion.** The same content works live as a pre-flight and in-flight companion, not only as a study tool.

## Operating Context

- Used on a phone, and on an iPad in the cockpit or briefing room — often with no usable network.
- Content is organised by aircraft type (A320, A320neo, DA40 in the prototype) and by checklist group: Normals, Abnormal, Emergency, Memory Items.
- Existing surfaces: Home, Flight, Flight Mode, Phases, Checklist, Memory Items Overview, Memory-item Phases, Limitations, Limitations View, SOPs, Learn, Learn Checklist, Learn Limitations, Quick Check, Topic, Type Rating, Logbook, Achievements, Leaderboard, Profile, Aircraft, Hangars, Organisations, Config Summary.
- Practice formats: Quick Check, Proficiency Check, Type Rating — multiple choice, cloze ("complete the checklist item"), and ordering questions.
- Engagement mechanics present: streaks (placement configurable), achievements, leaderboard.

## Capabilities and Constraints

**Hard constraints — future work must not break these:**

- **Fully offline, no backend.** Not a prototype shortcut; a real requirement. Service worker precaches the whole app shell, all dependencies (React, ReactDOM, Babel, Inter) are vendored locally, nothing is fetched from a CDN.
- **iPhone and iPad, portrait and landscape.** Both form factors are in scope; iPad Pro landscape has its own dashboard layouts.
- **Aviation content must stay accurate.** Checklist wording, limitation values, and SOP numbering are real-world safety content. Never invent, round, or prettify a value; never add a procedure that isn't real.

**Technical shape:**

- Static PWA, no build step, no package manager. `index.html` is the deployable app and **the sole authoritative artifact** — it carries the Claude Design compiler markup (`<x-dc>`, `sc-if`/`sc-for`, `{{ }}` bindings) rendered by `support.js`, the logic block, and the PWA layer.
- **There is exactly one copy of the app, and no second place to edit.** A Claude Design export (`EMI Prototype v2.dc.html`) used to sit alongside it and drifted badly — untouched from 2026-07-21 while `index.html` took ~20 commits, ending up with a different system radius, ink ramp, and no `:root` token block, at which point the stale file was mistaken for the design authority. It was deleted on 2026-08-11 along with the truncated `EMI Prototype v2 (standalone).html`. Generate an export on demand if Claude Design is ever needed again; never commit a second copy. The device bezel (`ios-frame.jsx`) is likewise gone — the app uses a full-screen responsive shell.
- **Component kit: HeroUI.** The real build targets HeroUI. `heroui.theme.ts` at the project root is the normative theme override derived from the app's own tokens. The prototype itself does not consume it — `index.html` declares `:root` custom properties as intent but hardcodes literals (exactly one `var()` call in the file).
- `ios-frame.jsx` supplies the `IOSDevice` bezel and status bar for the desktop preview. Nothing imports it any more; kept for reference.
- Changing `index.html`, an icon, or `vendor/` requires bumping `CACHE_VERSION` in `sw.js`; new precached files go in `PRECACHE`.
- Deployed as static files (GitHub Pages via a workflow in `.github/`), installed via Add to Home Screen / Install prompt.

**Status — deliberately a demo prototype.** The purpose is to sell and validate the concept; the design-compiler markup is expected to be rewritten in a real stack later. Visual fidelity matters more than architecture. Shown to: airlines and ATOs as prospective customers, investors, and pilots for feedback. It therefore has to read as a shipping product a crew would trust, communicate the concept fast, and survive scrutiny of its content realism.

**Undecided / not established:** real backend, sync, authentication, content authoring for organisations, pricing, and which aircraft types ship beyond the prototype's three.

## Brand Commitments

- Product name **Easy Memory Item**, short name **EMI**. Site: easymemoryitem.com.
- The official EMI logo is used unmodified across all app icons (`icons/logo-1466.png` is the untouched original; every other icon is a straight downscale).
- Brand blue `#0E4EA8` is the current manifest `theme_color` / `background_color` and runs through the UI.
- The user did not confirm the mark or the blue as *binding* during this interview — treat them as the incumbent identity in active use, not as a locked constraint. Ask before replacing them.

## Evidence on Hand

- Real A320-family content in the prototype: ten Normals checklists, three Abnormal, four Emergency, four Memory Items, twelve limitations, twenty-four SOP entries across four groups, five+ quiz questions.
- The official brand mark, in `icons/`.
- **Absent — must not be fabricated:** customer names, testimonials, user counts, training-outcome statistics, certifications or regulatory approvals, pricing, and any claim about airlines using the product. Sample data (user "Jonas", 87% proficiency, leaderboard entries) is placeholder, not evidence.

## Product Principles

1. **Content accuracy outranks presentation.** A prettier layout that alters a limitation value or checklist wording is a defect, not a tradeoff.
2. **The cockpit layout is the study surface.** Learning happens in the shape of the real procedure; don't abstract content away from the form the pilot will meet it in.
3. **Offline is the normal case.** Design for no network as the default state, not the error state.
4. **Pilot and organisation are equal halves.** Neither the solo learner nor the training department gets designed around.
5. **It must feel like a product, not a mockup.** The demo's job is to be trusted by crews, buyers, and investors on sight.

## Accessibility & Inclusion

No product-specific requirement was established in the interview, but the code establishes one: a **44px minimum touch target** (`--tap: 44px`), enforced on visually smaller controls via an invisible `.emi-tap::after` hit-area extension rather than by growing the control. Treat this as binding.

Note the real usage scene: bright cockpits, glare, one-handed phone use, and eyes-off-screen moments — legibility and touch-target size carry more weight here than in a desk app.
