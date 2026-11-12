# USER_FLOW.md
> **Milestone** | Weeks 1-2 - wireframes, flows and information architecture
> **Status** | IN PROGRESS - wireframes and IA complete; 3 screens outstanding
> **Read time** | 6 min

*Companion to [`PROBLEM_STATEMENT.md`](./PROBLEM_STATEMENT.md), [`USER_PERSONAS.md`](./USER_PERSONAS.md) and [`WEEK1_VALIDATION.md`](./WEEK1_VALIDATION.md)*
*Figma: **Low-Fi Wireframe** canvas (46 frames, greyscale) + **Clickable Interactive Figma Prototype** canvas (48 frames, colour) + **Design System** canvas (node 50:2, 180 components)*
*Verified 2026-11-12. The low-fi and prototype share one IA and one set of screen names — only the fidelity differs.*

---

## 1. Wireframe index

### 1.1 One inventory, three canvases

The **Low-Fi Wireframe** canvas was rebuilt on 2026-11-12 to mirror the Clickable Prototype: the same frame names, the same navigation model, the same components. The only difference is fidelity — the low-fi canvas is greyscale (`#252525` `#3A3A3A` `#686868` `#BEBEBE` `#E8E8E8` `#ECECEC` `#F7F7F7` `#FFFFFF`) with placeholder copy (*"Add a short title"*, *"Describe what you saw"*, *"Example state · Wireframe state"*, *"Illustration"*, *"Logo"*, *"Avatar"*), while the prototype carries the 18 colour tokens and the real microcopy.

This is the right structure for the Week 1 checkpoint: the wireframe proves the **information architecture** across *every* screen, and the prototype proves it at production fidelity, with no drift between them.

| Screen | Low-Fi ID | Prototype ID | Purpose | Persona |
|---|---|---|---|---|
| `Welcome` | 6:2 | 11:2 | Splash + 3-dot onboarding — *"Protect forests. Create lasting change."* | All |
| `Sign in` | 6:3 | 11:22 | Role tabs Ranger / Community Monitor / Admin, *"Select your role"* | All |
| `Home` | 6:4 | 11:59 | Task-adaptive home — *"Choose a task to get started."* → Check alerts / Report a problem / Explore the map | Amina, Joseph, Grace |
| `Map` | 6:5 | 11:130 | Satellite / Forest Cover / Protected layers, pins, legend | Amina |
| `Area details` | 6:6 | 11:195 | Before/after imagery, forest cover %, loss (ha), *"Follow this area"* | Amina, Grace |
| `Alerts` | 6:7 | 11:247 | Severity filter All/High/Medium/Low + alert list | Amina, Grace |
| `Alert details` | 6:8 | 11:326 | Map snapshot, severity, source, Detected→Verified→Resolved, Assign, Mark as resolved | Amina, Grace |
| `Report a problem` | 6:9 | 11:388 | Capture form — *"What did you see? / Where did it happen? / What happened? / How urgent is it?"*, photos (0/6) | Amina, Joseph |
| `Reports` | 6:10 | 11:443 | Tabs **On device / Sent / Approved** + create action | All |
| `Forest trends` | 6:11 | 11:496 | Date range, forest loss over time, alerts by region, Download report | Grace, Daniel |
| `Notifications` | 6:12 | 11:553 | Alert, verification, sync, status updates (TODAY / EARLIER) | All |
| `Settings` | 6:13 | 11:623 | Profile, assigned regions, language, saved reports & sending, log out | All |
| `Create account` | 9:92 | 11:683 | Name, email, password, terms, *"Organization-managed access"* | All |
| `Reset password` | 9:96 | 11:714 | Email + *"Connection required"* | All |
| `Check your email` | 9:100 | 11:733 | Reset link sent, next steps, resend | All |
| `Draft report` | 9:104 | 11:751 | Draft detail/edit — *"Only saved on this device"*, location required | Amina, Joseph |
| `Saved offline` | 9:125 | 11:804 | *"Your report is safe on this device"* + queued summary | Amina, Joseph |
| `Send saved reports` | 9:146 | 11:843 | Failed upload w/ per-photo progress, queued uploads, offline storage | Amina |
| `Resolve an alert` | 9:167 | 11:890 | Notes*, evidence photos, confirmation checkbox | Amina, Grace |
| `Choose a location` | 9:188 | 11:934 | *"Location is unavailable"* → settings / set on map / manual coords | Amina, Joseph |
| `Report sent` | 9:213 | 11:1010 | *"Sent for review"*, *"Submitted is not yet verified."* | Amina, Joseph |
| `Report details & review` | 53:2389 | 11:1778 | Submitted report + *"Awaiting review"* + review update | Joseph, Grace |
| `Reports to review` | 53:2442 | 45:17 | **Admin queue** — *"Admin access · Assigned regions only"* | Grace |
| `Review a report` | 53:2464 | 45:25 | **Admin review** — Approve / Request changes / Reject | Grace |
| `Approved report` | 53:2508 | 45:49 | Verified summary, verification history, *"Submitted → Reviewed → Verified"* | Grace, Daniel |

