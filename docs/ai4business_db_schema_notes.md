# AI for BUSINESS (aisourcinno.glide.page) — extraction working notes

## 0. Table tree — 41 tables at a glance

Markers: ✅ active in published app · 🔒 auth-only · 🚧 draft module · ❓ orphan. (cols = column count; feature IDs F-xx refer to `ai4business_retro_spec.md` §0.)

```text
DATABASE (41 tables, 1 006 columns, 531 rows used)
│
├─ REFERENCE / ENUMS
│   └─ _datalist (76c, 18r) ✅ ......... column-per-enum store: levels, roles, LLMs, types, countries [F-PL6]
│
├─ USERS & ACCESS
│   ├─ _users- INDIVIDUALS (62c) ✅ .... profile, roles, module entitlements, temp passwords, FR/UK, AI credits [F-PL2..5, F-A6]
│   └─ _users- COMPANIES (29c) ✅ ...... company identity, logo auto/manual, employee whitelist, payer [F-PL2]
│
├─ TAXONOMY (content backbone, C-1)
│   ├─ _structure- MACRO FUNCTION (4c) ✅ ... 12 macro-functions ranked
│   ├─ _structure- FUNCTION (20c) ✅ ........ functions per macro-function + workload/AI-priority rollups
│   └─ _structure- DELIVERABLES (12c) ✅ .... 82 deliverables (activités)
│
├─ APP SHELL
│   └─ HOME (26c) ✅ ................... module catalogue: 6 modules, FR/UK copy, locked flags [F-PL1]
│
├─ M1 AI TRAINING
│   ├─ training 1- HOME (14c) ✅ ....... landing copy + password gate
│   ├─ training 2- COURSE (73c) 🔒 ..... 67 slides: chapters, audio FR/UK, quiz, GPT tutor, practice, breaks [F-T2..T9]
│   └─ training 3- PRACTISING (15c) 🔒 . exercises per macro-function [F-T7]
│
├─ M2 AI PROMPTING
│   ├─ prompting 1- 👉 USC ENTRY (83c) ✅ ... Promptor wizard state machine + prompt assembly [F-P1..P4]
│   ├─ prompting 2- USE CASE (68c) ✅ ....... 108-task catalogue + workload/impact scoring [F-P1, F-D7]
│   ├─ prompting 3- My GPTs (14c) 🔒 ........ user-saved GPT links [F-P9]
│   ├─ 🚧 prompting 3- FORM HISTORY (38c) ... saved prompt runs [F-P10]
│   └─ 🚧 prompting 4- GPT CHAT (18c) ....... multi-turn chat sessions [F-P11]
│
├─ M3 AI DIAGNOSIS
│   ├─ usecase 1- PROCESS (27c) ✅ ..... processes + AI synthesis (gain €, priority) [F-D1, F-D6]
│   ├─ usecase 2- STAGE (34c) 🔒 ....... stages: levels, volume/cost, 10-axis AI potential, AI result [F-D2..D5]
│   ├─ 🚧 B1_usecaseAI- FORM (40c) ..... AI-theory per deliverable + workload math [F-D7]
│   └─ 🚧 B2_usecaseAI- USC DATA (14c) . per-user 6-col scratch grid → prompt model [F-D7]
│
├─ M4 AI STORE 🚧
│   ├─ 🚧 C1_libraryAi- USC SEARCH (31c) ... search screen: filters + AI search [F-S2]
│   ├─ 🚧 C2_libraryAi- GLOBAL LIST (52c) .. tools directory + ratings→stars + 💲provider fields [F-S1, F-S4, F-S5]
│   ├─ 🚧 C3_libraryAi- MY LIST (10c) ...... user×tool join [F-S3]
│   └─ 🚧 C4_libraryAi- CATEGORY (6c) ...... tool categories
│
├─ M5 AI RESOURCES / PEERS
│   ├─ kmPeers 1- HOME (16c) 🔒 ........ screen state + menus
│   ├─ kmPeers 2- RESOURCES (28c) 🔒 ... shared resources + ratings [F-R1, F-R2]
│   ├─ kmPeers 3- FORUM (37c) 🔒 ....... posts, answers, filters, claps [F-R3]
│   ├─ kmPeers 4- CIRCLES (11c) 🔒 ..... private circles [F-R4]
│   ├─ 🚧 km 2- BEST PRACTICES (11c) ... best-practice cards [F-R5]
│   ├─ 🚧 km 3- PROVIDERS (29c) ........ provider directory + 6-axis assessment [F-R6]
│   ├─ 🚧 peers X - CHAT (7c) .......... simple chat feed [F-R7]
│   └─ 🚧 A4-office- USUAL TOOLS (7c) .. user's usual tools [F-R8]
│
├─ M6 my SKILLS 🚧
│   ├─ 🚧 D1_skillAi- SKILLS (45c) ..... skill + AI core lesson + prefs [F-K1, F-K2, F-K4]
│   └─ 🚧 D2_skillAi- SOURCES (29c) .... sources → what's-new → updated lesson, api/call [F-K3]
│
├─ ADMIN & SUPPORT
│   ├─ _admin- MENU (5c) ✅ ............ Plus-menu items + per-user visibility
│   ├─ _admin- LEGAL TERMS (5c) ✅ ..... consent texts [F-A3]
│   ├─ _admin- PRICING (7c) ✅ ......... Starter/Master + Stripe [F-A4]
│   ├─ _admin- ROADMAP (6c) ✅ ......... roadmap cards [F-A5]
│   ├─ _admin- FEEDBACK (16c) ✅ ....... per-prototype ratings [F-A2]
│   └─ 🚧 _admin- PROMPT ENGINEERING (9c) .. prompt-technique knowledge base
│
└─ ❓ ORPHANS
    ├─ ❓ _structure- output category (6c) ... output-need enum
    └─ ❓ _aistack pricing (7c) .............. AI-stack offer pricing
```

