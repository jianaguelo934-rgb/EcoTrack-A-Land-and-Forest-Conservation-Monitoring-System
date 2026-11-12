# PROBLEM_STATEMENT.md
> **Milestone** | Week 1 - Problem Framing, Personas & Low-Fi Wireframes
> **Status** | COMPLETE - submitted 2026-11-12
> **Read time** | 5 min

*Source: Figma file "EcoTracker - A Land and Forest Conservation Monitoring System" - node 0-1 "Low-Fi Wireframe" (46 frames, greyscale), node 7-10 "Clickable Interactive Figma Prototype" (48 frames, colour), node 50-2 "Design System" (180 components) and node 99-2 "Cover". Verified 2026-11-12.*
*Companion doc: [`PERSONAS.md`](./USER_PERSONAS.md)*

---

## 1. Product in one line

**EcoTrack** is a mobile-first monitoring system for land and forest conservation: it turns satellite detections *and* on-the-ground observations into a single, verifiable, accountable workflow — detect → verify → resolve — with offline-first field capture, role/region-scoped access, and exportable impact reporting.

Taglines and voice, verified in the Clickable Prototype canvas: *"Protect forests. Create lasting change."* (Welcome) · *"Conservation starts with an observation."* (Welcome) · *"Report what you see. Follow forest alerts."* (Welcome) · *"Protect your forest."* (Home) · *"Monitor change. Share evidence. Act together."* (Low-Fi canvas)

---

## 2. Problem statement

### 2.1 Core problem statement

> Conservation teams **cannot know, with confidence, whether a piece of forest is still there — or whether anyone is doing anything about it.**
> Satellite imagery tells them *where* forest cover changed, but not *what* changed, *how much*, or *who*. Ground truth exists (patrol notes, photos, WhatsApp messages) but it is captured on paper and personal phones, disappears in transit, and never reaches the people making funding and enforcement decisions. Between the two, alerts go unverified, evidence is lost, rangers walk the same ground twice, and the organisation cannot prove impact to funders.

### 2.2 Why now

| Shift | Effect on the problem |
|---|---|
| Near-real-time satellite/LULC detection is affordable | A high volume of *unverified* detections now exists — triage became the bottleneck, not detection |
| Cheap, rugged Android + offline-capable PWA | Field data capture no longer requires connectivity or paper logistics |
| Funders (donors, carbon/ESG buyers) demand auditable impact data | "Hectares lost" without "hectares verified and actioned" no longer qualifies |
| Community-based conservation is mainstream | New user class (low-end phones, local language, intermittent data) that paper-and-WhatsApp workflows fail completely |

### 2.3 The four sub-problems (and where the Figma design already answers them)

**P1 — Detection without verification.**
Satellite flags a canopy change; nobody knows if it is illegal logging, fire, or seasonal growth. The design encodes a state machine: `Detected → Verified → Resolved`, with *evidence* attached at each step and the note *"Only authorized rangers or admins can resolve alerts."* (Screens `Alert details`, `Resolve an alert`.)

**P2 — Field work happens off-grid.**
Rangers patrol for days without signal. The design is explicitly offline-first: *"Offline · Saved here"*, *"Saved here, not sent yet"*, per-photo upload progress (*"Last attempt: 1 of 3 photos uploaded"*), Queued/Failed states with *"Couldn't send. Your report is still saved here."*, a send-queue screen with *"Try sending again ›"*, and the hard warning *"Do not clear app storage before this report syncs."* (Screens `Report a problem`, `Saved offline`, `Send saved reports`, `Dialog · Sending reports`, `Draft report`.)

**P3 — Evidence must be captured at the moment of observation, or it is worthless.**
Location (GPS or manual), up to 6 photos, category, description, and severity are all required at capture. The report lifecycle makes the chain of custody explicit — device-side `Draft → Waiting/Queued → Ready to send → Sent`, review-side `Submitted → Reviewed → Verified` — with *"Submitted is not yet verified."* and *"Only an organization-authorized admin can review reports."* (Screens `Report a problem`, `Reports`, `Draft report`, `Report sent`, `Report details & review`, `Review a report`, `Approved report`.)

