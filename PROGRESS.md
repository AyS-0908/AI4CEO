# Progress — AI4CEO

Shared project memory (per AGENTS-canonical). Update at every stop.

**Mission:** define and build AI4CEO — an AI Strategy diagnostic tool for SMB CEOs — run as the first live end-to-end test of the skills system (define → make → roast → formalize). Stages: folder-cleaning → doc-hygiene → ideasup-flow → Spec→Plan gap-fill → code-audit-loop build.

**CURRENT PHASE: THINKING/BRAINSTORMING the target user story & features**, from a wide set of sources (spec drafts, the working "Strat interview" V0, use-case catalogs, GPT instructions, course, shipped extension). The existing website (`index.html`) is only the venture's landing page, not the product.

---

## Status — 2026-07-09

**DONE**
- Read `SKILLS-DESIGN.md` + `AGENTS-canonical.md` for the run's rules.
- **Stage 1 — folder-cleaning: COMPLETE. Verdict: folder already clean, nothing to reorganize.**
  - 8 real items (`AGENTS.md`, `CLAUDE.md`, `design.md`, `index.html`, `macro_prd.md`, `.gitignore`, `.github/workflows/manual-coolify-deploy.yml`, `desktop.ini`) — all correctly placed. `desktop.ini` already gitignored.
  - Ran the deterministic pipeline (artifacts in scratchpad, nothing written to repo). Stopped before host-analysis on purpose — see rough edge.
  - **Rough edge logged** in `_AI_SKILLS/skill-folder-cleaning/skill_plan.md`: skill has no `.git`/VCS exclusion → scanned 46 files (38 git plumbing) and reported 2 phantom "duplicate groups" (normal git refs). Real defect for any git repo; feeding git internals to LLM analysis is wasteful + risky.

- **Stage 2 — doc-hygiene: COMPLETE.** APPLY pass (delegated to sub-agent, then a FRESH auditor sub-agent verified → GREENLIGHT-WITH-NITS; the 1 nit, a wrong `§` pointer heading in macro_prd.md, fixed inline).
  - Edits: fixed broken `functional_spec.md` ref in AGENTS.md; rebuilt macro_prd.md's stale/wrong page list to the code's real 5 pages; de-duplicated triplicated editorial rules → owner AGENTS.md + pointers in macro_prd.md & design.md; cut design.md's stale phase roadmap; untangled AGENTS.md's garbled design ref. No fact lost. Files changed: AGENTS.md, macro_prd.md, design.md (uncommitted).
  - **Rough edges logged** in `_AI_SKILLS/skill-doc-hygiene/skill_plan.md`: (1) broken-ref scan not applied to pointers the pass itself writes — MEDIUM; (2) no forced fresh-audit when run standalone; (3) ownership map hardcoded to GO_VIRAL filenames.

- **Stage 3 — ideasup-flow: IN PROGRESS (2026-07-10).** Direction pivot by founder: product = **AI Strategy tool for SMB CEOs** (per `docs/ai4ceo_spec_1_DRAFT.txt`; `docs/ai4ceo_spec_2_DRAFT.txt` = adjacent input). Pain/Opportunity fast-tracked by founder decision (no web research — honestly labeled); effort reserved for Stage 5 User Story brainstorm.
  - DRAFT artifacts written (maker sub-agent) + fresh-audit GREENLIGHT-WITH-NITS: `ideasup/1-pain.md` (4 clusters), `ideasup/2-opportunity.md` (1 pre-selected opportunity, skeptical check: "would not fund on evidence alone"), `ideasup/3-idea.md` (idea + 3 operator angles A self-serve / B consultant-operated / C workshop-companion, reco B-then-A).
  - Founder decisions recorded: operator = DUAL-MODE (self-serve CEO creates 1 business; consultant creates N clients — same flow); ambition = 150K–1M/yr confirmed; flow PAUSED at User Story × Features for open brainstorm (founder's explicit choice — no mechanical descent of the pipeline).
  - All brainstorm sources ingested and classified (2026-07-10 → 07-12), including the V0 source supplied as `docs/ai4ceo_aistrat_interview_tool_draft.txt` (working "Strat interview" Apps Script wizard; paused because questions are hardcoded). **Full inventory + classification: see `ideasup/5-user-story-INPUT.md` §2 (owner).** Key synthesis: the assets already form an AI4CEO SUITE (Diagnose → Prioritize → Act → Train → Equip); five scoring systems must be unified; real pricing evidence exists.
  - Founder corrected the proposition (2026-07-12): his one-liner (strategy first, then execution planning) + the journey branches at FRAME into "Strategy" and/or "Operations". Foundation file rewritten accordingly — plain language, 9 open questions. Founder-facing communication rule: plain sentences, no compressed jargon (also in global memory).
  - **The brainstorm foundation is `ideasup/5-user-story-INPUT.md`** — a fresh session needs only that file (+ `ideasup/3-idea.md`, this Progress.md). The ready-to-paste session prompt was delivered to the founder (also derivable from §7 of the foundation file).

**OPEN**
- Stage 3 (cont.) — Stage 5 User Story deep brainstorm (founder's focus), then Stage 6 Mockup, Stage 7 Specification.
- Stage 4 — Spec→Plan gap-fill (known missing skill; design deliverable for SKILLS-DESIGN plan item 4). Not started.
- Stage 5 — build phase-by-phase via code-audit-loop. Not started.

**NEXT ACTION (User):** start a fresh session with the ready-made prompt to run the Stage-5 User Story × Features brainstorm (one question at a time, 9 questions in `ideasup/5-user-story-INPUT.md` §5). Also open: nothing is committed yet — one commit ("AI4CEO product definition: stages 1–3 + brainstorm foundation") is recommended before the next session.

**IMPORTANT FILES**
- `ideasup/5-user-story-INPUT.md` — the brainstorm foundation (decisions, source map, journey, open questions). THE file to read first.
- `ideasup/1-pain.md`, `2-opportunity.md`, `3-idea.md` — validated stage artifacts feeding the foundation.
- `docs/` — raw thinking sources (spec drafts, V0 Apps Script source, external source list).
- `docs/ai4business_retro_spec.md` + `ai4business_db_schema_notes.md` — retro-spec of the AI4BUSINESS Glide prototype. Read §0 tree only; details on demand per F-xx ID (rule in AGENTS.md).
- `index.html` — the venture's landing page only (rules in AGENTS.md); `macro_prd.md` + `design.md` document that landing page.
- `_AI_SKILLS/SKILLS-DESIGN.md` (system being tested), per-skill `skill_plan.md` (where rough edges go).
