# Robbins Arbitration — Project Reference

Standing context for this site. This file exists because Claude Code sessions don't have access to the design conversation that produced this site — treat everything below as settled decisions, not open questions.

## What this project is
The live website for Tim Robbins, an independent international arbitrator, at robbinsarbitration.com. Six static HTML pages, deployed via GitHub Pages (repo: `tfrobbins6/robbinsarbitration`).

## Core working rule
Don't make independent design decisions. Follow existing HTML/CSS patterns exactly when extending or fixing the site. If a fix is ambiguous, or a "consistency" pass would mean changing something that might be intentional rather than a bug, ask before changing it — don't guess. This applies especially to anything page-specific (see below) that might look like an inconsistency but isn't.

## Local development & deployment

* Project lives at `~/Sites/robbinsarbitration`. Plain static site — no build step, no framework, no package manager.
* Local preview: a Python server on port 8934, launched via `.claude/launch.json`.
* Deployment: `git push` (over SSH) to `github.com:tfrobbins6/robbinsarbitration.git` → GitHub Pages builds from the `main` branch → served at robbinsarbitration.com.
* The `CNAME` file in the repo root (containing `robbinsarbitration.com`) is required for the custom domain and must not be removed.
* Confirm with Tim before pushing significant/visible changes live, rather than pushing and reporting after the fact.

## Brand

* Navy: `#000073` — Brick red: `#8E0A00` (from the logo; used as sparing accents, not large color blocks)
* Base: white/neutral, generous whitespace, minimal motion. Tone is "understated authority" — not flashy, not corporate-generic.
* Typography: EB Garamond (serif) for headings, Inter (sans-serif) for nav/labels/body UI text.
* Logo: use the provided file exactly — never recolor it or redraw an approximation of it. Its colors only read correctly on light/white backgrounds. If it ever needs to sit on a dark background, give it a white backing plate rather than altering the mark itself.

## Site structure

1. `index.html` — Home
2. `education.html` — Education & Qualifications
3. `arbitration-experience.html` — Arbitration Experience
4. `academic-professional.html` — Academic & Professional Activities
5. `contact.html` — Contact
6. `privacy-policy.html` — Privacy Policy

## Header and footer

* The masthead (dark, sticky nav bar) and identity band (logo/name/role) should be consistent across the five subpages.
* The homepage's identity band is intentionally different — it's merged into a two-column layout with Tim's portrait photo, and the logo/name are sized larger than on subpages. This is deliberate, not something to replicate onto the subpages or something to "fix" toward matching subpages.
* Each subpage's own hero/banner (photo + page title) below the identity band is page-specific — not part of the shared header.
* Footer content and exact treatment per page (full address block vs. slimmer version) has been actively discussed and adjusted — check current state and ask before assuming what's "supposed" to be there rather than applying a blanket rule.

## Content rules

* All copy comes from Tim's actual CV or his direct instructions — never invent or embellish professional facts (case details, dates, institutions, etc.).
* No small "eyebrow" labels above page titles or section headings anywhere on the site — these were deliberately removed.
* Case-record content (the arbitration matters list, Panel Appointments, etc.) and other page-specific components (the ledger-style layouts, Contact's office block layout, the Academic & Professional Activities table-of-contents) are intentionally different from each other — a "make things consistent" pass should not flatten these into a single shared style.

## Known technical gotchas

* The masthead is `position: sticky`. Any same-page anchor links (TOC jumps, "back to top") need `scroll-margin-top` on their targets (or an id placed off the sticky element) so the sticky bar doesn't cover the destination — this has bitten us before.
* DNS at GoDaddy has several records unrelated to the website (MX, TXT, autodiscover CNAME) that keep `tim@robbinsarbitration.com` email working — never touch these when working on anything DNS-related.

## Contact details (for reference, not to be treated as editable content without instruction)

* Email: tim@robbinsarbitration.com
* LinkedIn: https://www.linkedin.com/in/tim-robbins-15881610/
* The Hague: Jan Pieterszoon Coenstraat 7, 2595 WP, The Netherlands — +31 6 2550 4785
* Hong Kong: 7/F, Low Block, Grand Millennium Plaza, 181 Queen's Road Central — +852 5905 5668

## Credentials
Never handle a password, personal access token, or other credential on Tim's behalf, even if offered directly — ask him to enter it himself in his own terminal.