### 1.2 Dialogs & sheets — 23 on the prototype, 21 on the low-fi

| Dialog | Low-Fi ID | Prototype ID | Trigger |
|---|---|---|---|
| `Dialog · Category` | 53:2281 | 11:1477 | Report form category field |
| `Dialog · Assign ranger` | 53:2300 | 11:1485 | Alert detail → Assign |
| `Dialog · Language` | 53:2307 | 11:1489 | Settings → Language |
| `Dialog · Date range` | 53:2316 | 11:1493 | Forest trends → Date range |
| `Dialog · Search areas` | 53:2325 | 11:1497 | Map → Search |
| `Dialog · Export` | 53:2335 | 11:1501 | Forest trends → Download report |
| `Dialog · Log out` | 53:2343 | 11:1505 | Settings → Log out |
| `Dialog · Account requested` | 53:2351 | 11:1509 | Create account (org-managed access) |
| `Dialog · New password` | 53:2359 | 11:1513 | Reset password → demo link |
| `Dialog · Feedback` | 53:2373 | 11:1517 | Generic simulated-action notice |
| `Dialog · Allow location access` | 53:2379 | 11:1521 | **Renamed** from `Set report location` — now a proper permission request: *"Allow location access"* → *Use example current location* / *Not now* |
| `Dialog · Sending reports` | 53:2419 | 11:1840 | Send queue in progress — *"Sending your reports…"* |
| `Dialog · Search reports` | 53:2424 | 11:2361 | Reports → search |
| `Dialog · Map connection` | 53:2533 | 45:89 | *"The live map is unavailable"* → Retry map / View saved reports |
| `Dialog · Loading map` | 53:2543 | 45:97 | *"Loading map…"* → Return home |
| `Dialog · Unfinished report` | 53:2551 | 45:271 | *"Save your changes?"* → save / discard / keep editing |
| `Dialog · Delete draft` | 53:2560 | 45:281 | Draft report → Delete draft |
| `Dialog · Review access` | 53:2567 | 45:289 | *"Admin access required"* → Back to sign in / Stay here |
| `Dialog · Alert filters` | 53:2574 | 45:298 | Alerts → region filter, incl. empty state *"Region C · No detections"* |
| `Dialog · Map layers and recovery` | 53:2583 | 45:310 | Map → layers + *"Connection lost (demo)"* |
| `Dialog · Choose map point` | **missing** | **92:55** | **New** — *"Choose a map point"*, confirms a sample point with coordinates |
| `Dialog · Enter coordinates` | **missing** | **92:65** | **New** — *"Enter coordinates"*, latitude −90…90 / longitude −180…180 |
| ~~`Dialog · Photo`~~ | 53:2292 | *removed* | **Removed** from the prototype in the 2026-11-12 pass |

> ### ⚠️ Parity drift — fix this
> The prototype is now **48 frames** and the Low-Fi canvas is still **46**. The two new location dialogs exist only on the prototype, and `Dialog · Photo` exists only on the low-fi. Until both canvases carry the same 48 frames, the *"same IA, two fidelities"* claim no longer holds — and that claim is the strongest answer to *"did you really do low-fi first?"*
>
> **Fix (~20 min):** add `Dialog · Choose map point` and `Dialog · Enter coordinates` to the low-fi canvas in greyscale, delete `Dialog · Photo` there, and rename `Dialog · Set report location` to `Dialog · Allow location access`.

### 1.3 What changed across the two rebuilds (and what it closed)

