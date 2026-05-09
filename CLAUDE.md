# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository status

This repo currently contains only the project specification: [Prompt - Spécification.txt](Prompt - Spécification.txt). No code, build system, package manager, or tests exist yet. The first implementation work should follow the phased plan requested at the bottom of that spec ("Phase 1 → validation → Phase 2…").

## Project intent

Advanced **prototype** (not production) of a B2B consulting site: a CEO speaking to other CEOs about how AI helps in the CEO role. Conversion goal = sign-up to a monthly inter-CEO workshop (single CTA on the home page). The form does not actually send data — display "Prototype > 0 donnée envoyée ou stockée" on submit.

Pages (numbered by spec, not by nav order):
- Page 1 — Home "IA pour PDG" (6 screens, one key message per screen, including embedded YouTube testimonial `https://www.youtube.com/watch?v=stcfbhiuoHo`)
- Page 2 — "Entre PDGs" workshop sign-up form
- Page 3 — "Réflexions" (notes)
- Page 4 — "CEO Starter Kit" (diagnostic + prompt-generator tools; their code will be supplied separately — leave a clean integration seam)

## Hard technical constraints (from spec, do not relax without asking)

- **Single HTML file.** CSS inside `<style>`, JS inside `<script>`.
- **No framework, no CDN, no external asset, no database.** Site must work fully offline from one file.
- JS scope is limited to: mobile menu, form handling, in-page navigation / page-or-section switching, optional video modal. Do not add anything beyond that.
- Responsive. Design system reference: https://fr.ippon.tech (professional, modern, sober).
- Multi-page navigation must be implemented as **client-side section show/hide inside the single file** (since there is only one HTML file).
- Comments only where they add value. Class names must be readable and consistent. Apply DRY / YAGNI strictly.

## Editorial rules (enforce when writing copy)

- Audience: francophone CEOs of 100+ employee companies, AI-curious but non-technical.
- Tone: PDG-to-PDG, sober, direct, credible. No selling, only testifying.
- Avoid: "révolutionnaire", "disruptif", "game changer", marketing buzzwords, anglicisms, technical jargon.
- Prefer: concret, usage, recul, responsabilité, arbitrage, sérénité, leadership.
- Per screen: 1 strong title + 1 explanatory sentence + at most 3 bullet points. Low density.

## Workflow expected by the spec author

The spec explicitly asks the IA-Coder to:
1. Propose the code architecture (and alternatives if a single one is not reasonable).
2. Propose a phased coding plan where **each phase is testable before moving on**.
3. Produce phase 1, stop, explain how to test it, wait for validation, then continue.

Respect this loop — do not ship the whole site in one pass.

## Deployment target (informational)

GitHub repo → Coolify → Hostinger VPS. Nothing in the code should depend on that pipeline; static single-file hosting is sufficient.
