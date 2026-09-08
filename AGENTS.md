# AGENTS.md

Guidance to AI agents working in this repository.

## Project status — read this first

- **Current phase: THINKING / BRAINSTORMING the target product (AI4CEO): its user story and features.** No product code exists yet.
- The product being defined: an **AI Strategy diagnostic tool for SMB CEOs** (assess AI threats/opportunities on the business model, then assess and prioritize where to implement AI). Live state and next action: [Progress.md].
- Master input for the brainstorm: [ideasup/5-user-story-INPUT.md] (all decisions made so far, all sources classified, open questions). Stage artifacts: [ideasup/].
- Thinking sources: [docs/] — product spec drafts, the existing "Strat interview" Apps Script V0 source, and the list of external source documents.
- AI4BUSINESS retro-spec ([docs/ai4business_retro_spec.md], [docs/ai4business_db_schema_notes.md]): **read §0 (tree) only.** Open detail sections only when a specific feature/table ID (F-xx / C-x) is being evaluated, reused, or rebuilt.
- The existing website ([index.html]) is **only a landing page** for the venture — it is NOT the product. Its rules below apply when (and only when) editing it.

## Landing page (index.html) — rules

### Files

- Landing page spec: [macro_prd.md] · Design system: [design.md] · 1 single HTML/CSS/JS file: [index.html].

### Intent

- B2B landing page: a CEO speaking to other CEOs about AI in the CEO role. Conversion goal = sign-up to a monthly inter-CEO workshop. Advanced prototype: forms send no data on submit.
- Pages: see macro_prd.md § WEBSITE PAGES.

### Hard technical constraints (do not relax without asking)

- **Single HTML file.** CSS inside `<style>`, JS inside `<script>`.
- **No framework, no CDN, no external asset, no database.** Site must work fully offline from one file.
- JS scope limited to: mobile menu, form handling, in-page navigation / page-or-section switching, optional video modal
- Responsive
- Design method: google-labs-code/design.md best practices. Visual inspiration: fr.ippon.tech (sober, modern, professional). Project design system: see [design.md].
- Multi-page navigation must be implemented as **client-side section show/hide inside the single file** (only 1 HTML file)
- Comments only where they add value
- Class names must be readable and consistent
Apply DRY / YAGNI strictly.

### Editorial rules (enforce when writing copy)

- Audience: francophone CEOs of 100+ employee companies, AI-curious but non-technical.
- Tone: PDG-to-PDG, sober, direct, credible. No selling, only testifying.
- Avoid: "révolutionnaire", "disruptif", "game changer", marketing buzzwords, anglicisms, technical jargon.
- Prefer: concret, usage, recul, responsabilité, arbitrage, sérénité, leadership.
- Per screen: 1 strong title + 1 explanatory sentence + 1 illustration (when no cards) + at most 3 bullet points. Low density.

## Workflow expected by the founder (strict)

### When starting work:

1. Plan the tasks/phases
2. Wait for validation.

### Per user request:

1. Always start by defining the tasks
2. Implement -> check tasks -> test
3. Explain how to test (if applicable)
4. Wait for user validation -> Continue.

Founder-facing communication: plain sentences the founder (product designer, non-technical) can arbitrate on — no compressed jargon.

## Deployment target (informational — landing page only)

- GitHub repo → Coolify → Hostinger VPS.
- Nothing in the code should depend on that pipeline; static single-file hosting is sufficient.