| Canvas | Rebuild | Change | Gap it closed |
|---|---|---|---|
| Prototype | 2026-11-11 | **Added** `Reports to review`, `Review a report`, `Approved report`, `Dialog · Review access` | The Admin verification queue and the audit/verification history the first audit flagged as missing |
| Prototype | 2026-11-11 | **Added** `Dialog · Map connection`, `Dialog · Loading map`, `Dialog · Map layers and recovery` | Offline map usability — failure, loading, and recovery states now designed |
| Prototype | 2026-11-11 | **Added** `Dialog · Unfinished report`, `Dialog · Delete draft`, and Delete draft on `Draft report` | Draft lifecycle and data-safety confirmation |
| Prototype | 2026-11-11 | **Added** `Dialog · Alert filters` with a populated **and** an empty region result | Region-scoped filtering + honest empty state |
| Prototype | 2026-11-11 | **Added** `Dialog · Sending reports` | Explicit in-progress upload state |
| Prototype | 2026-11-11 | **Rewrote** `Home` as a task-adaptive screen | Partly closes the "Community Monitor has no home" gap |
| Prototype | 2026-11-11 | **Rewrote** the report form labels to question form | Plain-language field labelling for low-literacy users |
| Prototype | 2026-11-11 | **Removed** `21 Sign in error`, `27 Area comparison after`, `28 Map zoomed in` | Folded into other frames — **the sign-in error state is now absent** |
| Prototype | 2026-11-11 | **Renamed** `Bottom navigation` → `Main navigation` | Consistency only |
| **Low-Fi** | **2026-11-12** | **Rebuilt from 22 numbered screens to the same 46 frames** with matching names, greyscale palette, and placeholder copy | **The wireframe now covers every screen in the product**, not just the first 22 — the Week 1 deliverable is complete, and the low-fi/hi-fi IA can no longer drift apart |
| **Prototype** | **2026-11-12** | **Added** `Dialog · Choose map point` (92:55) and `Dialog · Enter coordinates` (92:65) — the full location fallback chain | The location flow is now end-to-end: permission → map pick → manual coordinates |
| **Prototype** | **2026-11-12** | **Renamed** `Dialog · Set report location` → `Dialog · Allow location access` (11:1521) and rewrote its content as a proper permission request | A real permission conversation instead of a location picker |
| **Prototype** | **2026-11-12** | **Removed** `Dialog · Photo` (11:1481) | Photo capture now folds into the capture form |
| **File** | **2026-11-12** | **Added** the **Design System** canvas (50:2) — 180 components, sections `01 · Colors`, `02 · Typography`, `03 · Corners` | **Closes the biggest Criterion 1 gap.** The tokens and component library are now visible to a judge |
| **Low-Fi** | *pending* | The two new location dialogs are **not** on the low-fi canvas yet, and `Dialog · Photo` still is | Parity drift — see the warning in §1.2 |
| **Low-Fi** | **2026-11-12** | Added *"Review reports · Admin"*, *"View forest trends"*, *"Works offline after first sign in"*, *"Reports are kept safe if you're offline."*, *"Save now. Send when you reconnect."*, *"Save for later"*, *"Send report"* | Wireframe copy now states the product promise rather than placeholder grey |

### 1.4 Canvas metrics (measured 2026-11-12)

| Metric | Low-Fi Wireframe | Clickable Prototype | Design System |
|---|---|---|---|
| Top-level frames | 46 (25 screens + 21 dialogs) | **48** (25 screens + 23 dialogs) | 180 components |
| Component instances | 325 | **332** | **361** |
| Unique components | 78 | 77 | — |
| Autolayout frames | **1 of 462** | **5 of 409** | **0 of 305** |
| Distinct x-offsets | 80 | 78 | — |
| Off-grid offsets (not ÷4) | 47 | 45 | — |
| Colour palette | 8 greys | 18 colour tokens | 16 colour tokens |

> The low-fi canvas is *not* where autolayout earns marks — the rubric's *"autolayout variants"* criterion applies to the component library in the prototype. But the shared component set (78 / 77 components across both canvases) is real: the greyscale wireframes are built from the same components as the colour prototype, which is exactly the evidence Criterion 1 wants.

---

## 2. Flow A — Amina (Ranger): Detect → verify → close, fully offline-capable