---

App ID: 4P7hyxb4SawKuAEkyr2d — Glide "Pages" app, PWA, FR/UK bilingual.
Meta description: "Démocratiser l'IA pour les PME-ETI". Theme #F6F6F6. 531 rows used.
Data endpoint: POST /api/container/playerFunctionCritical/getAppSnapshot → {appID, schema.tables[41], dataSnapshot: signed GCS .jzon URL, numRowsUsedInApp: 531}

## Naming conventions observed (Glide builder discipline)
- Sheet prefix = module: `_datalist` (global enums), `_users-`, `_admin-`, `_structure-` (taxonomy), then per-module screens: `training N-`, `prompting N-`, `usecase N-`, `kmPeers N-`; 🚧 = work-in-progress modules; ❓ = orphan/question tables.
- Column prefix `group/` = functional grouping inside a table (bckoff = backoffice, idcard, access, interact...).
- Suffix `_txt/_nb/_img/_url/_date/_boolean/_Rtxt (rich text/markdown)/_emoji`.
- Computed column markers: (R) relation find-row, (Rx)/(SP)+(R) multi-relation filter-rows, (LK) lookup `with`, (JL) join-strings, (TP) template, (IF) if-then-else, (SP) split-string, (RU) rollup reduce / reduce-to-member-by, (SV) single value get-nth / get-nth-last, (M) math assign-variables, (Q) query filter-sort-limit, (USC) user-specific column, (XLS)/(JS) yes-code (custom JS), (MA) make-array, (UPPER)/(RMV)/(TRUNCATE) yes-code text utils, plugin-computation (device type), generate-image (auto avatar/logo).
- FR-UK i18n pattern: pairs of `FR x` / `UK x` columns + `(IF) x` switch on user language.
- Access control pattern: per-module temp passwords (tempPwd/ (TP|SV|IF|USC)), `access/ role _nb` → datalist label, `access/ byAyS- authorized modules _txt` → (SP) → (R) filter HOME rows = authorized prototypes; AI credits quota (access/ by AyS- AI credits, maxRequest/ # request counters).

## Nav (published app): Home | FORMATION | PROMPT | CAS D'USAGE | ✉ (contact)
URLs: /dl/home, /dl/formation, /dl/... (deep links)

## 41 tables (sheet → cols; r = seeded rows visible in public snapshot)
Active:
1. _datalist (76c, 18r) — universal enum/reference table: one row per enum value set? Actually 18 rows × 76 columns, each column = an enum list (level/, user/, social/, company/, gpts/, prompt/, resources/, forum/, usecase/, gtm/, skill/, admin/, country/ groups). Row = index position.
2. _users- INDIVIDUALS (62c) — user profile, access rights, temp passwords per module, idcard/, business/ (company rel, macro-function+function rel), myPeers proximity, FR-UK selected language + translated UI labels, admin share link.
3. _users- COMPANIES (29c) — company identity, logo (manual/Clearbit/auto IF), size, authorized employee emails (SP→array), payer/ Stripe offering info.
4. _admin- MENU (5c) — app menu items + per-user visibility choice (USC).
5. _admin- LEGAL TERMS (5c) — legal text + per-user agreement boolean (USC).
6. _admin- PRICING (7c) — price id/title/amount/stripe link/(TP) note.
7. _admin- ROADMAP (6c) — roadmap items (title/type/details/picture).
8. _admin- FEEDBACK (16c) — user feedback: prototype ref → HOME, desc, ratings (understanding/ux/relevance/would recommend), contact opt-in.
9. _structure- MACRO FUNCTION (4c) — id, rank, title. Company function taxonomy L1.
10. _structure- FUNCTION (20c) — id, title, id macro-function (R), rollups: workload counts, AI-priority counts, highest function labels. Taxonomy L2.
11. _structure- DELIVERABLES (12c) — id, title, id macro-function, id function, desc, per-user home menu (USC), fake-relation trick to USC ENTRY. Taxonomy L3.
12. HOME (26c) — one row per module/prototype tile: ideasup/ module nb, title, FR/UK label+valueProp+description (IF switch), picture, locked boolean; generalities IF titles for home screen; background img, video, useCases ex markdown.
13. training 1- HOME (14c) — training landing: temp pwd entry (USC), IF titles/subtitles/testimonies/value added/takes away/warning, (JS) testimony.
14. training 2- COURSE (73c) — course player: chapter #/FR/UK title, end-chapter flag, per-user display chapter (USC); slide # + FR/UK titles, free-access flag, length + total rollup; content thumbnails/slides img, FR/UK takesAway, FR/UK audio, video, FR/UK instruction; practice (is advanced, FR/UK title, per-user macro-function select → relation to PRACTISING, lookups instructions+data table); breaks (is break, prompt, link); quizz (is quizz, FR/UK lessons learnt, 3× FR/UK questions + answers, per-user display answer); gptTutor (show/hide USC, TP prompt, user question USC, AI response USC); navigate (self relation for lessons, chapter+1 math+relation, password SV).
15. training 3- PRACTISING (15c) — exercises per macro-function: id + (R) + labels, FR/UK question, data table markdown, per-user showHide, (SV) prompt template from USC ENTRY, per-user user prompt.
16. prompting 1- 👉 USC ENTRY (83c) — THE prompt generator wizard (single-row screen table): module ref → HOME; intro (USC ai output type→datalist, request type→datalist, save request bool, request title); airole (USC macro-function + function → structure rels, sector→datalist, TP/IF assembly of AI role); format (USC display format, language, style→datalist, structure, length→datalist); promptGeneric (TP template + USC editable + copyTo); promptUseCase (USC id deliverable + id task → rels to USE CASE, lookups user required inputs, TP FINAL auto prompt, API/FileAnalysis variants 🚧); promptFindCase (user sector+function); promptDirect (TP prompt for Text/Code, IF FINAL); promptCreate (user entry → TP prompt); aiAnswer (USC corrected prompt, ai launched nb, ai answer text/picture + IFs); maxRequest (# requests counter + TP label); gptsStore (user keyword, show-hide, TP gptS result); interact (menuPrompts nb, menuMethod show-hide, history show-hide + isEven JS, hide ai answer + isEven JS).
17. prompting 2- USE CASE (68c) — use-case catalog rows (task level): bckoff ids+rels (macro-function, function → structure, deliverable → DELIVERABLES, SV to USC ENTRY), title task, prompt/ level biz impact + impact multiplicator (M), type, user needed inputs 1-5 + TP; AsstStep1/2 per-user view selections (macro-function/function rels), per-user workload inputs (mn to method/analyse/text/mmdia, yearly occurrences) → (M) deliverable workload/AI impact/% + TP label; wrkld/AIpty rollup chains (function highest, deliverable highest via reduce-to-member-by + JL); testAI (USC prompt general, type of ai test, ai launched, ai answer + IF); aiStore (SV → C1 USC SEARCH, TP prompt); export (csv file link USC, TP prompt for csv, result); interact (home menu, see guide + even JS, synthesis submenu).
18. prompting 3- My GPTs (14c) — user's GPT links: id user, timestamp, SV temp password, id macro category → datalist + label, title, description, url, public visibility bool, generated picture, kanban rank.
19. usecase 1- PROCESS (27c) — process diagnostic: temp pwd entry USC, bckoff ids (user, macroFunction, function → rels + UPPER labels), process title/desc/yearly occurrences/comments, ai/ (R) ID process → STAGE rows, (LK+JL) combined AI results per stage, TP prompt synthesis, ai result, priority; Is Favorited (USC).
20. usecase 2- STAGE (34c) — stages of a process: bckoff ids + (R) process, stage # + title + UPPER + TP, description; desc/ tools, level automation/outsourced/centralized, comments; wkld/ type unit, units volume, unit cost, (M) current total unit cost; skill/ 10 level columns (method, concept, data search, data analysis, writing, synthesis, ppt, image, audio, video); ai/ TP prompt + result.
21. kmPeers 1- HOME (16c) — km/peers landing: module ref → HOME, rank/title, TP user email, USC menus (top, macro function, function), resources id subtype USC, peers select proximity USC + (R) circles.
22. kmPeers 2- RESOURCES (28c) — shared resources: bckoff user rel/email/date/archive, category (type→datalist, subtype→datalist + emoji + TP), macro function + function ids, resource title/author/desc/weblink/video/picture, price id→datalist, rates (USC user rate + TP price+sum).
23. kmPeers 3- FORUM (37c) — forum messages: user rel + lookups (name, email, company+title+function, picture), timestamp, archive; origin (macro function rel, type msg→datalist, type topic→datalist, TP combos, title, msgOrigin markdown, attachment, video/audio/website links); answer (source id, msgAnswer); display USC filters (show-hide, id expertise, id type post, id type request, IF display forum NoSelect); kpi claps (USC clap, count, TP).
24. kmPeers 4- CIRCLES (11c) — peer circles: id, users, timestamp, title, description, keywords, generated picture, emails → SP → (R) INDIVIDUALS.

🚧 Draft modules (built but not in published nav):
25. 🚧 prompting 3- FORM HISTORY (38c) — saved prompt requests (form snapshot: aiUseCase in-function/in-sector/AI-type + TP request/prompt + aiResult; intro/aiRole/structure fields incl. headers A-E; ai final prompt + answer + picture; interact menus; ⚡(SV) > GPT CHAT; (Q) max credit filter-sort-limit).
26. 🚧 prompting 4- GPT CHAT (18c) — chat messages: session ID, timestamp, Role, Content, aichat response, IF response-or-loading; (R) session → FORM HISTORY + lookups (language, first ai answer); self-relation on session + (RU) count; TP 1st/other prompts for chat + IF.
27. 🚧 B1_usecaseAI- FORM (40c) — AI use-case theory form: deliverable rel → USE CASE, user, macro-function/function rels; AI theory impact + multiplicator + description + limitations + standard prompt; AsstStep2 workload inputs + math; wrkld rollups; testAI (see prompt or tool, final prompt, ai launched, ai answer + IF); toolAI (SV → C1, TP prompt).
28. 🚧 B2_usecaseAI- USC DATA (14c) — per-user scratch data grid (3 txt cols, 3 nb cols, all USC) + TP prompt model + USC editable/AI result.
29. 🚧 C1_libraryAi- USC SEARCH (31c) — AI tool library search screen: module ref → HOME; userEntry USC (macro-function, function, category, keyword, rank, see more + even JS); filter (SP id function/category, IF display, RMV/UPPER/SP keyword yes-code); searchByAi (user entry, TP automatic prompt, ai launched, ai answer, SP answer → (R) GLOBAL LIST); maxRequests TP labels; userTempData (# requests USC, in my list USC); interact topMenu search type.
30. 🚧 C2_libraryAi- GLOBAL LIST (52c) — AI tools directory: ids, publish bool, SV rels; desc (name, url, title, description, keyword, kwd aggregator + SP, pricing, funding, mother company); structure (id category SP→(R) C4, LK labels, id macro function SP→(R)); mmdia (logos clearbit/manual/Glide-generated + IF, cover, iFrame bool); forSearch IF display + (R)s to C1; userList (Q) → C3 + IF MyList; rating (ays comment/rating, USC rate, sum, # votes, (M) average, XLS formatting → (R) datalist → star emoji lookup, TP label); prov 💲 fields (logo BW, prezVideo, trainingVideo, embeddedSite, rank).
31. 🚧 C3_libraryAi- MY LIST (10c) — user's saved tools: id user, id tool → (R) GLOBAL LIST + lookups (title/url/description/logo/category).
32. 🚧 C4_libraryAi- CATEGORY (6c) — tool categories: id, emoji, title, description, rank.
33. 🚧 A4-office- USUAL TOOLS (7c) — user's usual office tools: id, user, rank, title, website, logo.
34. 🚧 peers X - CHAT (7c) — simple chat: timestamp, comments, user name/picture/email.
35. 🚧 km 2- BEST PRACTICES (11c) — best practices: user, date, id method/step, title, description, keywords, source, archive.
36. 🚧 km 3- PROVIDERS (29c) — provider directory: company, type, area, function; offer website/video/special offer/hasContract/page webview; assess USC scores (scope, simplicity, support, integration, price, quality) + increments + nb votes; logo; AI Office video.
37. 🚧 _admin- PROMPT ENGINEERING (9c) — prompt technique knowledge base: user need, prio, technique, description, guideline, example uses, prompt example.
38. 🚧 D1_skillAi- SKILLS (45c) — AI-tutored skill learning: screen titles; user rel; scope (field skill → datalist, sub-field); obj (title, level knowledge → datalist, concrete achievements, auto/manual picture + IF); privacy (notification frequency/channel → datalist, public visibility); prompt (language/style/length → datalist + TP initial skill prompt); ai (initial core lesson, IF wait-or-lesson, (Rx) sources, (LKx) updated lessons, (SVx) last updated, IF display); user notes.
39. 🚧 D2_skillAi- SOURCES (29c) — skill update sources: ids (source, skill, user), timestamp; source (type → datalist, title, www, IF display title, new information + TRUNCATE + hide bool + IF); skill rel + lookups (title, achievements, core lesson, language, style); prompt (length → datalist, TP prompt1 summary, TP ⚡prompt2 new core lesson); ai (what's new, updated core lesson); api/ call (yes-code) ← API CALL COLUMN.
40. ❓_structure- output category (6c) — id need, emoji, title, category output, rank.
41. ❓ _aistack pricing (7c) — id offering, title, description, price, currency, frequency.

## Home screen content (captured)
- Hero: illustration left; right: "IA.CCÉLÉREZ VOTRE ENTREPRISE"; quote "3/4 des TPE/PME/ETI s'interrogent sur les cas d'usage et gains concrets de l'IA" (BPI); 3 steps COMPRENDRE/EXPÉRIMENTER/APPLIQUER.
- "PROPOSITION DE VALEUR" purple section.
- YouTube embed: "FORMATION À L'INTELLIGENCE ARTIFICIELLE POUR DIRIGEANTS & MANAGERS" (copyright Aymard de Scorbiac 2024).
- Section "QUELS CAS D'USAGE POUR MOI ?" — DÉBUTANT: chatbot use (example links Prospection/Recrutement)...
- Purple CTA button "OBJECTIF : MAÎTRISER L'IA NIVEAU 1 📚" → formation.
- "ILS NOUS FONT CONFIANCE" — 3 testimonial speech bubbles (DRH d'ETI, Dirigeant de PME, Directeur Marketing de PME).
- Footer band: DURÉE: 1 journée 5/8 participants (présentiel/distance ~2-3h; exercices ~2-3h; conseil ~2-3h; bientôt autonome en ligne); PRESTATION -20% PME <20 pers; CONTACT contact@sourcinno.com "c'est un humain qui répond, pas une IA !"; button "CURRICULUM DE LA FORMATION IA 📊"; footer icons share/mail; "Propriété exclusive de Sourcinno - sourcinno.com - 2024".
- Modal on load: "This team has reached its row limit" (Glide quota) with Continue.

## FORMATION screen (/dl/formation)
- Hero banner img + title "Comprendre les enjeux, la pratique et la mise en oeuvre".
- "À la fin de cette formation VOUS MAÎTRISEREZ" — 3 columns: POURQUOI-Enjeux (Vitesse d'évolution, Champ d'application, Société) / QUOI-Cas d'Usages (Ce que c'est et n'est pas, Termes clés, "Prompter" VOTRE cas d'usage) / COMMENT-Déploiement (Plan d'action niveau 1, Anticipation niveau 2, Points d'attention). NB: "IA" = LLM.
- Purple section "PARCOURS de 3h" (mode autonome: 1.30h de cours, hors exercices) + notes card (FR/EN audio, slides EN, GPT+/Copilot Pro recommandé).
- "À EMPORTER": Compréhension Théorique et Pratique, Modèle de Prompt Simple/Avancé, Plan d'action niveau 1, Personnalisation de VOS GPTs, Accès à des GPTs clés (voir onglet "ia.PROMPT").
- Footer identical.

## Design tokens (observed)
- Dark navy/indigo background #1b1333-ish (hero #201743 approx), purple accent #6C5CE7/#7C5CFF family, white cards, light gray body bg (#F6F6F6 theme), Inter font (+ Roboto/Roboto Mono loaded), rounded-xl cards, top nav pill highlight, "Made with Glide" badge.
- Icons: Glide stroke SVG set (st-house, st-desktop, st-gague, st-mail, st-share, st-chevron-right).