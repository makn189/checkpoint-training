# Checkpoint — Licensing law & Challenge 25 training site

## What this is
An e-learning site for UK retail employees, covering licensing law and
Challenge 25. Two audiences:
1. All staff — short, practical modules (Challenge 25, ID checks, refusals)
2. Prospective personal licence holders — a **non-accredited warm-up**
   for the real APLH qualification (not a substitute for it — must never
   be worded as accredited or certified)

## Brand
- Name: **Checkpoint**
- Tone: plain-language first, legal term second. Written for someone on
  a shop floor, not a compliance officer.

## Scope change
- Site now holds **one course only** — no multi-course catalogue, no
  course grid on the landing page. Simplify navigation and any "browse
  courses" UI accordingly; the landing page should sell/explain the one
  course and lead straight into it.

## Design reference
- Visual reference: "ZenEd" learning platform by Design Monks
  (https://dribbble.com/shots/25606603-ZenEd-Online-Learning-Platform-Design)
  — clean, modern EdTech aesthetic. Exact palette/layout details not yet
  extracted from the shot (image wasn't viewable when this brief was
  written) — confirm specifics with the user or ask for a screenshot
  before assuming a full redesign matches it.

## Design system (current build — may be revised toward ZenEd reference above)

- Fonts: Fraunces (serif, headings) + Inter (body), via Google Fonts
- Palette: cream `#FBF7F1` background, ink `#22243B` text,
  lavender `#6E62E5` primary, peach `#FFC49B` / mint `#AEE3C8` / coral
  `#FF7A59` as accents
- Style: rounded cards, soft blob shapes, floating status cards, pill
  buttons — warm SaaS look (reference: Rise.com), not corporate/sterile
- Radius: 24–28px large containers, 16–18px cards

## Files in this folder
- `favicon.svg` — shield-and-checkmark mark (solid `#4E3FD1` lavender-deep,
  white check), used as the site favicon and reused inline as the small
  logo mark in the nav/footer on every page, and on the downloadable
  certificate.
- `index.html` (formerly `checkpoint-licensing-training-mockup.html`) — marketing/landing page, renamed so GitHub Pages serves it at the site root.
  Course grid links to the live course; other two cards are styled as
  "Coming soon" placeholders (no href).
- `checkpoint-course-player-full.html` — fully built, interactive
  9-module Challenge 25 & Acceptable ID course (includes a module on
  the digital ID rules that took effect 15 September 2026). Each module
  ends in a 10-question test (80% to pass, gates progress to the next
  module), with sidebar navigation, a streak stat, and a downloadable
  certificate on completion. Content and lesson list are hardcoded in a
  JS array inside the file (`lessons = [...]`). Fully bilingual: an
  EN/CY toggle in the topbar (matching `index.html`'s) swaps every
  lesson, quiz, and piece of UI chrome via a `lessonsCY` array + a `t()`
  string dictionary, and reads/writes the same `checkpoint-lang`
  localStorage key as the landing page, so a language choice made there
  carries straight into the course.
- `resources.html` — free downloadable templates page (currently three:
  a Refusal of Sales Log Sheet .docx, an Age By Year of Birth
  Calculator PDF, and a Due Diligence Checklist .docx, all in
  `resources/`). Linked from the main nav and footer.

## Content status — IMPORTANT
- Challenge 25 module: 9 lessons, fully written, but this is **mockup
  content** — grounded in the real Challenge 25 scheme basics, not
  legally reviewed. Flag clearly if asked to treat it as production-
  ready; it should be checked by someone licensing-literate before real
  staff rely on it.
- Welsh (CY) translation of the course — like the landing page's — is
  **AI-generated and not reviewed by a professional Welsh speaker**.
  The in-course `#lang-caveat` banner says so whenever CY is active;
  keep that caveat if the Welsh content is ever edited or extended, and
  flag clearly if asked to treat it as review-ready.
- "Licensing Law Annual Refresher" and "Personal Licence Warm-Up"
  modules: **not written yet** — landing page cards exist but link
  nowhere.

## What's NOT decided yet (ask, don't assume)
- Static site vs. framework (Next.js etc.) — matters if user accounts,
  completion tracking, or certificates are wanted later
- Hosting/deployment target
- Whether course progress needs to persist per-user (currently all
  client-side JS state, resets on reload)
- Real company name/domain if this goes further than a demo

## Working style
- This project came out of a design conversation in Claude chat, not
  from a formal spec — confirm assumptions rather than guessing when
  scope is unclear.
- Never word anything as an accredited/certified APLH qualification.
