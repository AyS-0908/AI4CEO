# Stage 5 INPUT — Brainstorm Foundation (AI4CEO)

- Date: 2026-07-12 · Status: FOUNDATION for the User Story × Features brainstorm
- Purpose: define the target user story and related key features for the AI4CEO project.
- Input: 
    - some food-for-thoughts (only) material from previous reflections and prototypes of the user. They are not a constraint and must be used only when relevant/usefull.
    - everything a FRESH session needs to run the detailed brainstorm whose output = validated `ideasup/5-user-story.md` (clear User Story + feature list). 
- The founder: a product designer/manager, non-technical: **all founder-facing output must be plain language, full sentences, no compressed jargon** (compressed style is acceptable only inside AI-to-AI prompts).

---

## 1. DECISIONS LOCKED (do not reopen)

| Decision | Value |
|---|---|
| Product | AI Strategy diagnostic tool for SMB CEOs (product language English and, ideally, also French according to building complexity) |
| One-liner (founder's own wording) | "As a CEO, I can assess the opportunities and threats of AI for my company (**strategy**); then concretely assess and prioritize where to implement AI in my company (**execution planning**)." |
| Operator | DUAL-MODE, same flow: a CEO uses it for his 1 company (self-serve); a consultant uses it for N client companies. Identical journey. |
| Ambition | 150K–1M €/yr |
| Journey shape | At the start the user chooses the diagnosis type: **"Strategy"** and/or **"Operations"** — two branches after a common FRAME step (see §4) |
| Method | Brainstorm User Story × Features BEFORE any further pipeline descent |
| Old docs status | `index.html` = the venture's **landing page only** (stays live); `macro_prd.md` / `design.md` document that landing page — none of the three defines the product |

## 2. SOURCE MAP (all ingested and classified)

Note: only food-for-thoughts, not a constraint to define the target design (user story and features).

| Source | Key content | Class |
|---|---|---|
| docs/ai4ceo_spec_1_DRAFT.txt | Most mature spec draft: Google-Sheets diagnostic. company→mission→function scope→strategy questions + process scoring (criteria columns, value×feasibility bands)→Quick Win/Strategic/Defer→AI-generated report (Google Doc, versioned). Recommendation fields per item: WHY/RISK/TOOL/NEXT/EFFORT. Two flags has_strategy_diag / has_process_diag = the two branches the founder confirmed | Core draft (its scoring unit "process" and its scoring model are challenged — see §5 Q3/Q8) |
| docs/ai4ceo_aistrat_interview_tool_draft.txt | **THE WORKING V0** — full source of the live "Strat interview" Sheets tool: menu + 7-section wizard (S1 Context, S2 AI projects, S3 Market impact, S4 Processes, S5 Business opportunities, S6 Execution, S7 Wrap-up/priorities), sidebar progress, auto-save ~8s, resume via DASH_OVERVIEW, strict template validation. Data: DB_INTERVIEW, DB_SCOPE_VISION, DB_PROJECTS, DB_MARKET (4 Porter-style forces: Competition/Clients/Suppliers&Ecosystem/Regulation, each opportunities+threats scored), DB_PROCESSES (per process: 3 value scores accelerate/costs/quality + 3 feasibility factors determinism/data_quality/skills_buyin + existing tools), DB_EXECUTION (maturity scores: velocity, governance, culture, organization, skills, IT), REPORTS (aggregates + prompt/llm_response columns = report-generation seam). Known limits per its own README: questions hardcoded in code (main reason paused), rigid schema, no versioning. Founder backlog on the sheet: import free notes→AI structures→feeds tool; AI analysis of whole dataset; flexible sections; mobile webapp | 🔥 Confirms the wizard UX; richest scoring model; adds the EXECUTION-READINESS dimension |
| docs/ai4ceo_spec_2_DRAFT.txt | "AI Consultant" Sheets toolkit (17 tools, registries, pipelines) | Adjacent; source of the send-forms-to-people pattern + Docs/Slides export |
| docs/ai4ceo_spec_2_APPENDIX.txt | Consultant document mechanics: interview notes→AI merge→AI structuring→cross-interview synthesis; benchmark = questions×players web research; final synthesis | V2+ machinery |
| processor GPT instructions (OneDrive docx) | Taxonomy Macro-Function→Function→Deliverable→Key-Info (12 macro-functions); per deliverable: quantified savings (volume/yr × time/unit × % saved) + complexity → 2×2 Savings×Easiness map | 🔥 the €-quantification method |
| gpts_aiConsultant (OneDrive docx) | 3 modules: Understand AI (quiz+badge) / Identify use cases (+ live demo on the user's real data) / Prepare implementation (tool comparison, 5-step plan) | Education layer + the live-demo idea |
| ai usecase- Knowledge illustration.xlsx (OneDrive) | LIBRARY SEEDS EXIST: HR catalog 82 rows (4 levels); Sales scoring Simplicité×Qualité→priority A/B/C; Marketing prompt templates (role+task+{placeholders}) | 🔥 proof the content library exists |
| AI USECASES PROMPTS.txt (OneDrive) | LIBRARY FACTORY: meta-prompt pipeline to generate/check the catalog per function; AI-assistance level 1–5; prompts typed Analyze/Search/Create | 🔥 semi-automatic library production |
| AI course PPTX (OneDrive) | Why/What/How training per function; value×easiness prioritization criteria; REAL PRICING evidence: training 50–350€/user; "Use Cases App" 100–400€ once + 8–10€/mo; ROI 2 months; competitor AIPRM 500€/user/yr | Suite module + willingness-to-pay evidence |
| AIFORALL extension (shipped, Chrome Store v1.1) | Prompt generator for any employee: role/need/question → ready prompt → opens the right AI | Suite module (later) |
| skill-benchmark (_AI_SKILLS) | Evidence-checked competitive benchmark pipeline | V2 engine for the Strategy branch |
| CxO roles JPG | CEO/CFO/COO role KPIs | Low; report framing only |

## 3. THE SUITE INSIGHT

The founder's assets already form an AI4CEO SUITE: **Diagnose** (this tool) → **Prioritize** (the 2×2 map) → **Act** (use-case catalog + prompt library) → **Train** (course) → **Equip** (extension). Differentiation vs the free "AI maturity" questionnaires of big consultancies: here the output plugs into ready-made execution assets. V1 = the diagnostic only.

## 4. THE PROPOSED V1 JOURNEY (founder-corrected; basis for the brainstorm)

1. **FRAME** — describe the company once (sector, size, context) + **choose the diagnosis**: "Strategy", "Operations", or both.
2. **STRATEGY branch** — guided questionnaire: where does AI threaten or help this business model? (The working V0 already does this with 4 market forces — competition, clients, suppliers/ecosystem, regulation — each scored for opportunities and threats, plus a "new business opportunities" section.)
3. **OPERATIONS branch** — (a) SCOPE: tick the functions to examine (sales, HR, finance…); (b) PROCESS REVIEW: correct a pre-filled list of concrete work items with simple scores (the V0 scores each process on 3 value questions — speed, cost, quality — and 3 feasibility questions — how rule-based, data quality, team skills/buy-in).
4. **PRIORITIES** — a 2×2 map (value × ease); € estimate for the top items (volume × time saved method).
5. **DELIVERABLE** — a one-page summary for the CODIR + the full report (Google Doc, versioned).

V2 candidates: mini-questionnaires sent to function heads; free-notes import (AI structures them into the tool); AI-written recommendations (WHY/RISK/TOOL/NEXT/EFFORT); web-researched market evidence for the Strategy branch; re-run at +6/12 months showing progress; live links from each priority to prompts/training/extension; mobile webapp.

Banned (anti-features): project-management/action-tracking drift; vendor commissions; auto-implementation promises; chatbot-consultant.

## 5. OPEN QUESTIONS — the brainstorm agenda (plain language)

**CRITICAL:** The assessment must be CUSTOMIZED and prove REAL VALUE, i.e. NO AI-GENERIC-SLOP.
*Note: "=> Insights" are developer's first reflection per question.*

1. Should V1 be built knowing the suite exists — leaving simple "hooks" so each recommended action can later link to prompts/training — or fully standalone?
    *=> Insights: unclear question. What will the CEO have in V1? If it's just the website, it's USELESS; they must at the VERY MINIMUM have the strategy AI-assessment; really CUSTOMIZED to their company.*
2. Scoring in two passes: quick A/B/C rating on everything, then detailed € estimate only for the top-rated items? 
    *=> Insights: is this for Strategy and/or Operations? What risks of AI-slot-not-customized assessment in the quick rating?* 
3. What unit do we score in Operations: the broad **process** ("recruitment") or the concrete **deliverable** ("a job description")? The catalogs and prompt libraries work per deliverable; spec_1 works per process; the V0 works per process. 
    *=> Insights: rather broad process at CEO level, and detailed deliverable at functional head level; note: assessing the broad process requires to have a look at AI-opportunity per key deliverable.*
4. V1 data entry: pre-filled lists the user corrects. When do we add (a) forms sent to function heads, (b) free-notes import?
    *=> Insights: the more we pre-fill information/answers, the better; CEO do not have time. BUT we must not prefill with generic information.*
5. Keep a live-demonstration step (see §6 "wow moment") in the journey?
    *=> Insights: why not, IF it really proves value. Would it be in the 'Strategy' module or (rather) in the 'Operations' one?*
6. Final outputs: one-pager AND full report?
    *=> Insights: this is for SMBs, therefore a full report must NOT have neither too generic-verbose information nor not-customized ones. It must be easy to read, quickly; the one-pager can be two pages if needed*
7. Execution readiness (can this company deliver: pace of decision, governance, culture, organization, skills, IT). Include in V1, or keep V1 to Strategy + Operations only?
    *=> Insights: 'Execution' is key; must be in v1. BUT the real question is: is it in each module (strategy, operations), only in 'Operations', or a dedicated 3rd module? We may (to be challenged) imagine that it there is an 'IT execution readiness' (available tools, suppliers...) in the Strategy module; then, a customized-questionnaire per assessed function in 'Operations'.*
8. Five scoring systems now exist across the documents (spec_1 criteria; Sales-sheet A/B/C; processor-GPT € savings; course value×easiness; V0's 3-value + 3-feasibility questions). They must become ONE. Which wins, and what exactly are the questions asked?
    *=> Insights: unclear question and options (with pros/cons).*
9. What becomes of the V0 tool: evolve it (its own README says "decouple questionnaire from code" = make questions configurable) or treat it as a learning prototype and rebuild?
    *=> Insights: V0 & Co are only food-for-thoughts*

## 6. TERMS EXPLAINED (so no jargon survives)

- **"Wow moment"**: an optional step during the diagnostic where the tool takes ONE real task of the company (e.g. yesterday's meeting notes) and has AI actually produce the deliverable (the meeting summary) live, in front of the CEO. Purpose: proof instead of promises. Comes from the founder's own GPT design ("customized example" step).
- **"V0"**: the founder's existing "Strat interview" Google-Sheets tool (source in docs/ai4ceo_aistrat_interview_tool_draft.txt) — working prototype, paused because questions are hardcoded.
    *=> Insights: forget the existing V0 if it is irrelevant for the target project.*
- **"Library"**: the expert content (question sets, process/deliverable catalogs per sector, scoring rules, prompt templates) that powers the diagnostic. Seeds exist (xlsx); a semi-automatic production method exists (meta-prompts).

## 7. NEXT STEP (for the fresh session)

Run the brainstorm with the founder question by question (§5), in plain language, one theme at a time. Then: write `ideasup/5-user-story.md` following the ideasup-flow Stage-5 template (persona / problem / value hypothesis / V1 scope + reasons / story table V1-V2-V3); have a FRESH sub-agent audit it against the stage contract; update Progress.md; log any skill rough edges to `_AI_SKILLS/skill-ideasup-flow/skill_plan.md`. Working rules: substantive artifacts are drafted by a sub-agent and audited by a different fresh sub-agent.

**REMINDER:** We are designing the target project; existing material (in `docs' folder) is ONLY food-for-thoughts, NEVER a constraint (can be changed/ignored entirely if not useful).

---
