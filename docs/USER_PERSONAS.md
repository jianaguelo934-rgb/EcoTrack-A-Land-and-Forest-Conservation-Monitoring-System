# USER_PERSONAS.md
> **Milestone** | Week 1 - Problem Framing, Personas & Low-Fi Wireframes
> **Status** | COMPLETE - submitted 2026-11-12
> **Read time** | 4 min

*Source: Figma file "EcoTracker — A Land and Forest Conservation Monitoring System" (node 7-10)*
*Companion doc: [`PROBLEM_FRAMING.md`](./PROBLEM_STATEMENT.md)*

Roles present in the design: **Ranger**, **Community Monitor**, **Admin** (sign-in tabs on screens 02/21).

---

## 1. Amina — Field Ranger (Primary)

| | |
|---|---|
| **Age / role** | 31 · Forest Ranger, conservation NGO · 3 reserves (Region A & B) |
| **Context** | Patrols on foot 6–8 hrs/day in rugged terrain. Phone in a waterproof case, mid-range Android. Signal only near the ranger post. Swahili speaker; English OK for reading, writes in Swahili. |
| **Literacy / digital confidence** | Medium. Comfortable with maps, WhatsApp, camera; dislikes forms longer than a minute. |
| **Goals** | 1. Reach the flagged area before the next patrol. 2. Know what's actually there (clearing? fire? regrowth?). 3. Capture evidence that cannot be disputed. 4. See that her reports get *used*, not just filed. |
| **Frustrations** | Satellite pins with no context; WhatsApp photos that vanish; paper notebooks that get wet; no way to know if someone already checked a spot; alerts assigned to nobody; admin back-and-forth to close a case. |
| **Current workaround** | Screenshots coordinates onto a paper patrol sheet; sends photos on WhatsApp; calls the office when in signal range. |
| **Key quote** | *"If the photo doesn't upload here, I'm not going to bother taking the photo."* |
| **Success looks like** | I know which alerts are mine, I can file a complete report in under a minute with no signal, and I can see that my evidence closed the case. |

**Behaviours to design for:** prioritises by *distance + severity*; works in bursts at the end of a patrol; checks the map before leaving camp; wants the next step obvious; needs location to be forgiving (GPS or manual).

**Screens that must work for her:** `Map` · `Area details` · `Alerts` · `Alert details` · `Report a problem` · `Saved offline` · `Send saved reports` · `Resolve an alert` · `Choose a location` · `Sign in`

---

## 2. Joseph — Community Monitor (Primary)

| | |
|---|---|
| **Age / role** | 24 · Community Monitor (volunteer, ~2 days/week) · lives on the forest edge, farms alongside it |
| **Context** | Trained by the NGO, uses a shared/older Android with ~4 GB free and a metered data bundle. Swahili first language, limited English reading. Reports illegal logging, fire, encroachment, wildlife. |
| **Literacy / digital confidence** | Low-to-moderate. Voice notes, photos, WhatsApp, icon-first navigation. A 12-field form is a wall. |
| **Goals** | 1. Report what I saw without fear of blame. 2. Know it reached someone. 3. Do it in my own language. 4. Do it without spending my own data. |
| **Frustrations** | English-only forms → abandons mid-way; "location required" errors; unclear whether the photo attached; camera-permission confusion; phone storage full; no feedback for days after submitting; phone call is the only reliable channel. |
| **Current workaround** | Calls or WhatsApps a ranger with a photo; waits for a reply. |
| **Key quote** | *"The form asked too many things. So I sent the photo to the ranger's WhatsApp instead."* |
| **Success looks like** | I can send a photo + one tap of category in my language, and I get told "received, being checked". |

**Behaviours to design for:** 1–2 taps per field; large tap targets; photo-first; language switch prominent; forgiving location; visible confirmation + status; no loss on failure.

**Screens that must work for him:** `Welcome` · `Sign in` (Community Monitor tab) · `Home` · `Report a problem` · `Saved offline` · `Reports` · `Notifications` · `Choose a location` · `Create account`

