# Anchorman Handyman Services — repo conventions

Small static brochure site for a solo handyman (David Evans, Tampa Bay).
Personal project — not related to Inkkeeper/voidroot repos. Read `context.md`
for the business brief, decisions made, and open questions.

## Stack (chosen 2026-11-07)

Plain HTML/CSS, no build step, no dependencies: `index.html` (single page,
anchored sections) + `styles.css` + `_headers` (Cloudflare Pages headers).
`assets/logo.png` is the favicon. Serve the repo root — `file://` or any
static host works. Target hosting is Cloudflare Pages connected to the
private GitHub repo. Rationale and rejected options live in `context.md`.

## Before changing UI

Read `.agents/skills/making-ui-changes/SKILL.md`: reuse before you create,
cover every state in the same change, and prove the change visually at phone
AND desktop widths before calling it done.

## Hygiene

`.devin/rules/git-hygiene.md` — no `git add -A`, no secrets, `assets/source-docs/`
stays untracked. `.devin/rules/media.md` — strip EXIF/GPS from every published
photo (these are customers' homes), downscale phone shots for web, keep
originals separate.

## Customer-facing copy rules

- Primary CTA is "text me" (813-384-0975) — call and email are secondary.
- Never claim "licensed & insured" or similar without written confirmation
  from David.
- Keep everything a customer reads plain and local: services, service area,
  how to reach him. No jargon, no dark patterns.
