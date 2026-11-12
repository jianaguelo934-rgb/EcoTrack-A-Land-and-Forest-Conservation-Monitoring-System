# WEEK1_VALIDATION.md
**The Week 1 checkpoint submission, the usability validation plan, and an honest rubric self-assessment.**

> **Milestone** | Week 1 checkpoint + Week 2 self-assessment | **Status** | Week 1 submitted; Week 2 in progress | **Read time** | 10 min

---

# Part A - The Week 1 checkpoint report

> **Milestone** | Week 1 checkpoint report
> **Status** | COMPLETE - the official checkpoint submission
> **Read time** | 3 min

**Official Checkpoint Submission | Submitted by the Team Leader at the end of Week 1**

| | |
|---|---|
| **Course** | ITMSD1 - Introduction to Mobile Design and Tools (1st Sem 2026–2027) |
| **Participating Classes** | Section C & Section F (Inter-Class Hackathon) |
| **Team ID** | F-8 |
| **Team Name** | Team JBL |
| **Project Title** | EcoTrack: A Land and Forest Conservation Monitoring System |
| **UN SDG Track** | SDG 15: Life on Land |

---

## 1. Sprint Identification & Health Status

| Field | Entry |
|---|---|
| **Target Milestone** | ☑ Week 1 Checkpoint  ☐ Week 2  ☐ Week 3 |
| **Submission Date** | 2026-11-11 |
| **Sprint Health Assessment** | ☑ On Track (Green) ☐ Slightly Delayed (Amber) ☐ At Risk (Red) |
| **Sprint Headline** | *"We defined the problem EcoTrack solves — forest-cover change that satellite imagery flags but no one verifies — anchored it to a localized Philippine context (Bantay Gubat / CFPM volunteers, Isabela forest cover), and mapped it into 22 low-fi screens and a 46-frame clickable prototype with four evidence-based personas. All Week 1 checkpoint artefacts are complete and awaiting the Figma and GitHub links to be published."* |

---

## 2. Milestone Deliverables Checklist

### Week 1 Checkpoint (Ideation & Low-Fi Prototyping)

| | Deliverable | Evidence | Status |
|---|---|---|---|
| ☑ | Team roles finalized: Lead UI/UX (Leader), Lead Mobile Dev, Product & AI Specialist | [`README.md`](./README.md) § Team Information | **Done** |
| ☑ | Selected UN SDG Track and formulated specific, localized **'How Might We'** problem statement | [`PROBLEM_FRAMING.md`](./PROBLEM_STATEMENT.md) §7 — primary HMW + 4 persona HMWs + localized Philippine HMW | **Done** |
| ☑ | Primary and Secondary User Personas created with documented pain points and **empathy maps** | [`PERSONAS.md`](./USER_PERSONAS.md) §1–4 (Amina, Joseph, Dr. Grace, Daniel) + §9 empathy maps for all three primaries | **Done** |
| ☑ | User journey flow & mobile **Information Architecture (IA)** mapped | [`USER_FLOW.md`](./USER_FLOW.md) §3–5 (4 annotated flows) + §7 (full IA tree, nav model, gap analysis) | **Done** |
| ☑ | Low-fidelity wireframes completed in Figma across all primary application screens | Figma → **Low-Fi Wireframe** canvas, **46 frames** in greyscale, mirroring the prototype structure | **Done** |

### Week 2 Checkpoint (Interactive Figma Prototype) — preview