> ⚠️ **Gap (narrowed since the first audit):** the design offers a *Community Monitor* role at sign-in, and the prototype rebuild made `Home` task-adaptive (*"Choose a task to get started."* → Check alerts / Report a problem / Explore the map) with question-form labels on the report form (*"What did you see? / Where did it happen? / What happened? / How urgent is it?"*). What is still missing is a **monitor-specific home** (alerts near me / my reports and their status / what's happening in my area / a prominent language toggle) and a **3-field fast-capture path** for a volunteer on a 4 GB phone. The capture and feedback loop itself — `Report a problem` → `Saved offline` → `Send saved reports` → `Report sent` → Notifications — now exists end to end.

---

## 3. Dr. Grace — Conservation Program Director / Org Admin (Primary)

| | |
|---|---|
| **Age / role** | 46 · Program Director & org admin · 5 regions (A–E), 20+ staff, 3 funders |
| **Context** | Desk-based, laptop + phone, lives in Excel and grant reports. Accountable to a board and to donors. |
| **Literacy / digital confidence** | High, data-fluent. Wants to export and wants an audit trail. |
| **Goals** | 1. Know which regions are degrading and why. 2. Route scarce ranger capacity to the right place. 3. Ensure submitted reports are *verified* so the data is defensible. 4. Control who sees what. 5. Produce funder-ready impact reports without hand-built spreadsheets. |
| **Frustrations** | Reports arrive late or not at all; can't distinguish *detected* from *verified*; alert backlog with no owner; duplicate assignments; no audit trail of who resolved what and why; every month is another manual slide deck. |
| **Current workaround** | Spreadsheets fed by hand from WhatsApp exports and ranger call-ins. |
| **Key quote** | *"I can tell you how much forest we lost. I can't tell you whether anyone actually did anything about it."* |
| **Success looks like** | One screen shows open vs verified alerts per region, every alert has an owner, every resolution has notes and evidence, and I export the funder CSV in 30 seconds. |

**Behaviours to design for:** filters first (region, severity, status, date); bulk assignment; a verification queue; audit trail; export; role & region administration; weekly cadence (Monday review).

**Screens that must work for her:** 03 Home dashboard · 06 Alerts · 07 Alert detail · 10 Insights · 12 Profile (assigned regions) · 19 Resolve alert · 23/24/25 Report review states · Dialogs: Assign ranger, Date range, Export

> ⚠️ **Gap (mostly closed since the first audit):** the app claims *"Organization-managed access… Your role and regions are assigned after approval"* and offers an Admin role. The prototype rebuild now delivers the **verification queue** (`Reports to review` → `Review a report` → `Approved report`, gated by `Dialog · Review access` — *"Only an organization-authorized admin can review reports."*) and an **audit/history view** (`Approved report` → *Verification history* → *"Submitted → Reviewed → Verified"*). What remains is one screen: **(a) Admin — Team & access management**, so an admin can actually *assign* roles and regions rather than only review reports.

---

## 4. Daniel — Donor / Grant Monitor (Secondary, indirect)

| | |
|---|---|
| **Age / role** | 52 · Grants & impact officer at a foundation (does not log in) |
| **Context** | Consumes the monthly export only. Judges the programme on hectares protected, alerts resolved, and evidence of verification. |
| **Goals** | Verified numbers, comparable across regions and months, with a clear note on what is counted. |
| **Frustrations** | Inconsistent definitions between reports; data that changes without a note; no way to separate *verified* from *detected*. |
| **Key quote** | *"If it's not verified, it's a rumour with a satellite image."* |
| **Needs from the product** | Forest loss over time, alerts by region, verification status, and a clean CSV/PDF export with clear definitions. |

---

## 5. Persona → Screen Traceability

> Screen names are the **current** names in the Clickable Interactive Figma Prototype canvas (verified 2026-11-11). The prototype was rebuilt after these documents were first written, so the older numeric names no longer exist.

| Prototype screen | Amina (Ranger) | Joseph (Monitor) | Grace (Admin) | Daniel (Donor) |
|---|---|---|---|---|
| `Welcome` | ● | ●●● | ○ | — |
| `Sign in` | ● | ●●● | ●● | — |
| `Home` | ●●● | ●● | ●●● | ○ |
| `Map` | ●●● | ●● | ●● | — |
| `Area details` | ●●● | ●● | ●● | — |
| `Alerts` | ●●● | ●● | ●●● | ○ |
| `Alert details` | ●●● | ● | ●●● | — |
| `Report a problem` | ●●● | ●●● | ○ | — |
| `Reports` | ●●● | ●●● | ●● | — |
| `Forest trends` | ● | — | ●●● | ●●● |
| `Notifications` | ●●● | ●●● | ●● | — |
| `Settings` | ●● | ●● | ●●● | — |
| `Create account` | ● | ●●● | ●● | — |
| `Reset password` | ●● | ●●● | ●● | — |
| `Check your email` | ●● | ●●● | ●● | — |
| `Draft report` | ●●● | ●●● | ●● | — |
| `Saved offline` | ●●● | ●●● | — | — |
| `Send saved reports` | ●●● | ●● | ● | — |
| `Resolve an alert` | ●●● | — | ●●● | — |
| `Choose a location` | ●●● | ●●● | — | — |
| `Report sent` | ●● | ●●● | ● | — |
| `Report details & review` | ●● | ●●● | ●● | — |
| `Reports to review` | — | — | ●●● | — |
| `Review a report` | — | — | ●●● | — |
| `Approved report` | ● | ● | ●●● | ○ |
| 23 dialogs (category, assign, language, date range, export, location, map states, draft states, review access…) | ●● | ●● | ●● | — |

**Legend:** ●●● core · ●● important · ○ peripheral

---

## 6. Flows to wireframe per persona

**A. Amina — Detect → verify → close (offline-capable)**
Onboarding (`Welcome`) → Sign in (Ranger) → Home → Map (nearby alert, pin) → Area details (before/after + loss ha) → Alerts list (filter High) → Alert details (Detected) → Assign to me → Directions → Report a problem (photo, category, severity, location, notes) → Saved offline (Queued) → Send saved reports (progress) → Report sent → Alert resolved (notes + evidence + confirm)

**B. Joseph — Spot → report → get feedback**
Onboarding → Sign in (Community Monitor) → Monitor home *(to be designed)* → "Report something" → Simplified capture (photo + category + one-line description; location via current/manual) → Saved offline → Queued → Sync → Submitted → Notification "Report received / verified / update"

**C. Grace — Triage → verify → report**
Home dashboard → Alerts (Region A, High, Unassigned) → Alert detail → Assign to field team → Review submitted reports queue *(to be designed)* → Verify / Request more info → Insights (date range) → Export CSV/PDF → Team & access management *(to be designed)*

---

## 7. Recommended wireframe additions driven by these personas

| # | Addition | Persona | Why |
|---|---|---|---|
| 1 | **Community Monitor home** — nearby alerts, my reports + status, big "Report" button, language toggle | Joseph | Role exists in sign-in but has no home |
| 2 | **Progressive-disclosure report form** for monitors (photo-first, 4 fields, expandable details) | Joseph | Current form is ranger-length and English-first |
| 3 | **Admin: Team & access management** — invite, assign role, assign regions | Grace | Claimed in copy, not designed |
| 4 | **Admin: Verification queue** — list of Submitted reports, Verify / Request more info | Grace | ✅ **Built** — `Reports to review` → `Review a report` → `Approved report`, gated by `Dialog · Review access` |
| 5 | **Audit & history log** per alert/report — who did what, when, notes, evidence | Grace, Daniel | Trust + defensibility |
| 6 | **Distance & travel time on the alert list** ("1.4 km away") | Amina | Tests assumption A1 (distance + severity) |
| 7 | **First-field-use coach marks** on the capture flow (not just onboarding) | Amina, Joseph | Offline-first usage; reduce abandonment |
| 8 | **Offline map download manager** | Amina, Joseph | Map tiles are unusable without it |
| 9 | **Feedback to the community monitor after submission** (received → verified → acted on) | Joseph | Tests assumption A2 |
| 10 | **Empty/placeholder discipline** — define "Time unavailable / Coordinates unavailable" states | All | Already in design; make them intentional |

---

## 8. Open questions for research

1. What is the real detection → action SLA today, and who owns each region?
2. Do rangers actually carry a GPS-capable phone on patrol, and how often is location available?
3. What is the minimum evidence set a funder will accept as "verified"?
4. Which languages, in which regions? (Design offers English / Kiswahili / Français.)
5. What is the real cost per hectare protected, and can EcoTrack feed a business case?
6. Who is the review authority for `Submitted → Verified` in practice — a ranger, an admin, or a committee?
7. Can the community monitor role be paid or credited, and how does that affect motivation to report?

---

## 9. Empathy Maps

> Required by the Week 1 checkpoint: *"Primary and Secondary User Personas created with documented pain points and **empathy maps**."*

### 9.1 Amina — Field Ranger

| Quadrant | Notes |
|---|---|
| **Says** | *"If the photo doesn't upload here, I'm not going to bother taking the photo."* · *"Is this one mine, or is somebody else already on it?"* · *"Don't make me type it again."* |
| **Thinks & Feels** | *Proud of her patrol and her eye for forest change. Anxious when she can't prove what she saw. Frustrated by having to repeat herself to an office. Resentful of admin process, protective of her time.* |
| **Does** | Checks the map before leaving camp. Screenshots coordinates onto paper. Sends photos over WhatsApp because it is instant. Works in bursts at the end of a patrol. Keeps her own mental list of "spots I've already checked." |
| **Sees** | Rain, ruts, canopy gaps on a ridge. Other rangers' trucks leaving camp. Paper patrol sheets going soft. |
| **Hears** | *"Is the signal back yet?"* · *"We'll check it next week."* · Radio chatter with no answer. |
| **Pains / Gains** | **Pains:** ambiguous alerts, duplicate patrols, lost photos, admin back-and-forth, battery and data limits. **Gains:** a clear next action, a report that survives the day, evidence that closes a case. |

### 9.2 Joseph — Community Monitor

| Quadrant | Notes |
|---|---|
| **Says** | *"The form asked too many things. So I sent the photo to the ranger's WhatsApp instead."* · *"Did they get it?"* · *"Where do I put the picture?"* |
| **Thinks & Feels** | *Wants to protect the forest he lives beside. Afraid of being blamed or of causing trouble. Overwhelmed by long forms. Proud when his report leads to action. Unsure whether the app "is for people like me."* |
| **Does** | Takes photos at dawn and dusk. Calls or WhatsApps a ranger. Counts on his phone storage. Switches off mobile data. Uses a shared device. |
| **Sees** | Timber trucks at night. Smoke on the ridge. Neighbours who report but never hear back. |
| **Hears** | *"Report it properly."* · A ranger saying *"I'll check it."* and then nothing. |
| **Pains / Gains** | **Pains:** English-only long forms, unclear photo attachment, no confirmation, no feedback, storage limits, no credit. **Gains:** one tap that works, clear confirmation, and news that something was done. |

### 9.3 Dr. Grace — Conservation Program Director / Org Admin

| Quadrant | Notes |
|---|---|
| **Says** | *"I can tell you how much forest we lost. I can't tell you whether anyone actually did anything about it."* · *"Who owns this?"* · *"Show me the evidence."* |
| **Thinks & Feels** | *Accountable to a board and to funders. Frustrated by data that arrives late or not at all. Protective of the organisation's credibility. Cautious about publishing unverified figures. Wants control without micromanaging.* |
| **Does** | Reviews the alert backlog every Monday. Chases overdue verifications by text. Builds donor slides by hand. Tries to read the spreadsheet without trusting it. |
| **Sees** | Rangers double-covering the same sector. Reports sitting in "Under Review" for weeks. A spreadsheet with a broken formula. |
| **Hears** | *"Sir, na-submit na."* · *"We already reported that one."* · A funder asking for hectares protected. |
| **Pains / Gains** | **Pains:** unowned backlog, duplicate assignments, unverifiable data, manual reporting, no audit trail. **Gains:** one filtered queue, a visible owner, evidence on every resolution, a one-click export. |

### 9.4 Empathy map → design decision trace

| What the empathy map revealed | Design decision made |
|---|---|
| Amina works in bursts, offline, and hates re-typing | Auto-save drafts locally; every field recoverable; report survives app kill |
| Joseph abandons long forms and distrusts silent submissions | Photo-first capture; visible "Received" confirmation; plain-language status |
| Amina has no way to know if a spot was already checked | Assignment state on every alert ("Unassigned · Assign ranger") + alert history |
| Joseph never hears back | Notification loop: Received → Verified → Action taken |
| Grace cannot defend a number she cannot trace | Verified vs detected distinction surfaced in Insights and in the export |
