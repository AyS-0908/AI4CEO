# AI4CEO — User Story × Features (macro draft)

- Date: 2026-07-12 · Status: DRAFT for founder validation — macro view first; the formal `5-user-story.md` (Stage-5 template, sub-agent drafted + audited) follows after validation.
- Inputs: the 10 decisions of the 2026-07-12 brainstorm + the ai4business prototype learnings (`docs/ai4business_retro_spec.md`, `docs/ai4business_db_schema_notes.md`) as food-for-thought.

## 1. The user story (one breath)

**CEO (self-serve):** "As the CEO of a francophone SMB, I describe my company once — the tool has already read my website and pre-filled most of it — I choose a Strategy and/or Operations diagnosis, and in about an hour of guided questions about MY company I get: a scored view of where AI threatens or boosts my business model, a prioritized map of where AI concretely helps my operations with euro estimates, an honest check of whether my company can deliver, and two documents I can put on the table at my next management meeting — all in French, all specific to my company, nothing generic."

**Consultant (same product):** "As a consultant, I run that exact same journey for each of my client companies, all under one account."

## 2. Macro map — User Story step › Features › Key comments

| User story step | Features (V1) | Key comments |
|---|---|---|
| **1. Welcome & company setup** | Account (CEO: 1 company / consultant: N clients) · company form (sector, size, context) · tool reads the company website and pre-fills the profile; user corrects | First "it understood my business" moment (Q4). Dual-mode is one product, not two (locked). |
| **2. Choose the diagnosis** | Pick "Strategy", "Operations", or both | The journey branches here (locked). |
| **3. Strategy branch** | Guided questionnaire on the 4 market forces (competition, clients, suppliers/ecosystem, regulation): opportunities & threats scored impact × time-horizon · "new business opportunities" section | Keeps its own scoring, separate from Operations (Q8). Design inherited from the V0. |
| **4. Operations — quick pass** | Tick the functions to examine · pre-filled process list (library + website tailoring) · per process: 3 mandatory questions (weight / value / ease) + 3 optional (information / team / distinctiveness) → shortlist of 5–8 | Q2, Q3, Q8. CEO can always promote a process into the detailed pass. |
| **5. Operations — detailed pass** | Each shortlisted process opens into 3–5 concrete work items (pre-filled from the catalog, correctable) · per item: euros (volume × time × AI share) + quality flag + 3 ease questions | Euros only exist at work-item level (Q3). **The catalog already exists**: 12 macro-functions → functions → 82 deliverables → 108 tasks, proven in ai4business. |
| **6. Live demonstration** *(optional)* | On 1 shortlisted work item of a curated "safe" type: the tool asks for that task's required inputs, then produces the real deliverable live | Q5. ai4business already solved the mechanics: each task in the catalog knows its 1–5 required inputs, and the prompt-assembly pipeline exists as templates. |
| **7. Execution readiness** | ~10 company-wide questions (decision pace, ownership, culture, skills, organization, IT), asked once, whichever branches ran | Q7. Tempers the "ease" scores and gets its own report section. |
| **8. Priority map** | 2×2 value × ease map · labels quick win / strategic / later · euro figures on top items | Q8. Readiness-adjusted. |
| **9. Deliverables** | Decision sheet (1–2 pages, for the management meeting) + full report built ONLY from the company's own answers and scores · every recommendation stored with department / task / solution type · versioned | Q1, Q6. Strict no-generic rule. French first; architecture ready for more languages (Q10). |
| **10. Consultant mode** | Client list · switch company · same journey per client | Locked decision; no separate consultant product. |

**NEW — one decision to make (from ai4business):** attach a **ready-to-use prompt** to each top recommendation in the report, assembled from the catalog exactly like ai4business's "Promptor" does (role + task + format + the task's required inputs). It needs no AI infrastructure — it is template text assembly, proven in the prototype — and it turns the report from "what to do" into "start today". Recommendation: include in V1; it may be the cheapest wow in the whole product.

## 3. What the ai4business prototype changes (food-for-thought, absorbed)

