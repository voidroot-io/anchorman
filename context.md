# Anchorman — project context

Handoff written 2026-11-07 by a Devin session in the inkkeeper workspace, at
Sean's request, so a fresh session on this folder alone has everything it
needs. Read this file first.

## What this is

A personal project, not Voidroot/Inkkeeper work. Sean is building a website
for **David Evans**, a friend of Sean's mom. David is a solo handyman; the
site is a small brochure site, not a product.

## Business facts (from `assets/source-docs/David Evans.vcf`)

- **Name:** Anchorman Handy Man Services LLC
- **Owner:** David Evans
- **Phone (preferred contact — TEXT):** 813-384-0975
- **Email:** anchormanhandymanservices@gmail.com
- **Service area:** Tampa, St. Petersburg, Clearwater, and surrounding areas (FL)
- **Logo:** `assets/logo.png` — anchor + drywall screw, navy/gray, tagline "Anchored in Quality"

## Questionnaire answers (docx/pdf in source-docs — same content both files)

- **Facebook business page:** none — David asked if Sean can create it.
- **Google Maps/GBP:** not listed — "would be great to happen."
- **Custom domain:** unanswered (example floated was davidshandyman.com).
- **Budget:** **No payment at the moment.** Maybe in the future. (Sean is OK
  covering a small amount if clearly worth it, but plan for $0 recurring.)
- **Contact preference:** text preferred. For small jobs he gives ballpark
  quotes from customer-texted photos + description; bigger jobs he meets on
  site. → The site's primary CTA should be "text photos of your job."
- **Phone:** Android. He can take/upload his own photos; old-phone photos are
  being recovered via the T-Mobile store.

## Constraints & decisions made so far

1. **$0 recurring is the hard requirement** (David's answer). Only acceptable
   recurring cost is a domain (~$10-15/yr) if he wants one — undecided.
2. **Updates will be rare** (new photos/testimonial occasionally) — do NOT
   build heavy CMS machinery for this. A CMS is optional convenience, not a need.
3. **Longevity matters to Sean** — avoid tools that die. The durable answer:
   content as plain files in git. Any tool can die; the site survives.
4. **David edits it himself** — or realistically, rarely enough that Sean
   doing it is also fine. Self-edit path should still exist.

## Stack recommendation (from prior research — validate before building)

**Recommended: static site (Astro or plain HTML) + free hosting + optional
Pages CMS for self-editing.** Repo in git, deploy to Cloudflare Pages or
GitHub Pages — $0/mo. Pages CMS (app.pagescms.org, free, MIT, GitHub-login)
gives him a browser editor with no backend to run; Sveltia CMS is the
alternative if he edits at /admin (needs a one-time Cloudflare Workers OAuth
app, also free).

Runner-up if he'd rather have a hosted editor: **Carrd Pro ~$19/yr**.
**WordPress ruled out**: 4 pages updated rarely doesn't justify the
update/security/on-call burden.

## Non-site work items (manual, for Sean/David — the session can't do these)

- **Facebook business page:** needs creating. A password was supplied in the
  questionnaire (see source-docs — do NOT commit or echo it; it is weak and
  was shared in plaintext — worth telling David to pick a better one).
  The session can draft ready-to-paste page content (name, category,
  description, hours, CTA) but account creation is a human step.
- **Google Business Profile:** claim/create — verification is tied to
  David's phone/address, so he does it; the session can draft the profile
  content. **This matters more than the website for a handyman** — it's how
  he gets calls. Sequence: GBP first, site second.
- **Domain:** decide with David. If yes, buy via a cheap at-cost registrar
  (e.g. Cloudflare ~$10/yr).

## Open questions for Sean / mom / David

- Domain: yes/no, and what name (davidshandyman.com vs anchormanhandyman.com)?
- Can the site say "licensed & insured"? Do not print it unless true — FL is
  picky about handyman vs. contractor claims.
- Services list (what jobs does he take — drywall, fixtures, fence, paint…?).
  The logo implies drywall (screw + patch motif) but confirm.
- Hours / service days.
- Photos: ETA on recovered old-phone photos; any reviews/testimonials to quote?
- Licensed business name on the site: "Anchorman Handy Man Services LLC" vs
  the shorter "Anchorman Handyman" styling in the logo.

## Sensitive-data note

`assets/source-docs/` contains David's contact card and a document with a
**password in plaintext**. The folder is gitignored. Never copy its contents
into tracked files, the site, or commit messages. Never publish the raw vcf.

## Repo conventions

See `AGENTS.md` and `.devin/rules/`. Global `~/.devin` rules (model routing,
session-efficiency coach) apply to any session in this folder automatically.