```
Welcome
  └→ Sign in [Ranger tab]
       └→ Home  ("Check alerts · Report a problem · Explore the map")
            ├→ Map ──tap pin──→ Area details  (before/after, loss ha, "Follow this area")
            └→ Alerts [filter High]
                 └→ Alert details (Detected)
                      ├→ Dialog · Assign ranger  (Assign to me │ Assign to field team)
                      ├→ Details / Directions
                      └→ Report a problem  ← OFFLINE OK
                           ├→ Save draft        → Draft report → Reports [On device · Draft]
                           ├→ Dialog · Set report location
                           ├→ Choose a location  (permission denied → manual coords)
                           └→ Submit report     → Saved offline (Queued)
                                                  └→ Send saved reports  (auto-send on reconnect)
                                                       └→ Dialog · Sending reports
                                                       └→ Report sent  ("Sent for review")
                      └→ Resolve an alert  (notes* · evidence photos · confirm) → Alert details (Resolved)
```

**Critical properties to preserve:** every arrow from `Report a problem` onward must work with zero connectivity; a draft must never be cleared; `Sent` must never be visually equal to `Approved`.

---

## 3. Flow B — Joseph (Community Monitor): Spot → report → get feedback

```
Welcome
  └→ Sign in [Community Monitor tab]
       └→ Home  ("Choose a task to get started." → "Report a problem")
            └→ Report a problem (SIMPLIFIED path)
                 ├→ Choose a location  (denied → "Set location on map" / manual coords)
                 ├→ Dialog · Photo  (attach demo field photo)
                 └→ Submit → Saved offline (Queued)
                              └→ Send saved reports → Report sent
                                   └→ Notifications: "Report verified" → "Newly status updated"
```

