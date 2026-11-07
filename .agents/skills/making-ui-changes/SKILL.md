---
name: making-ui-changes
description: Read before changing any component, page, or styles. Five moves to change UI without silently breaking another screen - reuse before you create, cover every state, check the blast radius, prove it visually at phone and desktop widths.
---

# Making UI changes

Adapted from the inkkeeper repo's making-ui-changes skill, made stack-agnostic
for a small static site. Run these five moves on any UI change.

## 1. Reuse before you create

Extend an existing component/partial/utility class instead of adding a
near-copy. Two things that look the same drift apart. Build net-new only when
nothing fits.

## 2. Cover every state, in the same change

Every component or state you add or change is proven in the same change, never
a follow-up. For this site the states that matter: phone width AND desktop
width on every page, plus interactive states (nav open/closed, form
success/error, gallery lightbox).

## 3. Check the blast radius

Editing a shared partial, layout, or utility class changes every page that
uses it. Grep the usages, decide which pages this touches, and check each one
renders right.

## 4. Prove it visually

Not done until you've looked at it: screenshot the changed pages at a phone
width (~375px) and a desktop width (~1280px) — Playwright or the browser
devtools device toolbar — and eyeball the result before committing. A page
you didn't mean to change that moved is a stop-and-look (usually move 3).

## 5. Kill flake at the source

Anything non-deterministic in a screenshot (dates, randomness, animations)
gets frozen or disabled at capture time — don't accept noise as a baseline.
