# AGENTS.md

Guidance to Codex (Codex.ai/code) when working in this repository.

## Repository status

- Functional specification: [functional_spec.md]
- 1 HTML, CSS, JS file: [index.html]
- Design system: [design.md].

## Project intent

- B2B consulting site (a CEO speaking to other CEOs about how AI in a CEO role) 
- Conversion goal = sign-up to a monthly inter-CEO workshop 
- Advanced **prototype** (not production). The workshop registration form does not send data on submit.

Pages:
- Page 1 — Home "IA pour PDG": PDG testimony
- Page 2 — "Entre PDGs": workshop sign-up form
- Page 3 — "Réflexions": PDG notes
- Page 4 — "PDG Starter Kit" (diagnostic + prompt-generator tools; their code will be supplied separately — leave a clean integration seam)
- Page 5 — Contact form.

## Hard technical constraints (from spec, do not relax without asking)

- **Single HTML file.** CSS inside `<style>`, JS inside `<script>`.
- **No framework, no CDN, no external asset, no database.** Site must work fully offline from one file.
- JS scope limited to: mobile menu, form handling, in-page navigation / page-or-section switching, optional video modal
- Responsive
- Design system: customize [https://github.com/google-labs-code/design.md] best practices to design of https://fr.ippon.tech (professional, modern, sober)
- Multi-page navigation must be implemented as **client-side section show/hide inside the single file** (only 1 HTML file)
- Comments only where they add value 
- Class names must be readable and consistent
Apply DRY / YAGNI strictly.

## Editorial rules (enforce when writing copy)

- Audience: francophone CEOs of 100+ employee companies, AI-curious but non-technical.
- Tone: PDG-to-PDG, sober, direct, credible. No selling, only testifying.
- Avoid: "révolutionnaire", "disruptif", "game changer", marketing buzzwords, anglicisms, technical jargon.
- Prefer: concret, usage, recul, responsabilité, arbitrage, sérénité, leadership.
- Per screen: 1 strong title + 1 explanatory sentence + 1 illustration (when no cards) + at most 3 bullet points. Low density.

## Workflow expected by the spec author (strict)

Explicitly instruction to the IA-Coder:

### When starting the project:

1. Plan the implementation phases
2. Wait for validation.

### Per user request:

1. Always start by defining the tasks
2. Implement -> check tasks -> test 
3. Explain how to test (if applicable)
4. Wait for user validation -> Continue.

## Deployment target (informational)

- GitHub repo → Coolify → Hostinger VPS. 
- Nothing in the code should depend on that pipeline; static single-file hosting is sufficient.