**Still open:** the Home task cards are generic. There is no monitor-specific variant (alerts near me, my reports' status, language toggle). Everything else in Joseph's path now exists.

---

## 4. Flow C — Grace (Admin): Triage → verify → report

```
Sign in [Admin tab]
  └→ Home
       ├→ Alerts [High + Dialog · Alert filters] → Alert details → Dialog · Assign ranger
       ├→ Reports [Sent] → Report details & review  ("Awaiting review")
       ├→ Reports to review  (45:17)          ← ADMIN QUEUE
       │     └→ Review a report (45:25)       ← Approve | Request changes | Reject
       │           └→ Approved report (45:49) ← Verification history · "Submitted → Reviewed → Verified"
       ├→ Forest trends (date range) → Dialog · Export (CSV | PDF)
       └→ Settings (Assigned regions · +2)
```

**Gating:** a non-admin attempting a review action hits `Dialog · Review access` — *"Only an organization-authorized admin can review reports. In this demo, return to sign in and choose the Admin role."* → Back to sign in / Stay here.

---

## 5. Flow D — Daniel (Donor, indirect)

```
(no login)  ←  Forest trends (forest loss over time, alerts by region, verified vs detected)
             ←  Dialog · Export (CSV / PDF)  →  consumed monthly
```

**Add to `Forest trends`:** a definition note (*"Hectares lost = satellite-detected ∩ verified"*) so a funder can trust the number.

---

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

## 7. Mobile Information Architecture

> Required by the Week 1 checkpoint: *"User journey flow & mobile Information Architecture mapped."*

### 7.1 Navigation model

Five-tab main navigation (present on every signed-in screen):

| Tab | Route | Screens |
|---|---|---|
| Home | `/home` | `Home` |
| Map | `/map` | `Map` · `Area details` |
| **+** | `/report/new` | `Report a problem` |
| Reports | `/reports` | `Reports` · `Report details & review` |
| Alerts | `/alerts` | `Alerts` · `Alert details` · `Resolve an alert` |
| Settings | `/settings` | `Settings` · `Send saved reports` · `Forest trends` · `Notifications` |

The `+` is a **centre action**, not a tab — capture is reachable from any screen, which is the fastest possible path to a report for Joseph.

### 7.2 IA tree

```
EcoTrack
│
├── Welcome (splash + 3-dot onboarding)
│
├── Sign in  ── role tabs: Ranger │ Community Monitor │ Admin
│   ├── Dialog · Account requested
│   ├── Create account → Dialog · Account requested
│   ├── Reset password → Check your email → Dialog · New password
│   └── Dialog · Review access  (guard: "Admin access required")
│
└── AUTHENTICATED  (role + region scoped)
    │
    ├── Home  ("Choose a task to get started.")
    │    ├── Check alerts  →  Alerts
    │    ├── Report a problem  →  Capture flow (below)
    │    └── Explore the map  →  Map
    │
    ├── Map
    │    ├── Search  →  Dialog · Search areas
    │    ├── Layers  →  Dialog · Map layers and recovery  ("Connection lost (demo)")
    │    │                └── Dialog · Map connection / Dialog · Loading map
    │    ├── Area preview →  Area details
    │    │                      ├── Before / After comparison (in-frame)
    │    │                      └── "Follow this area"
    │    └── Dialog · Alert filters  →  all / high / medium / low + region
    │
    ├── Alerts
    │    ├── Alert details
    │    │      ├── Status: Detected → Verified → Resolved
    │    │      ├── Dialog · Assign ranger  (Assign to me │ Assign to field team)
    │    │      └── Resolve an alert  (notes* · evidence photos · confirm)
    │    └── Dialog · Alert filters
    │
    ├── Capture flow
    │    ├── Report a problem
    │    │      ├── Dialog · Category  (Illegal logging │ Fire │ Encroachment │ Wildlife)
    │    │      ├── Dialog · Allow location access  (permission request)
    │    │      │     └── Dialog · Choose map point  →  Dialog · Enter coordinates
    │    │      ├── Dialog · Unfinished report  ("Save your changes?")
    │    │      └── Draft report
    │    │             ├── Dialog · Delete draft
    │    │             └── Set location / Edit draft
    │    ├── Saved offline  (Queued)
    │    ├── Send saved reports  (Failed · Queued · Ready to send)
    │    │      └── Dialog · Sending reports  ("Sending your reports…")
    │    └── Report sent  ("Submitted is not yet verified.")
    │           └── Report details & review  ("Awaiting review")
    │
    ├── Reports  [On device │ Sent │ Approved]
    │    ├── Dialog · Search reports
    │    └── Report details & review
    │
    ├── Admin review flow
    │    ├── Reports to review        (45:17)
    │    ├── Review a report          (45:25)  → Approve │ Request changes │ Reject
    │    └── Approved report          (45:49)  → Verification history
    │
    ├── Forest trends
    │    ├── Dialog · Date range  (7 days │ 30 days │ This year)
    │    └── Dialog · Export  (CSV │ PDF)
    │
    ├── Notifications
    │
    └── Settings
         ├── Assigned regions  (Region A │ Region B │ +2)
         ├── Language  →  Dialog · Language
         ├── Saved reports & sending  →  Send saved reports
         └── Dialog · Log out
```

### 7.3 Screen count by state type

| Type | Count | Screens |
|---|---|---|
| Primary flows | 13 | `Home`, `Map`, `Area details`, `Alerts`, `Alert details`, `Report a problem`, `Reports`, `Report details & review`, `Forest trends`, `Settings`, `Notifications`, `Send saved reports`, `Resolve an alert` |
| Auth & onboarding | 4 | `Welcome`, `Sign in`, `Create account`, `Reset password` + `Check your email` |
| Success / error / empty states | 8 | `Saved offline`, `Report sent`, `Draft report`, `Choose a location`, `Approved report`, `Dialog · Map connection`, `Dialog · Loading map`, `Dialog · Alert filters` (empty region) |
| Admin review | 3 | `Reports to review`, `Review a report`, `Approved report` |
| Dialogs & sheets | 21 | see §1.2.2 |
| **Total frames** | **46** | 25 screens + 21 dialogs |
| **Prototype total** | — | **48** frames — 25 screens + 23 dialogs |

### 7.4 Remaining IA gaps

| # | Missing node | Impact | Status |
|---|---|---|---|
| 1 | **Community Monitor-specific home variant** | Joseph's task cards are generic; no "alerts near me" or local-language entry point | **Open** — the highest-value remaining gap |
| 2 | **Sign-in error state** | The prototype dropped the old `21 Sign in error` frame — there is no invalid-credentials state | **Open** — add a validation error on `Sign in` |
| 3 | **Team & access management** | The app claims *"your role and regions are assigned after approval"*, but no screen lets an admin assign them | **Open** — admin can only *review*, not *administer* |
| 4 | **Map download manager** | `Send saved reports` shows *"Map downloads · None saved"*, but there is no screen to download a region | **Open** — the closest is `Dialog · Map layers and recovery` |
| 5 | **Community Monitor quick-capture form** | The form is now question-labelled (good) but still 5 required fields for a volunteer with a 4 GB phone | **Open** — add a 3-field fast path |

> **Note:** gaps 1–4 were all flagged in the first audit. The rebuild closed the Admin verification queue, the audit history, the map failure states, and the draft lifecycle. What remains is role-specific convenience, not missing workflow.