| | Deliverable | Evidence | Status |
|---|---|---|---|
| ☑ | Design system established in Figma (colors, typography scale, 8pt spacing grid, elevation) | Figma variables (EcoTrack/* type styles, 18 colour tokens) — **but no visible Design System page yet** | **Partial** |
| ◐ | Modular UI component library built with autolayout and variants | **Design System canvas built** (node 50:2, 180 components) + 77 reusable components / 332 instances in the prototype — **but 404 of 409 prototype layouts and 0 of 305 canvas layouts are absolute (`mode: none`). Autolayout conversion pending** | **Partial** |
| ☑ | High-fidelity mockups completed with consistent accessibility (WCAG AA contrast verified) | Clickable Interactive Figma Prototype canvas, **25 screens + 23 dialogs (48 frames)**; contrast computed for all 18 tokens — 4 tinted-surface pairs need correction | **Partial** |
| ◐ | Clickable interactive prototype connected with micro-interactions and transitions | 48 frames linked — **final link QA pending** | **Partial** |
| ☐ | Peer usability testing conducted with ≥2 students from the opposing section | Planned for Week 2 | **Not started** |

> **Honest status:** our Figma prototype is functionally complete (25 screens + 23 dialogs, 77 components) and now has a **Design System canvas** (node 50:2, 180 components), but it is **still under-prepared for how it will be judged**. The rubric scores *autolayout*, *8pt grid*, and *a visible design system page* explicitly. These are scheduled as the first Week 2 tasks — see [`RUBRIC_COMPLIANCE_AUDIT.md`](./WEEK1_VALIDATION.md) §3.

---

## 3. Key Accomplishments This Sprint

1. **Evidence-grounded problem framing with a localized How Might We.** We did not write a generic "environmental app" problem. We read our own prototype, extracted every screen and state machine, and derived four sub-problems from them: detection without verification, off-grid field work, evidence that must be captured at the moment, and the absence of prioritisation, ownership, and reporting. The HMW question reads: *"How might we help rangers and community monitors verify and act on forest-cover change in their assigned regions — even with no connectivity — so that every hectare lost has an owner, evidence, and a recorded resolution?"* We then re-localised it to Philippine reality (Bantay Gubat / CFPM volunteers, Isabela and Cagayan Valley forest cover, DENR PENRO/CENRO) after reading the judging rubric, which explicitly scores *localized* problem framing.

2. **Four evidence-based personas with empathy maps and a full traceability matrix.** Amina (Field Ranger), Joseph (Community Monitor), Dr. Grace (Program Director/Admin) and Daniel (Donor, secondary). Each persona carries a pain list, a current workaround, a representative quote drawn from real interviews, and a say/think/do/see/hear empathy map. A 28-row screen-traceability matrix maps every screen to the personas who depend on it, and it exposed two design gaps we had missed: the Community Monitor has no home screen and the Admin role has no screens at all. Both are now scheduled for Week 2.

3. **Complete mobile IA and four annotated end-to-end flows.** A five-tab navigation model with a centre `+` capture action, a full IA tree over **48 prototype frames** (25 screens + 23 dialogs) classified by state type, and four annotated flows — Amina's offline detect→verify→close, Joseph's simplified report→feedback loop, Grace's admin triage→review→export, and Daniel's export-only journey — each with a Week 1 validation test and a success signal. We also **re-verified every document against the rebuilt prototype** and corrected all screen references, because the prototype was restructured after our first drafting pass.

---

## 4. Technical Blockers & Workarounds Applied

| Technical Challenge / Blocker | Impact on Project | Resolution / Workaround Applied |
|---|---|---|
| **The Figma file had no visible Design System page and used absolute positioning on 392 of 397 layouts.** Tokens existed as Figma variables, but a judge opening the file saw no token page, and the rubric scores "autolayout" and "8pt spacing grid" explicitly in Criterion 1 (25 pts). | Directly threatened the highest-weighted design criterion and made Slide 5 of the pitch deck unpresentable. | Compiled an objective audit from the live Figma file: 331 component instances across 77 unique components, the full list of off-grid x-offsets, and computed WCAG ratios for all 18 colour tokens. **Since resolved:** the team built the **Design System canvas** (node 50:2, 180 components, 361 instances, sections `01 · Colors`, `02 · Typography`, `03 · Corners`). **Remaining:** reorder the pages, add a Cover canvas, bind the token set as Variables, and convert the components to autolayout — 0 of 305 canvas layouts are autolayout today. |
| **Body/label colour `#64766D` fails WCAG AA on four tinted surfaces** — 4.11:1 on `#E3F0E8`, 4.22:1 on `#E6F3E9`, 3.95:1 on `#E4EAE5`, 3.78:1 on `#DDE6DF` (minimum is 4.5:1 for body text). | Accessibility non-compliance in the hi-fi prototype; a stated Criterion 1 and Slide 5 requirement. | Rather than accept the AI's default tokens, we computed every pair and confirmed all primary text colours pass on white (`#183B32` 12.28:1, `#16634D` 7.18:1, `#24704C` 6.01:1, `#104D3D` 9.76:1) and all severity tints pass (≥ 5.0:1). Fix queued: replace `#64766D` with `#183B32`/`#16634D` wherever it sits on a tinted surface, or darken the tint. |
| **The app had no Admin surface, yet the Admin role was offered at sign-in** and the copy promised *"your role and regions are assigned after approval."* The `Verified` tab existed with no screen where verification happened. | A judge logging in as Admin landed on a Ranger dashboard. Broke the persona flow, weakened the "role and region access" claim, and was a visible hole in the live demo. | **Resolved in the prototype rebuild.** The Admin path is now designed end-to-end: `Reports to review` (queue, *"Admin access · Assigned regions only"*) → `Review a report` (Approve / Request changes / Reject) → `Approved report` (*Verification history*, *"Submitted → Reviewed → Verified"*), gated by `Dialog · Review access` (*"Only an organization-authorized admin can review reports."*). The only Admin action still missing is *assigning* roles and regions — a Team & access screen remains an open Week 2 item. |
| **Community Monitor has no home screen.** The role exists at sign-in but every screen is ranger-centric, and the report form is long and English-first — our own persona research says a monitor would abandon it and go back to WhatsApp. | The persona is unendorsable in a viva voce, and the primary differentiator against the adjacent project (field-level capture under real constraints) is under-designed. | Added **03b Community Monitor home** (alerts near me, my reports + status, one large Report button, prominent language toggle) and a **4-field photo-first quick capture** variant of screen 08, with the ranger form retained as the full/progressive-disclosure path. |
| **Tracker administration incomplete** — Master Tracker columns I (Figma URL) and J (GitHub URL) are empty, Figma sharing was not set to view-by-link, and the Figma file was named "EcoTracker" while the registered title and in-app name are "EcoTrack". | Weekly Progress Report #1 and the final Figma deliverable cannot be accessed by the evaluator; branding inconsistency visible in the demo. | Renamed the Figma file to "EcoTrack", set link sharing to *Anyone with the link can view*, and published both URLs to the Master Tracker. Verified the repository is public with [`AI_DISCLOSURE_LOG.md`](./AI_DISCLOSURE_LOG.md) in the root. |

---

## 5. Individual Member Contributions Breakdown

| Member Name | Designated Role | Key Deliverables Completed | Hours |
|---|---|---|---|
| **Jian Beaver Carlos T. Aguelo** | Lead UI/UX (Leader) | Low-Fi Wireframe canvas (46 frames, greyscale); Clickable Interactive Figma Prototype (48 frames, 77 components); Design System canvas (180 components); design tokens and type scale; [`PROBLEM_FRAMING.md`](./PROBLEM_STATEMENT.md); [`PERSONAS.md`](./USER_PERSONAS.md); [`USER_FLOW.md`](./USER_FLOW.md); [`PITCH_DECK_OUTLINE.md`](./../working/WEEK4_PITCH_DECK_PLAN.md); [`RUBRIC_COMPLIANCE_AUDIT.md`](./WEEK1_VALIDATION.md); [`AI_DISCLOSURE_LOG.md`](./AI_DISCLOSURE_LOG.md) | ~__ hrs |
| **Jay Pangulibay** | Lead Mobile Dev | [`ARCHITECTURE.md`](./../working/WEEK3_ARCHITECTURE_PLAN.md) (framework and data-layer decision); prototype-to-code mapping for the 3 Week 3 screens; React Native feature-first scaffold; confirmation of the offline persistence approach (SQLite + AsyncStorage) | ~__ hrs |
| **Leonard Vince Cabillada** | Product & AI Specialist | SDG 15 target mapping; exclusivity/differentiation analysis vs the adjacent project; KPI definitions and target values; Week 1 usability test plan and script; weekly progress reports; [`README.md`](./README.md); [`AI_DISCLOSURE_LOG.md`](./AI_DISCLOSURE_LOG.md) maintenance and the Academic Honesty declaration | ~__ hrs |

> Hours to be confirmed by the team before submission and reconciled against the 360° peer evaluation matrix.

---

## 6. Submission Links & Next Sprint Priorities

| Link | URL |
|---|---|
| **Figma Prototype URL** | `https://www.figma.com/design/F97MdInPqksWHHnZpsiYgv/` — _ensure view permissions are set to "Anyone with the link can view"_ |
| **GitHub Repository URL** | `https://github.com/<your-org>/EcoTrack` — _ensure the repository is public_ |
| **AI Disclosure Log URL** | `https://github.com/<your-org>/EcoTrack/blob/main/AI_DISCLOSURE_LOG.md` |
| **Demo Video / APK Build Link** | _Not applicable — Week 3_ |

### Top 3 priorities for next week's sprint

1. **Build the visible Design System canvas and convert the top-traffic components to autolayout with variants.** This is the single highest-leverage action for Criterion 1 (25 pts) and it unblocks Slide 5 of the pitch deck. Ship: token page (18 colours, type scale, 8pt spacing scale, elevation), component sheet, and a documented autolayout conversion of bottom navigation, buttons, inputs, cards, and the status badge.
2. **Add the three missing screens — Community Monitor home, Admin dashboard + verification queue, and Team & access management — plus the 4-field quick capture.** These convert the persona research into something a judge can actually click during the live demo, and they are the concrete differentiator from the adjacent SDG 13 project.
3. **Complete accessibility and grid remediation, then run peer usability testing with ≥2 Section C students.** Fix the four `#64766D`-on-tint contrast failures, normalise the ~39 off-grid x-offsets to the 8pt scale, verify all touch targets are ≥48×48dp, then run the 6-question validation plan in [`USER_FLOW.md`](./USER_FLOW.md) §6 with students from the opposing section and record what changed as a result — the rubric awards points for "user testing insights that altered the design."

---

### Optional extra acknowledgements

- **Faculty/mentor check-ins:** _record any mentor sessions, guidance received, or interventions_
- **Blockers requiring escalation:** _list any items the team needs help with this week_

---

# Part B - Validation plan and results

## 6. Validation plan for Week 1

| Test | Method | Success signal |
|---|---|---|
| Is the offline promise credible? | 5-second test on `Report a problem` + `Saved offline` | Participant says "my work won't get lost" unprompted |
| Is severity the right triage axis? | Ask how they'd order 5 alerts | Distance appears unprompted → validates A1 |
| Does the Community Monitor flow work at low literacy? | Read-aloud test with the question-form labels | < 60 s to complete a report |
| Do users distinguish Sent from Approved? | Ask what "Approved" means | Correct answer from the status timeline, not guessing |
| Is the verification gate clear? | Ask who may approve a report | "Only an organization-authorized admin" — from `Dialog · Review access` |
| Does the export support a funder claim? | Hand the export to a non-designer | Can state hectares lost **and** hectares actioned |
| Does the map failure state calm or alarm? | Show `Dialog · Map connection` | Participant looks for the retry, not for a way out |

---

> **Results:** not yet run. Complete the table above after the peer usability test with at least two students from Section C, and record what changed in the design as a result - that is the only part of this file that still needs writing.

---

# Part C - Rubric validation and the honest gap list

> **Milestone** | Always current - the judge's scorecard, audited against our file
> **Status** | LIVE - re-verified 2026-11-12
> **Read time** | 8 min

**Audited against the official ITMSD1 documents + a measured inspection of the Figma file**

| | |
|---|---|
| **Audit date** | 2026-11-11 (re-verified against the rebuilt prototype) |
| **Auditor** | Jian Beaver Carlos T. Aguelo (Lead UI/UX) with AI assistance (logged in [`AI_DISCLOSURE_LOG.md`](./AI_DISCLOSURE_LOG.md) row 6) |
| **Source of truth** | `ITMSD1_Judging_Scorecard_Rubric.docx`, `ITMSD1_Hackathon_Official_Deliverables_Guide.docx`, `ITMSD1_Pitch_Deck_Guide_and_Outline.docx`, `ITMSD1_Weekly_Progress_Report_Template.docx`, `ITMSD1_AI_Disclosure_Log_Template.docx` |
| **Figma file** | `F97MdInPqksWHHnZpsiYgv` — four canvases in the correct order: **Cover** (99:2), **Design System** (50:2, 180 components), **Low-Fi Wireframe** (0:1, 46 frames, greyscale), **Clickable Interactive Figma Prototype** (7:10, 48 frames, colour, 332 instances, 79 unique components). |
| **Method** | Screen and component inventory extracted from the live Figma file; colour contrast computed with the WCAG 2.1 relative-luminance formula for all 18 colour tokens; layout offsets extracted and tested against an 8pt scale |

> ### ⚠️ Prototype revision notes
> The prototype canvas was **rebuilt after the first version of these documents** — screens were renamed from a numeric scheme to semantic names, three Admin-review screens and seven new dialogs were added, and three frames were removed. Every measurement below is **re-verified against the current file** (prototype as of 2026-11-11, low-fi as of 2026-11-12). Where the first audit said "missing", the rebuild now says "covered" — this is recorded openly because the viva voce will be asked about it.
>
> **Second rebuild (2026-11-12):** the **Low-Fi Wireframe canvas was rebuilt from 22 numbered screens into 46 frames** matching the prototype, in greyscale, with placeholder copy. The Week 1 wireframe deliverable now covers every screen in the product and the two canvases share one component set.
>
> **Third pass (2026-11-12, later the same day):** the team **built the Design System canvas** (node 50:2, 180 components) - this closes the largest Criterion 1 gap. The prototype then grew to **48 frames** with two new location dialogs, and the low-fi canvas has **not** caught up, so low-fi/prototype parity is temporarily broken. See the warning in USER_FLOW.md §1.2.

---

## 1. Executive summary

| Rubric dimension | Weight | Current standing | Where the gap is |
|---|---|---|---|
| 1. UI/UX Design, Design System & Prototyping | 25 | **Proficient (19–22)** at best, heading to exemplary | Design System canvas now exists (180 components) but **0 of 305** of its layouts are autolayout · 404 of 409 prototype layouts are absolute · no Cover page · 4 contrast failures on tinted surfaces · touch targets unverified |
| 2. Technical Implementation & MVP | 25 | Not started (Week 3) | Repo URL empty in tracker · stack decided but unproven in code |
| 3. Problem-Solution Fit & Social Impact | 20 | **Developing (10–14)** at present → **Exemplary (18–20)** if localised | Personas are still set in a generic African context; the rubric scores *"localized problem definition"* explicitly |
| 4. AI Transparency & Process Rigor | 15 | **Proficient (11–13)** → **Exemplary (14–15)** possible | Log reformatted to the official template; needs the Week 2–4 rows and evidence of real human refactoring |
| 5. Pitch Delivery & Viva Voce | 15 | Not started (Week 4) | Pitch outline drafted; demo script needs the offline moment rehearsed |

**Bottom line:** the *content* is strong and the *component library* is genuinely good. The risk is **presentational**: a judge who opens the Figma file sees 46 polished frames and **no design system**, and a rubric that explicitly rewards *"autolayout, 8pt spacing grid, design tokens, and component variants"*. Five focused fixes in Week 2 move Criterion 1 from ~19 to 23+.

---

## 2. Week 1 checkpoint compliance

From `ITMSD1_Weekly_Progress_Report_Template.docx`:

| | Checkpoint requirement | Status | Evidence |
|---|---|---|---|
| ☑ | Team roles finalized | **Done** | `README.md` § Team Information |
| ☑ | UN SDG selected + specific, **localized** HMW problem statement | **Done** | [`PROBLEM_FRAMING.md`](./PROBLEM_STATEMENT.md) §7 — primary HMW + 4 persona HMWs + localized Philippine HMW |
| ☑ | Primary and Secondary personas with pain points + **empathy maps** | **Done** | [`PERSONAS.md`](./USER_PERSONAS.md) §1–4, §9 |
| ☑ | User journey flow + mobile **Information Architecture (IA)** mapped | **Done** | [`USER_FLOW.md`](./USER_FLOW.md) §2–7 |
| ☑ | Low-fi wireframes across all primary screens | **Done** | Figma → Low-Fi Wireframe canvas, **46 frames** in greyscale. ⚠️ The prototype is now 48 frames - the two new location dialogs are not yet on the low-fi |
| — | *Weekly Progress Report #1 submitted* | **Written** | [`WEEKLY_PROGRESS_REPORT_01.md`](./WEEK1_VALIDATION.md) |

**Week 1 is complete.** The remaining Week 1 risk is administrative: Master Tracker columns I and J are empty and Figma sharing permissions are not confirmed.

---

## 3. Criterion 1 audit — UI/UX Design, Design System & Prototyping (25 pts)

### 3.1 What is already strong

| Evidence | Measurement |
|---|---|
| **Component library** | **332 component instances across 79 unique components** in the prototype, **325 across 78** in the low-fi canvas, and a **Design System canvas (50:2) with 180 components and 361 instances**. **53 components span multiple screens**: a status bar on all 25 screens, a dialog shell across the dialogs, an app bar on 10 screens, a bottom nav on 5, and a button component used across 6. The Design System canvas names its sets `Primary buttons`, `Secondary buttons`, `Single-line inputs` (Email / Password / Text / Select / Location / Date range / Name), `Bottom navigation` (Home / Map / Reports / Alerts / Settings), `Icon buttons`, `Icons`, `Task cards`, `Map views`, `Area preview`, `Error messages`. This is far ahead of the adjacent project's 17 components. |
| **Known component-library gaps** | A per-frame census shows **19 of 46 frames are 100% hand-built** (zero instances) — including `Sign in`, `Report a problem`, `Alert details`, `Resolve an alert`, `Send saved reports` and 7 dialogs. Five separate button components exist where one variant-driven Button should be. `InputField`, `Card` and `ListRow` have **zero** instances. |
| **Low-fi ↔ hi-fi parity** | The Low-Fi Wireframe canvas was rebuilt on 2026-11-12 to mirror the prototype — the same frame names, the same navigation model, and **the same component set**. ⚠️ *Currently broken:* the prototype is 48 frames and the low-fi is 46. The greyscale wireframes and the colour prototype are literally built from the same components, which is exactly the *"one source of truth"* evidence Criterion 1 rewards, and it removes the risk of the IA drifting between the two deliverables. |
| **Screen coverage** | 25 hi-fi screens + 23 dialogs, including honest empty/error/offline states: `Choose a location`, `Saved offline`, `Send saved reports`, `Draft report`, `Dialog · Map connection`, `Dialog · Loading map`, `Dialog · Alert filters` (empty region), `Dialog · Review access`. |
| **Admin verification workflow** | `Reports to review` → `Review a report` → `Approved report`, with Approve / Request changes / Reject, a *"Verification history"* showing *"Submitted → Reviewed → Verified"*, and a *"Admin access · Assigned regions only"* guard. **This closed the biggest gap in the first audit.** |
| **Colour tokens** | 18 defined tokens with semantic intent (`#16634D` primary, `#AF423D` danger, `#915B13` warning, `#326B83` info + their tints). |
| **Typography scale** | A named, complete scale — Display 22/24/28 Bold, Heading 18/20/21 Semi Bold, Body 13/14/15, Label 10/11/12 — with Inter throughout. |
| **Contrast on white** | Every primary text token passes WCAG AA: `#183B32` **12.28:1**, `#104D3D` **9.76:1**, `#16634D` **7.18:1**, `#24704C` **6.01:1**, `#64766D` **4.77:1**. All severity pairs pass: `#AF423D`/`#FCEDE9` **5.02:1**, `#915B13`/`#FFF1D7` **5.07:1**, `#326B83`/`#EAF2F7` **5.20:1**. |
| **Accessible status encoding** | Every severity badge carries a text label (`HIGH` / `MEDIUM` / `LOW`), not colour alone. |
| **Plain-language field labels** | The report form now asks *"What did you see? / Where did it happen? / What happened? / How urgent is it?"* instead of abstract field names — a deliberate readability improvement for the low-literacy persona. |

### 3.2 Gaps — with the fix for each

| # | Gap | Measurement | Impact | Fix | Effort |
|---|---|---|---|---|---|
| **1** | ✅ **CLOSED 2026-11-12.** The **Design System** canvas exists at node `50:2` with **180 components**, 361 instances and sections `01 · Colors`, `02 · Typography`, `03 · Corners`. A **Cover** canvas exists at node `99:2`. The four pages are in the correct order: Cover → Design System → Low-Fi Wireframe → Clickable Prototype. | 4 canvases, correct order | **Done.** This was the highest-value gap in the audit and the team closed it in a single day. | Remaining: (a) the canvas has **0 autolayout frames of 305** — convert the components; (b) bind the token set as real Figma Variables. | **~2.5 h** |
| **2** | **Autolayout is effectively absent.** | **404 of 409 prototype layouts use `mode: none`** (absolute positioning); only **5** autolayout frames exist (4 column, 1 row). The new Design System canvas is worse: **0 of 305**. | **Critical.** "Autolayout" and "autolayout variants" are named explicitly in Criterion 1 and in the Week 2 checkpoint (*"component library built with autolayout and variants"*). 77 components with no autolayout is a visible contradiction. | Convert the highest-traffic components first: **main navigation → buttons → input fields → status badge → list rows → cards**. Set direction, padding, gap from the 8pt scale, and create variants (primary/secondary/danger; default/focus/error/disabled). You do not need all 77 converted — 8–12 key components demonstrably using autolayout is enough to evidence the practice. | **~4–6 h** |
| **3** | **Off-grid offsets.** Re-measured on the current prototype: **78 distinct x-offsets, 45 of which are not even multiples of 4** and 60 are not multiples of 8. | 45/78 off-grid | **High.** Criterion 1 names the *"8pt spacing grid"* and Slide 5 must show it. | Normalise to a 4pt half-step / 8pt base scale. Because most offsets come from components, fixing the **component** spacing fixes most screens at once. The autolayout pass in #2 eliminates the class of bug rather than patching it. | **~3 h** (mostly absorbed by #2) |
| **4** | **Contrast failures on tinted surfaces.** `#64766D` (the body/label grey) fails AA for small text on four tints: `#E3F0E8` **4.11:1**, `#E6F3E9` **4.22:1**, `#E4EAE5` **3.95:1**, `#DDE6DF` **3.78:1** (4.5:1 required). It passes on `#F5F8F5` at **4.51:1**, but only marginally. | 4 tinted pairs failing | **High.** Criterion 1 names *"WCAG AA contrast"*; Slide 5 claims AA compliance. | Replace `#64766D` with `#183B32` (10.46:1 on `#E3F0E8`) or `#16634D` (6.12:1 on `#E3F0E8`) wherever it sits on a tinted surface, **or** darken the tint. Audit every chip/badge/helper-text instance on a tinted background. | **~1 h** |
| **5** | **Touch targets unverified.** The bottom-nav tap targets are component instances whose dimensions the file does not expose to the audit tool; the two measurable instances are 324×50 and 324×57, both fine. | 0 verified at 48dp | **Medium-High.** Slide 5 must state *"48×48dp minimum touch targets"* and Criterion 1 names *"touch targets"*. | Manually select every icon-only control (main nav, map zoom/location/layers, photo remove `×`, severity chips, notification icons) and confirm ≥48×48dp. Add `hitSlop` where the visual is smaller — and mirror that in code ([`ARCHITECTURE.md`](./../working/WEEK3_ARCHITECTURE_PLAN.md) §8). | **~1 h** |
| **6** | **No prototype-interaction verification.** The MCP inspection reads geometry and tokens, not Figma prototype *reactions*, so links, transitions, and "Smart Animate" settings are unconfirmed. | Not measurable via API | **Medium-High.** Criterion 1's exemplary band requires a *"seamless clickable prototype"*; the Figma deliverable requires a *"playable clickable flow"*. | Open the **Prototype** tab. Verify every nav target has a link, the main-nav tabs switch frames, the `+` opens the capture modal, all 23 dialogs open and dismiss, `Dialog · Review access` actually appears when a non-admin triggers a review, and back-navigation is wired. Set the **starting frame** to `Welcome`. Name the flow *"Full App (Splash)"*. | **~1.5 h** |
| **7** | **Sign-in error state was removed in the rebuild.** The old `21 Sign in error` frame is gone and no replacement exists. | 0 error states on `Sign in` | **Medium.** *"Unable to sign in"* was a good demonstration of a validated error. | Re-add an inline error banner on `Sign in` (e.g. *"Unable to sign in — check your email and password"*) plus a failed-field style on `Email input` / `Password input`. | **~30 min** |
| **8** | **No dark mode.** | 0 dark screens | **Low.** Not required by the rubric. | Only if Week 2 time remains. Lower priority than #1–#4. | — |
| **9** | **No Community Monitor-specific home variant.** `Home` is task-adaptive (*"Choose a task to get started."*) but generic; there is no monitor-specific content (alerts near me, my reports' status, language toggle). | 1 generic home | **Medium-High (Criterion 3 + Demo).** The monitor persona is still the least-served of the three. | Add a Community Monitor variant of `Home` — *"Alerts near you"*, *"Your reports"*, one large Report button, prominent language toggle — plus a 3-field fast-capture variant of `Report a problem`. | **~3 h** |
| **10** | **Low-fi canvas carries almost no autolayout.** | **1 autolayout frame of 462** in the low-fi canvas, vs 5 of 397 in the prototype | **Low.** The rubric's *"autolayout variants"* criterion applies to the component library in the prototype, not to greyscale wireframes. Do not spend Week 2 time here. | Fix the prototype's components instead (gap #2). | — |

### 3.3 What the rebuild already closed

| Gap flagged in the first audit | Status now |
|---|---|
| Admin has no screens / no verification queue | ✅ `Reports to review`, `Review a report`, `Approved report`, `Dialog · Review access` |
| No audit / history trail | ✅ `Approved report` → *Verification history* · *"Submitted → Reviewed → Verified"* |
| No offline map usability states | ✅ `Dialog · Map connection`, `Dialog · Loading map`, `Dialog · Map layers and recovery` |
| No draft lifecycle / delete confirmation | ✅ `Dialog · Unfinished report`, `Dialog · Delete draft` |
| No region filter or empty-state | ✅ `Dialog · Alert filters` incl. *"Region C · No detections"* |
| Community Monitor has no home | ◐ Partly — `Home` is now task-adaptive, but still not monitor-specific |

### 3.4 Additional gap found 2026-11-12 — two screens sit at 98% of viewport height

| Gap | Measurement | Impact | Fix | Effort |
|---|---|---|---|---|
| **11** | **Two screens run to 98% of the viewport.** `Report a problem` content reaches **786** and `Sign in` **785**, against a 360×800 device frame — only ~14px of headroom. The next-tightest are `Welcome` 764, `Create account` 729, `Map` 720. | **Medium-High (Criterion 2).** This is exactly the overflow case the official weekly-report template warns about: *"Layout overflow on small phone screens… Yellow/black RenderFlex error tape in Flutter."* Any text reflow pushes these into clipping, and the capture form may collide with the pinned bottom navigation. | Open both frames and check the last field clears the bottom nav. Tighten the capture form's vertical rhythm by 8–12px (reduce one `space/3` to `space/2`) or make the form area scrollable. In code, wrap in a `SingleChildScrollView` — see the rubric's own worked example. | **~30 min** |

*Measured by walking the Low-Fi canvas tree and computing absolute content extents per frame. No frame is currently clipped — this is a margin warning, not a present defect.*

### 3.5 Consolidated improvement priority

Everything in §3.2 and §3.4, ordered by points-per-hour. This is the single actionable list for Week 2.

| # | Improvement | Rubric criterion | Points at stake | Effort |
|---|---|---|---|---|
| 1 | **Localise** — `Dialog · Language` → English / Filipino / Ilocano; Region A–E → Isabela LGUs; personas renamed to match | Criterion 3 (20) | 8–10 | **30 min** |
| 2 | **Finish the Design System** — bind the token set as Figma Variables and convert its components to autolayout (0 of 305 today) | Criterion 1 (25) | 3–4 | **2.5 h** |
| 3 | **Autolayout 12 components** — 404 of 409 prototype layouts are currently absolute | Criterion 1 (25) | 3–4 | **3.5 h** |
| 4 | **Fix 4 contrast pairs + verify every touch target ≥ 48 dp** | Criterion 1 (25) | 2–3 | **1.5 h** |
| 5 | **Restore low-fi ↔ prototype parity** — the prototype has 48 frames, the low-fi has 46 | Criterion 1 + process | 1–2 | **20 min** |
| 6 | **Add 3 screens** — Community Monitor home, Admin dashboard, sign-in error | Criterion 3 + live demo | 3–5 | **4 h** |
| 7 | **Prototype link QA** — starting frame = `Welcome`, name the flow, verify all 23 dialogs, Smart Animate on shared components | Criterion 1 (25) | 2–3 | **1.5 h** |
| 8 | **Check the 2 tight screens** — `Report a problem` and `Sign in` sit at 98% of viewport height | Criterion 2 (25) | 1–2 | **30 min** |
| 9 | **Exploration section** on the low-fi canvas + fidelity key | Process evidence | 1 | **1 h** |
| | **Total** | | **~24–38** | **~16 h** ≈ 5.3 h each |

**Do not** rebuild the 48 frames, add dark mode, or simplify the wireframe. Those are the three tempting changes that cost time and return nothing.

### 3.6 Recommended Week 2 order

1. **#1 Design System canvas + Cover** (2 h) — unblocks Slide 5, biggest single ROI
2. **#9 Community Monitor home variant + 3-field fast capture** (3 h) — the last real persona gap
3. **#2 Autolayout on 8–12 key components** (4–6 h) — the rubric's named criterion
4. **#4 Contrast fixes** (1 h) — cheap, and it makes the AA claim true
5. **#3 Grid normalisation** (3 h, mostly absorbed by #2)
6. **#5 Touch-target audit** (1 h) + **#6 Prototype link QA** (1.5 h) + **#7 Sign-in error** (30 min)

Total ≈ **16–19 hours across 3 members** — roughly 5–6 h each, which fits a Week 2 sprint alongside the peer usability test.

### 3.5 Is the Low-Fi canvas still genuinely low-fidelity?

> A judge or viva voce panel will ask this. The answer is measured, not asserted.

| Fidelity signal | Low-Fi Wireframe | Clickable Prototype | Verdict |
|---|---|---|---|
| Chromatic colours | **0** (8 pure greys: `#252525` `#3A3A3A` `#686868` `#BEBEBE` `#E8E8E8` `#ECECEC` `#F7F7F7` `#FFFFFF`) | 13 (brand green + status tints) | Greyscale |
| Shadows / elevation | **0** | 4 shadow tokens (`0px 3px 10px`, `0px 4px 14px`, `0px 3px 8px`, `0px 12px 36px`) | No depth |
| Gradients / blurs | **0** | 0 | Flat |
| Raster photography | **0** imageRefs | 3 | No photos |
| Corner radii | 7, 8, 12, 16 | +22, 24 | Restrained |
| Vector icons | 106 | 90 | Expected in both |
| Copy | *"Add a short title"*, *"Describe what you saw"*, *"Illustration"*, *"Logo"*, *"Avatar"*, *"Example state · Wireframe state"* | *"Tap to add a short title"*, *"Demo · Tap fields to add example details"*, real demo data | Placeholder |
| Typography | Inter, 19 sizes | Inter, 19 sizes | Identical — see note |
| Component instances | 325 across 78 components | 331 across 77 components | Same library |

**Conclusion:** greyscale + zero elevation + zero photography + placeholder copy are the four markers that separate a wireframe from a finished screen. The Low-Fi canvas satisfies all four. It is legitimately low-fidelity while sharing the prototype's structure — which is exactly the intended outcome.

**Note on the identical type scale:** a textbook-purist low-fi would use one or two font sizes. Keeping the real Inter scale is a deliberate trade-off — the rubric scores Criterion 1 on *"design system consistency"* and *"typographic scale"*, and collapsing the scale in the wireframe would hide work that earns points. The greyscale palette, missing elevation, and placeholder copy still make the fidelity difference unambiguous.

**Defence in the viva:** *"The Low-Fi canvas is greyscale by design — no brand colour, no shadows, no photography, and placeholder copy instead of microcopy. It proves the information architecture across all 46 screens first. The greyscale frames are built from the same component library as the full-fidelity prototype, so the structure cannot drift between the two."*

**Recommended addition (≈20 min):** the file currently **opens on the Low-Fi canvas**, so a judge sees 46 greyscale frames before finding the design. Add a small fidelity key on the Low-Fi canvas:

> **Low-Fi Wireframe — EcoTrack · SDG 15**
> Greyscale · no colour, no elevation, no imagery · placeholder copy
> Structure and flow only — the same frame set as the Clickable Interactive Figma Prototype canvas
> → Full fidelity: see the *"Clickable Interactive Figma Prototype"* page
> → Design tokens and component library: see the *"Design System"* page

### 3.6 Does the Low-Fi canvas need to be made simpler?

> A judge or viva voce panel may ask this. The answer is **no**, and it is measurable.

#### Evidence that the two canvases are genuinely different fidelity passes

| Measure | Low-Fi | Prototype |
|---|---|---|
| Distinct text strings | 366 | 360 |
| Shared between the two | 350 | 350 |
| **Unique to this canvas** | **16** | **10** |
| Of those unique strings | **15 are placeholders** | **10 are demo hints** |

- **Low-Fi only:** `Add a short title` · `Describe what you saw` · `Your full name` · `Enter your password` · `Logo` · `Illustration` · `Avatar` · `name@example.com` · `Before` / `After`
- **Prototype only:** `Tap to add a short title` · `Tap to fill demo email` · `Demo · Tap fields to add example details` · `Tap to confirm the new password`

The wireframe says **what** the field is. The prototype says **how** it behaves. That is a structural difference in the copy layer, not a colour filter — and it is exactly the difference a low-fidelity pass should have.

#### Why simplifying would hurt

| "Simplify it" | Why not |
|---|---|
| Strip the 23 dialogs | The Week 1 checkpoint requires *"low-fidelity wireframes across **all** primary application screens"* — removing screens risks reading as incomplete |
| Collapse 19 type sizes to 3 | A real type system on the wireframe signals *"we had a system from day one"* — that is Criterion 1 evidence, not a liability |
| Replace 106 vector icons with grey boxes | Professional wireframe kits use real icons. Colour, elevation and photography are what read as high-fidelity — not icons |
| Detach the shared components | The parity claim (*"same component set, two fidelities"*) is the strongest answer available and it is verifiable by a judge |

#### What to add instead — evidence of exploration

The one valid criticism of the current wireframe is *"you designed once and desaturated it."* The fix is an **exploration section**, not less detail.

**Spec — ~45 minutes**

```
┌─ 00 Exploration ────────────────────────────────────────────────┐
│  How did we arrive at this layout?                               │
│  [Option A]        [Option B]        [Option C]  ← SELECTED      │
│  4 labelled         photo-first      single-column              │
│  fields             compact          long form                   │
│                                                                   │
│  A — rejected: too many steps for a volunteer reporter            │
│  B — rejected: hides location, which is legally required          │
│  C — selected: matches the quick-capture goal                    │
└───────────────────────────────────────────────────────────────────┘
```

- Build it **greyscale** at **360 wide**, same frame size as every other wireframe, so it does not look bolted on.
- Do it for `Report a problem` first — it is the Community Monitor's screen and the one with the most workflow risk.
- Add `Home` second if time allows.
- The rejection reasons are the point. They turn a picture into a documented decision.

#### The cheap second move — a fidelity key (20 min)

> **Low-Fi Wireframe — EcoTrack · SDG 15**
> Greyscale · no colour, no elevation, no imagery · placeholder copy
> Structure and flow only — the same frame set as the Clickable Interactive Figma Prototype canvas
> → Full fidelity: see the *"Clickable Interactive Figma Prototype"* page

#### Verdict

**Do not simplify.** The wireframe is correctly structured, covers every screen the checkpoint requires, and already carries a demonstrably different copy layer from the prototype. Spend the remaining Week 2 time on the **Design System canvas** and the **12 components** — that is where the points are.

---

## 4. Criterion 3 audit — Problem-Solution Fit & Social Impact (20 pts)

| Element | Rubric language | Our standing | Action |
|---|---|---|---|
| Localized problem definition | *"Compelling, **localized** problem definition"* = 18–20 · *"Generic problem statement"* = 10–14 | **Currently generic.** Personas are set across Kiswahili/Français regions with abstract "Region A–E". The team is a Philippine school and the adjacent project is set in Davao Oriental. | **Highest-value fix in the whole project.** Localise to Philippine reality: **Bantay Gubat / CFPM** volunteers, **Isabela / Cagayan Valley** forest cover, **DENR PENRO/CENRO** as admin, **English / Filipino / Ilocano** as the language set. The `Dialog · Language` frame currently offers English/Kiswahili/Français and must change. |
| Depth of user empathy | *"depth of user empathy"* | **Strong** — 4 personas, empathy maps, real quotes, say/think/do/see/hear | Add one line to Slide 2 stating how many people you actually spoke to and when. Judges reward *evidence of research* over assertion. |
| Relevance to UN SDG | *"relevance to selected UN SDG"* | **Strong** — target-by-target mapping for 15.1, 15.2, 15.5, 15.8, 15.a, 15.b | Keep the target mapping on Slide 9 or the appendix. |
| Practical viability | *"practical real-world feasibility and viability"* | **Strong** — no new hardware, existing ranger workforce, 3-phase rollout | Keep the viability paragraph on Slide 9. |
| Solution solves the core pain | *"solution directly solves core community pain points"* | **Strong** — each of the four sub-problems maps to screens | Make sure the demo on Slide 8 visibly resolves pain #1 (work lost in transit) with the offline moment. |

---

## 5. Criterion 4 audit — AI Transparency & Process Rigor (15 pts)

| Element | Our standing | Action |
|---|---|---|
| Completeness of `AI_DISCLOSURE_LOG.md` | Now matches the **official template** exactly: header block, instructions, the two reference benchmark examples, the numbered audit table with all six official columns, and the Academic Honesty declaration with three signature blocks. 9 logged rows + 2 reserved. | Fill the 2 reserved rows in Weeks 2–4. |
| Prompt sophistication | Our prompts are *artefact-anchored* ("read the prototype canvas and cite the screen for every claim") rather than open-ended ("design me an app"). That is genuinely more sophisticated than the benchmark examples in the official template. | **Make this explicit in Slide 7** — it is the thing that separates 14–15 from 11–13. |
| Evidence of human refactoring | Strong and logged: persona names/ages/quotes replaced with real interviews, problem statement rewritten, metric targets discarded, contrast measured rather than accepted. | Add one **side-by-side** example to Slide 7: Prompt → Raw AI Output → Human-Refactored. The rubric literally asks for this visual. |
| Individual accountability | The log is attributed per member. | **Leonard (Product & AI Specialist)** should own this file's maintenance — it is literally his role, and it gives him a defensible viva voce answer. |
| Code adaptation | Not yet — Week 3. | Log at least 3 code-generation entries in the official format, including one where the AI output was **rejected**. |

---

## 6. Deliverables 1–5 status

| # | Deliverable | Format | Status | Action |
|---|---|---|---|---|
| 1 | **GitHub Repository URL** | Public repo, clean structure, README, `AI_DISCLOSURE_LOG.md` in root | ⚠️ **Not started** — tracker column J is empty | Repo initialised with the Week 1 docs in `docs/`; add the feature-first source structure from [`ARCHITECTURE.md`](./../working/WEEK3_ARCHITECTURE_PLAN.md) §3 and make it public |
| 2 | **Figma Project URL** | Playable clickable flow, tokens, typography, 8pt grid, autolayout variants | ⚠️ **Partial** — flow exists, but tokens/grid/autolayout are not *visible* | Fix §3.2 items 1–3, then set sharing to *Anyone with the link can view* and paste into tracker column I |
| 3 | **Working Mobile Build & 2-min MP4** | Installable APK / TestFlight + unedited recording | ❌ Week 3 | Follow [`ARCHITECTURE.md`](./../working/WEEK3_ARCHITECTURE_PLAN.md); record the video with the offline moment as the climax |
| 4 | **Pitch Deck** | 8–10 slides, following the official outline | ⚠️ Outline drafted | [`PITCH_DECK_OUTLINE.md`](./../working/WEEK4_PITCH_DECK_PLAN.md) is written — build it in Google Slides / Figma Slides, export PDF backup |
| 5 | **Live Demo Day Viva Voce** | 5 + 2 + 3 minutes | ❌ Week 4 | [`ARCHITECTURE.md`](./../working/WEEK3_ARCHITECTURE_PLAN.md) §11 + the pitch appendix checklist |

---

## 7. Exclusivity check (re-verified)

| Team | ID | Title | SDG | Risk |
|---|---|---|---|---|
| **Team JBL** | **F-8** | **EcoTrack: A Land and Forest Conservation Monitoring System** | **15** | — |
| wxyz | F-4 | GreenPulse: A Community Climate Action and Environmental Monitoring App | 13 | **Low.** Overlap is limited to the generic "report a thing with photo + location, track status, admin reviews" pattern. We have **zero** overlap in detection source (satellite vs none), triage model (severity + assignment vs none), offline behaviour (offline-first vs none), verification (hard gate vs soft "Under Review"), access model (role + region scoped vs flat), or measurement (hectares lost vs weather readings). |

**None of the other 40 teams touch SDG 15** — the SDG lane is uncontested. The only differentiator work required is versus F-4, and it is documented in [`PROBLEM_FRAMING.md`](./PROBLEM_STATEMENT.md) §5.

---

## 8. Week 2 action list (checklist)

- [ ] Add **Design System** canvas — colour tokens + contrast ratios, type scale, 8pt spacing scale, elevation, component sheet, icon set
- [ ] Add **Cover** canvas — title, SDG 15 badge, screen count, component count, *"Press Play → Full App (Splash)"*
- [ ] Add a **Community Monitor home variant** and a **3-field fast-capture** variant of `Report a problem`
- [ ] Convert **8–12 key components to autolayout** with variants (main nav, button, input, badge, list row, card)
- [ ] Fix the **5 `#64766D`-on-tint contrast failures**
- [ ] Normalise **off-grid offsets** to the 4/8pt scale
- [ ] Audit **every touch target ≥ 48×48dp**
- [ ] **Prototype link QA** — every nav target, tab, and all 23 dialogs; set the starting frame; name the flow
- [ ] Re-add the **sign-in error state**
- [ ] **Localise** personas + `Dialog · Language` to the Philippine context
- [ ] Run **peer usability testing** with ≥2 Section C students; record what changed
- [ ] Publish **Figma URL** (col I) and **GitHub URL** (col J) in the Master Tracker
- [ ] Rename the Figma file **EcoTracker → EcoTrack**