**P4 — Nobody can prioritise, own, or report on the work.**
Severity (Low/Medium/High), alert filters (*All / High / Medium / Low* plus a region filter), *Assign to me / Assign to field team*, detection source (Satellite / field report), region scoping (Region A–E), and Insights with forest loss over time + alerts by region + CSV/PDF export. (Screens `Alerts`, `Alert details`, `Forest trends`, `Settings`, `Resolve an alert`, `Dialog · Alert filters`.)

### 2.4 User pain points (ranked by severity)

| # | Pain | Evidence in design |
|---|---|---|
| 1 | **Work is lost in transit.** Photos sent over WhatsApp, evidence never reaches the system of record. | "Upload failed · Retry", "Upload interrupted · Report kept on device" |
| 2 | **Alerts queue without an owner.** Detections sit unassigned, unverified. | "Unassigned · Assign ranger" |
| 3 | **No shared picture of state.** Who checked what, what's still open, what's verified. | Alerts list, Status timeline, Sync status |
| 4 | **Field forms are too long / wrong language.** People abandon and fall back to verbal or WhatsApp reporting. | Required-field asterisks, 3 languages (English/Kiswahili/Français) |
| 5 | **GPS permission and signal fail at the worst moment.** | `Choose a location` — *"Location is unavailable"*, with manual coordinates fallback |
| 6 | **Data can't be trusted or defended.** "We saw a change" vs "here is the photo at 07:12 at 0.4, -1.7 with a description". | Before/after imagery, evidence photos, resolution notes + confirmation checkbox |
| 7 | **Impact reporting is manual and slow.** | Insights screen, Export CSV/PDF (demo) |
| 8 | **No cost of my time is visible.** | Home → "Recent updates" · "Forest monitoring activity" · "Field report activity" |

### 2.5 User needs

**Functional**
- Capture evidence offline in under 90 seconds
- See what's near me and what's open
- Know my report's state without asking anyone
- Assign work and hand it off cleanly
- Produce evidence-grade exports
- Access only my regions

**Emotional**
- *My field knowledge counts*
- *My work isn't wasted*
- *If I press submit, it will not disappear*
- *I can trust this number in front of a funder*

### 2.6 Constraints

- Offline-first; no assumption of connectivity, GPS, or camera permission.
- Low-end Android, limited storage, metered data.
- Organisation-managed access — roles and regions assigned by an org admin; admin access requires an invitation.
- Multi-region deployment (Regions A–E) with region-scoped visibility.
- Evidence must be defensible: location + timestamp + photos + notes.

### 2.7 Assumptions to validate in wireframe testing

- **A1:** Ranger prioritisation is driven by severity *and* travel distance, not severity alone.
- **A2:** Community monitors will submit only if they get visible feedback on their report.
- **A3:** Manual coordinate entry is an acceptable fallback, not just an error state.
- **A4:** A `Submitted → Verified` reviewer queue is needed for Admin — currently implied but not designed.

### 2.8 Success metrics

| Category | Metric | Target (hypothesis) |
|---|---|---|
| Speed | Detection → verified | < 72 hours median |
| Speed | Capture → server (after reconnect) | < 15 min median |
| Reliability | Sync success rate on reconnect | > 98% |
| Evidence quality | Reports submitted with GPS + ≥1 photo | > 85% |
| Coverage | Weekly active rangers per region | +40% in pilot |
| Coverage | Weekly active community monitors | > 60% of invited |
| Accountability | Alerts with an owner within 24h | > 90% |
| Impact | Hectares lost → hectares verified & actioned | tracked as a ratio |
| Trust | Reports verified (Submitted → Verified) | trending upward, no manual backfill |

### 2.9 Non-goals (v1)

- Public/citizen reporting portal with a moderation queue.
- Payments, grants disbursement, or carbon-credit trading.
- Building our own satellite/LULC pipeline — assume detections are ingested from an external source.
- IoT/sensor/drone hardware integration.
- Real-time chat between rangers — WhatsApp remains the tool for that.

### 2.10 Design principles to carry into the low-fi wireframe

