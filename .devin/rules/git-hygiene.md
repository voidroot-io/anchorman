---
description: "Secrets/commit hygiene — read before committing env or config files or editing .gitignore"
trigger: model_decision
---

Git Hygiene Rules: Anchorman site

Adapted from the inkkeeper repo's hygiene rules (generic parts kept).

Never Commit (secrets / personal)
`.env*` files of any variant. Credential material of any kind: `*.pem`,
`*.key`, `*.p12`, `*.pfx`, `credentials.json`, `service-account*.json`.
`assets/source-docs/` — David's contact card and a questionnaire containing a
plaintext password live there; keep it gitignored forever.

Never Commit (generated / machine-local)
`node_modules/`, build output (`dist/`, `out/`, `build/`), caches, `*.log`,
`.DS_Store`, `Thumbs.db`, `.idea/`.

Working Practices
- Never `git add .` or `git add -A`; stage explicit paths so untracked local
  artifacts and secrets can't slip in.
- Never bypass hooks (`--no-verify`) and never force-push to `main`.
- If a secret is ever committed, treat it as compromised: rotate it, then
  scrub history.
- Scratch files (notes, one-off scripts, screenshots) stay out of the repo or
  under an ignored `.scratch/`.
- This repo may go public (free static hosts serve public repos). Anything in
  the tree is world-readable — treat it that way before every commit.