- **The content library is no longer hypothetical.** Taxonomy (12 macro-functions → functions → 82 deliverables → 108 tasks with required inputs) exists as exportable seed data. This was V1's biggest risk; it is now a head start.
- **The prompt-assembly pipeline is proven** (context → role → task → format → final editable prompt), including quotas ("AI credits") and multi-LLM handoff. Powers the live demo (step 6) and the NEW prompt-per-recommendation idea.
- **A deeper drill exists if ever needed**: process → stages with 10 skill-need scores and unit-cost math. Too heavy for the CEO's hour → V2 candidate (consultant mode first).
- **Pricing evidence**: €199/€249 modules sold via Stripe in the prototype's market — a reference point when V1 pricing comes up.
- **For the future implementation (store, do not design now):** enum/reference tables instead of hardcoded lists · a real i18n dictionary (the FR/UK column-pair pattern worked but hurt) · per-user state separated from shared data · module entitlements per user · a server-side LLM gateway holding the prompt templates · module catalog as data. Logged so the Spec/Plan stages inherit them.

## 4. V2 shortlist (unchanged + enriched)

Function-head mini-questionnaires (first) · free-notes import · prompt/training links live under each recommendation (if the NEW item above stays out of V1) · stage-level drill for consultants · web-researched market evidence in Strategy · +6/12-month re-run with progress view · English · mobile.

## 5. Anti-features (unchanged)

No project-management drift · no vendor commissions · no auto-implementation promises · no chatbot-consultant.

## 6. Idea inventory — the full selection view

Every feature idea found in the sources (`docs/`, prototypes, OneDrive assets), in one table. Status: ✅ placed in V1 (step #) · 🔜 already on the V2 list · 🏛️ suite module (separate product, park it) · ⛔ banned · **⬜ TO DECIDE — placed nowhere yet, founder call needed**. Reco = my stance, one word.

### 6a. ⬜ TO DECIDE (the gaps — 10 calls to make)

| # | Idea (plain words) | Source | Reco |
|---|---|---|---|
| G1 | Inventory of the company's **existing/planned AI projects** during setup — the diagnosis should know what's already tried | V0 §S2 | V1 (1 short step in FRAME) |
| G2 | **Auto-save, resume later, progress bar** — a CEO's hour is always interrupted | V0 mechanics | V1 (requirement, not feature) |
| G3 | Each top recommendation written with 5 fixed fields: **WHY / RISK / TOOL / NEXT / EFFORT** | spec_1 | V1 structure, AI-drafted in V2 |
| G4 | Report **export format**: Google Doc only, or also PDF / Slides for the CODIR? | spec_1, spec_2 | V1 = PDF + Doc; Slides V2 |
| G5 | **AI coherence check** on the whole answer set before the report (flags contradictions, weak spots) | V0 backlog | V2 |
| G6 | **Cross-interview synthesis** (consultant interviews several executives, AI merges) | spec_2 appendix | V2 (consultant mode) |
| G7 | **Monetization mechanics**: packaging, price point, payment, usage quotas ("AI credits") | ai4business F-PL3/F-A4 (€199/249 evidence) | Decide at Spec stage, not now |
| G8 | **In-app feedback** after the diagnostic (4 ratings + "want to talk?") | ai4business F-A2 | V1 (cheap, feeds sales) |
| G9 | **Implementation-prep content** under recommendations: tool comparison + 5-step plan | gpts_aiConsultant | V2 (feeds G3's TOOL/NEXT) |
| G10 | **Configurable questionnaires** (questions as data, not code — the V0's stated death cause) | V0 README, spec_2 registries | V1 architecture note → add to §3 list |

### 6b. Placed ideas (recap — no action needed)

| Status | Ideas |
|---|---|
| ✅ V1 | Website pre-fill (step 1) · dual-mode (1, 10) · branch choice (2) · 4-forces strategy scoring + new-biz opportunities (3) · two-pass Operations scoring (4–5) · € at work-item level (5) · live demo (6) · execution readiness (7) · 2×2 map + labels (8) · decision sheet + versioned no-generic report (9) · **NEW: prompt-per-recommendation (§2, pending founder OK)** |
| 🔜 V2 | Function-head mini-questionnaires · free-notes import · prompt/training links under recommendations · stage-level drill (10-axis) · web-researched market evidence · +6/12-month re-run · English · mobile |
| 🏛️ Suite (park, other products) | Training course module (ai4business M1 + course PPTX) · prompt/GPT directory + multi-LLM launcher (M2 F-P5..P8) · AIFORALL extension · AI-tools store + provider directory (M4, F-R6) · peers community: resources/forum/circles (M5) · AI-tutored skills (M6) |
| ⛔ Banned | PM drift · vendor commissions · auto-implementation promises · chatbot-consultant |

Discipline note: 6a exists to **close** the inventory, not to grow V1 — every "V1" reco above is deliberately small (a step, a field structure, a requirement).