1. **Offline is the default, not an error state.** Every capture path must be completable with zero bars.
2. **Evidence over opinions.** Every alert and report resolves to photos + coordinates + notes.
3. **Show the state of the work.** Draft / Queued / Failed / Submitted / Verified and Detected / Verified / Resolved must be visible at a glance.
4. **Never lose data.** Local-first persistence, visible queue, safe retry, explicit "saved on this device".
5. **Least effort for the field, most control for the office.** Field = a usable report in a few taps. Office = filters, assignment, export.
6. **Permission follows role and region**, and the UI must explain it (*"Your organization controls role and region access."*).
7. **Plain language, local language, and honest empty states** — keep the design's integrity here (*"Time unavailable"*, *"Last updated: unavailable"*).

---

## 3. Problem → Screen Traceability

> Screen names below are the **current** names in the Clickable Interactive Figma Prototype canvas (verified 2026-11-11). The prototype was rebuilt after the first pass of these documents, so the older numeric names (01–28) no longer exist.

| Problem | Prototype screens that answer it | Status |
|---|---|---|
| P1 Detection without verification | `Alert details`, `Resolve an alert`, `Dialog · Assign ranger` | Covered |
| P2 Off-grid field work | `Report a problem`, `Saved offline`, `Send saved reports`, `Dialog · Sending reports`, `Draft report`, `Settings` | Covered |
| P3 Evidence capture & chain of custody | `Report a problem`, `Reports`, `Draft report`, `Choose a location`, `Report sent`, `Report details & review` | Covered |
| P4 Prioritise, own, report on work | `Home`, `Alerts`, `Alert details`, `Forest trends`, `Resolve an alert`, `Dialog · Alert filters` | Covered |
| Review & verification authority | `Reports to review`, `Review a report`, `Approved report`, `Dialog · Review access` | **Covered** — the verification queue now exists |
| Access control (role + region) | `Sign in` (role tabs), `Settings` (Assigned regions), `Create account`, `Dialog · Review access` | Covered — admin access is gated at the action, not by a separate admin console |
| Field efficiency for monitors | `Report a problem`, `Home` (task cards) | Partial — Home is task-adaptive, but there is no monitor-specific variant |
| Offline map usability | `Dialog · Map connection`, `Dialog · Loading map`, `Dialog · Map layers and recovery`, `Send saved reports` (Offline storage) | **Covered** — map failure and recovery states now designed |
| Draft lifecycle & data safety | `Draft report`, `Dialog · Unfinished report`, `Dialog · Delete draft` | **Covered** — added in the rebuild |

### 3.1 Report lifecycle, as actually modelled in the prototype

The prototype now shows **two** related chains, and the documents previously described only one:

| Chain | States shown in the prototype | Where |
|---|---|---|
| **Alert** | `Detected → Verified → Resolved` | `Alert details` status timeline |
| **Report, device-side** | `Draft` → `Waiting` / `Queued` → `Ready to send` → `Sent` · with `Failed` + `Couldn't send. Your report is still saved here.` | `Reports` tabs **On device / Sent / Approved**, `Send saved reports` |
| **Report, review-side** | `Submitted → Reviewed → Verified` | `Approved report` → *Verification history* |
| **Report, outcome-side** | `Submitted` ≠ `Verified` — *"Submitted is not yet verified."* | `Report sent` |

**Every doc, pitch slide, and demo script must use these exact words.** The old framing of a single `Draft → Queued → Failed → Submitted → Verified` chain conflated the device queue with the review workflow; the prototype separates them, and the separation is the stronger story.

---

## 4. UN SDG Alignment

**Primary track: SDG 15 — Life on Land** (as registered on the Master Tracker).

| SDG 15 target | How EcoTrack serves it |
|---|---|
| **15.1** Conserve and restore terrestrial ecosystems, and halt the loss of biodiversity | Continuous forest-cover % and area-monitored tracking; protected-area map layer; before/after imagery on every area |
| **15.2** Promote sustainable forest management and reverse the rate of deforestation | *Core of the product.* Illegal logging, fire, and encroachment detection → verification → resolution, with hectare loss quantified per area |
| **15.5** Reduce degradation of natural habitats and reverse the decline of biodiversity | Encroachment and wildlife report categories; loss (ha) and forest-cover trend per monitored area |
| **15.8** Integrate conservation into national and local planning and hold institutions accountable | Organisation-managed roles and regions; an explicit verification gate; an audit trail of who did what, when, and with what evidence |
| **15.a** Mobilize significant financial resources for forests and biodiversity | Donor-grade export (CSV/PDF) of loss (ha), alerts by region, and **verified vs merely detected** figures |
| **15.b** Promote locally-led participatory management of natural resources | The Community Monitor role — community-based forest observation with evidence-grade capture and feedback |

