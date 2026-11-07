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

## Live preview (2026-11-07)

Site is live at **https://voidroot-io.github.io/anchorman/** — GitHub Pages,
repo `voidroot-io/anchorman` flipped **public** to enable it (revert to
private if it moves to Cloudflare). Push to `main` = auto-deploy. `_headers`
is Cloudflare-specific and ignored by Pages; og:image URL is hardcoded to the
Pages host — update both if the host/domain changes.

Derived logo assets (generated, regenerate from `assets/logo.png` if a better
source arrives): `logo-emblem.png` (roundel crop, white bg flood-filled to
transparent — reads as white-line art on navy), `logo-lockup.png` (full
transparent lockup — navy wordmark, unusable on dark), `favicon.png`,
`og.png`. Self-hosted Oswald variable font in `assets/fonts/` sets the
live-text wordmark.

## Stack (decided 2026-11-07)

**Plain HTML/CSS single-page site — no build step, no dependencies.**
`index.html` + `styles.css` + `_headers` (Cloudflare Pages security headers);
`assets/logo.png` doubles as favicon. Chosen over Astro/SSGs: the site is one
page, updates are rare, and zero dependencies is the extreme of the
"survive every tool dying" requirement. Revisit only if it grows past one
page or David really will self-edit.

**Hosting target: Cloudflare Pages** (git-connected, $0/mo). Repo lives on
GitHub under Sean's account (private) — backup + push-to-deploy + keeps the
Pages CMS self-edit path open (Pages CMS is GitHub-login). GitHub Pages is
the equally-valid fallback host. No domain yet — build is host-agnostic.

Single page with anchored sections: header (sticky "Text me"), hero,
services, photos (marked up, commented out until real photos arrive), about,
contact, footer. Primary CTA is `sms:` with prefilled body. JSON-LD
`HomeAndConstructionBusiness` for local SEO.

Rejected: WordPress (on-call/security burden for 4 static pages), Carrd
($19/yr + content not in git), Astro/SSG (unneeded machinery at this scale).

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
- Logo source: who made it, and is there a vector/higher-res original
  (AI/EPS/SVG/PDF, or a bigger PNG)? The 792px raster is the only source; it
  looks AI/clip-art shaded. Current site works around it (emblem crop on
  navy, live-text wordmark), but a real source file would sharpen everything.

## Draft reply for mom (NOT SENT — Sean reviews/sends when ready)

Plain-English answers back to her questionnaire plus the outstanding asks.
Numbered like her doc so it's easy to respond point-by-point:

```
Got the answers — that helps a lot. A few things back:

1. Facebook page: yes I can help set that up. One thing though — the
   password in the doc is short and it was sent over email/text in
   plaintext, so once we're in he should change it to something longer.
   Also, a Facebook business page has to be owned by a personal account:
   easiest is I create it under mine and add David as admin once he has
   a Facebook login, or I walk him through making his own.

2. Google Maps: I'll get him set up on Google Business Profile — that's
   honestly the bigger win for a handyman, it's where the calls come
   from. Google will need to verify him at his phone/address, so he'll
   need to be involved for one step; I'll prep everything else.

3. Domain: still need a yes/no — does he want something like
   anchormanhandyman.com or davidshandyman.com (~$12/year), or is a free
   web address fine for now?

4. Cost: no monthly cost — the site itself will run free. Only possible
   charge would be the ~$12/year domain if he wants one.

5. Text preferred — got it, and the "text me photos for a ballpark"
   workflow will be the main button on the site. That's a great hook.

6. Photos: whenever the old-phone ones are recovered, send them my way
   (or a shared folder). More real job photos = better site.

Two more quick things to ask him:
- Can the site say "licensed & insured"? Only if it's actually true —
  Florida is picky about handyman claims, so I won't print it otherwise.
- What's his actual services list? (drywall, fixtures, fence, paint,
  TV mounting…?) The logo looks drywall-ish but I don't want to guess.
```

## Sensitive-data note

`assets/source-docs/` contains David's contact card and a document with a
**password in plaintext**. The folder is gitignored. Never copy its contents
into tracked files, the site, or commit messages. Never publish the raw vcf.

## Repo conventions

See `AGENTS.md` and `.devin/rules/`. Global `~/.devin` rules (model routing,
session-efficiency coach) apply to any session in this folder automatically.