**Secondary tracks (state as supporting, not primary):**

| Track | How EcoTrack serves it |
|---|---|
| **SDG 13.1 / 13.3** Climate Action | Forest-loss-over-time is a climate indicator; community monitors as local climate stewards |
| **SDG 16.6** Effective, accountable institutions | Verification gate + resolution notes + evidence + audit history = accountable enforcement, not just awareness |

**One-line pitch alignment:** *"EcoTrack turns deforestation from an unverified satellite anomaly into a verified, owned, and resolved conservation action — the operational layer for SDG 15."*

---

## 5. Differentiation & Exclusivity Compliance

> Required by the hackathon policy: *"Multiple teams may target the same UN SDG track, provided their specific problem statements, target personas, and primary feature sets are distinctly different."*
> Registering team: **F-8 — EcoTrack, SDG 15**. Closest adjacent project: **F-4 — GreenPulse, SDG 13** (registered earlier; EcoTrack registered later, so EcoTrack carries the burden of demonstrating distinctness).

### 5.1 The shared surface (acknowledge it, then separate)

Both products use the generic pattern *report an issue with photo + location → track status → admin reviews → map*. Every student team in this hackathon is allowed one "report an issue" screen. **One shared screen is not a duplicate concept.** The concept is the domain, the actor model, the state machine, and the primary feature set — and those are genuinely different.

### 5.2 Head-to-head differentiation

| Dimension | GreenPulse (F-4) | **EcoTrack (F-8)** |
|---|---|---|
| SDG | 13 — Climate Action | **15 — Life on Land** |
| Domain | Municipal waste, drainage, flooding, litter, cleanup drives | **Forest cover change: illegal logging, fire, encroachment, wildlife** |
| Detection source | Human reports only | **Satellite detections + field reports (dual-channel)** |
| Core state machine | Submitted → Under Review → In Progress → Resolved | **Alerts: Detected → Verified → Resolved. Reports: Draft → Queued → Failed → Submitted → Verified** |
| Offline behaviour | None — requires connection | **Offline-first: local drafts, queued uploads, per-photo progress, failed-upload retry, sync center** |
| Triage & ownership | Status filters only | **Severity (Low/Med/High) + assignment to ranger/field team + "Unassigned" queue** |
| Verification | Soft "Under Review" state | **Hard verification gate, mandatory resolution notes + evidence, and a recorded alert history** |
| Access model | Flat: resident vs admin | **Organisation-managed roles (Ranger / Community Monitor / Admin) + region-scoped visibility across Regions A–E** |
| Actors | 2 personas (Resident, Admin) | **4 personas (Ranger, Community Monitor, Admin, Donor/Grant Monitor)** |
| Measurement | Temperature / rainfall / air quality (sample data) | **Forest cover %, loss (ha) over time, alerts by region, verified vs detected, exportable CSV/PDF** |
| Engagement model | Community events — cleanups, tree planting, climate tips | **Professional fieldwork: patrol, evidence capture, alert ownership, resolution** |
| Locality | City of Mati, Davao Oriental | **Multi-region deployment with regional scoping** |

### 5.3 Primary feature set we claim (and GreenPulse does not have)

1. **Satellite detection ingestion** — the product reacts to a change on Earth, not only to a user submitting a form. This is the concept-defining feature.
2. **Severity triage and alert ownership** — "Unassigned · Assign ranger" means work is routed, not just logged.
3. **Offline-first capture with a visible sync queue** — the field reality GreenPulse ignores entirely.
4. **Verification and audit trail** — evidence-grade, defensible, funder-acceptable.
5. **Region-scoped access control** — multi-region, organisation-managed permissions.
6. **Hectare-level impact quantification and export** — forest loss (ha) and alerts by region, not air-quality sample readings.

### 5.4 Language to use in the pitch

> *"GreenPulse is a community awareness-and-engagement app for municipal environmental issues. EcoTrack is a monitoring-and-enforcement system for forest cover loss: it ingests satellite detections, verifies them on the ground by people who are often offline, assigns them to rangers, and produces donor-grade evidence that hectares were actually protected."*

### 5.5 What we should NOT do

- Do not claim "the only environmental monitoring app" — GreenPulse owns that wording.
- Do not add community cleanup events, tree-planting challenges, or climate-tip content. That is GreenPulse's territory and would dilute our differentiation.
- Do not use the phrase "report an issue" as our core value proposition. Lead with *detection → verification → resolution*.
- Do not use temperature/rainfall/air-quality metrics as our headline analytics. Our headline is **forest cover loss (ha) and verified action taken**.

---

## 6. Localisation Note (important for realism)

The current personas and copy use **Kiswahili / Français** and generic **Region A / Region B**, which reads as an African deployment. The team is a Philippine school (DOrSU, Maddela, Isabela) and the adjacent competitor is set in **Davao Oriental** — an instructor will read the app as unmoored from a real Philippine context.

**Recommended swap (apply before submission):**

| Current | Recommended |
|---|---|
| Region A / B / C–E | **Isabela, Cagayan Valley** + named LGUs (e.g., Maddela, Cabagan, San Pablo, Tumauini) |
| Forest Ranger | **Bantay Gubat / CFPM forest monitor** (Community Forest Protection and Monitoring Programme — a real Philippine DENR institution) |
| Community Monitor | **Barangay-based CFPM member / sitio forest guardian** |
| Illegal logging, fire, encroachment | Same — keep, they are correct for Sierra Madre & Cagayan Valley |
| Kiswahili, Français | **English, Filipino, Ilocano** (or English, Filipino, Cagayan Valley dialect) |
| "ha" units | Keep hectares; add "hectares of Cagayan Valley forest" context |
| Admin persona (NGO Program Director) | **DENR PENRO / CENRO officer** or NGO conservation program head |

---

## 7. How Might We — Problem Statement

> Required by the Week 1 checkpoint: *"Selected UN SDG Track and formulated specific, localized 'How Might We' problem statement."* This is the sentence that the whole product defends against.

### 7.1 Primary HMW — the product thesis

> **How might we help rangers and community monitors verify and act on forest-cover change in their assigned regions — even with no connectivity — so that every hectare lost has an owner, evidence, and a recorded resolution?**

### 7.2 Supporting HMWs — one per persona

| Persona | How Might We |
|---|---|
| **Amina** (Ranger) | *How might we turn a satellite pin on a map into a complete, verified field report in under 90 seconds — with no signal — so that my patrol effort is not wasted?* |
| **Joseph** (Community Monitor) | *How might we make a forest incident reportable in under 60 seconds, in the user's own language, on a low-end phone with no data — so that reporting becomes easier than sending a WhatsApp photo?* |
| **Dr. Grace** (Admin) | *How might we convert scattered alerts and unverified reports into a defensible, exportable record of hectares protected — so that enforcement and funding follow evidence, not assumption?* |
| **Daniel** (Donor, indirect) | *How might we distinguish hectares merely *detected* from hectares *verified and actioned* — so that a funder can tell a rumour from a result?* |

### 7.3 Localised HMW — the Philippine version (recommended for submission)

> **How might we help Bantay Gubat and CFPM volunteers in Isabela verify satellite-flagged clearing across Cagayan Valley forest — with no signal in the field — so that illegal logging is confirmed by someone on the ground before it ever reaches the CENRO?**

This version is what should appear in the pitch deck (Slide 3) and the Weekly Progress Report, because the rubric awards 18–20 points in Criterion 3 for a *"compelling, localized problem definition"* and only 10–14 for a *"generic problem statement."*

### 7.4 HMW → Design principle → Screen

| HMW | Design principle that answers it | Screens that prove it |
|---|---|---|
| Verify forest change with no connectivity | Offline is the default, not an error state | 08, 17, 18, 26, 12 |
| Every hectare lost has an owner, evidence, resolution | Evidence over opinions; show the state of the work | 06, 07, 19 |
| Reportable in 60 seconds, in the user's language | Least effort in the field | 08, 13, 20 |
| Defensible, exportable record of hectares protected | Never lose data; show the state of the work | 09, 10, 16, 22–25 |

This swap costs about 30 minutes and materially raises perceived authenticity with a Philippine instructor.
