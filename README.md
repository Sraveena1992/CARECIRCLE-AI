<div align="center">

# ✺ CARECIRCLE AI
### Better days, together.
**Every dose matters. Every elder deserves a circle of care.**

An elder-first, shared care workspace for daily medication routines, appointments and caregiver coordination.

[![Live Demo](https://img.shields.io/badge/OPEN-LIVE%20DEMO-117C70?style=for-the-badge)](https://carecircle-ai-0og5.onrender.com)
[![Source](https://img.shields.io/badge/EXPLORE-GITHUB-102D37?style=for-the-badge)](https://github.com/Sraveena1992/CARECIRCLE-AI)

![Catalyst 2026](https://img.shields.io/badge/Catalyst-2026-8B5CF6) ![Solo project](https://img.shields.io/badge/Build-Solo-0E7490) ![Node 18+](https://img.shields.io/badge/Node.js-18%2B-43853D) ![Prototype](https://img.shields.io/badge/Status-Demo%20prototype-F59E0B)

**💊 Medication routines · 📅 Appointments · 👥 Care circle · 📊 Adherence insights · ♿ Accessible design**

</div>

---

## 🌟 The vision

Older adults often manage multiple prescriptions, appointments and helpers. A list of reminders alone does not give everyone a shared picture of what has happened, what is coming up, and where support is needed.

**CareCircle AI** explores a more human-centered approach: a clear daily dashboard for the older adult, with a shared fictional care record that a caregiver can review. The elder remains central to every decision.

> **Important:** This is a **fictional hackathon demonstration**, not a medical device or production healthcare service. Never upload real patient data, rely on it for medication decisions, or interpret its rule-based insights as medical advice. Despite the project name, the current implementation **does not integrate a generative AI model**.

## 🖥️ Explore the experience

**[Launch the interactive demo →](https://carecircle-ai-0og5.onrender.com)**

The live demo includes a welcome/login experience, dashboard, medications, appointments, care-circle view and insights. Free hosting may take time to wake up after inactivity.

| Area | Implemented demonstration |
|:--|:--|
| 🏡 **Overview** | At-a-glance medication status and upcoming appointments |
| 💊 **Medications** | Add a schedule, deactivate a medication, log a dose as taken or skipped |
| 🛑 **Duplicate prevention** | A dose can only be logged once per medication per day |
| 📅 **Appointments** | Add and remove fictional appointments |
| 👥 **Care circle** | Switch between two predefined elder/caregiver demo identities |
| 📈 **Insights** | Calculated dose totals and a clearly labeled rule-based summary |
| 🔔 **Awareness** | In-app upcoming/missed dose and appointment indicators when state is requested |
| 🔐 **Access** | Demo passcode login, session cookie and basic failed-login throttling |
| 📱 **Interface** | Responsive layout with prominent controls and readable text |

### 🎭 Fictional demo personas

| Role | Account | Demo passcode |
|:--|:--|:--|
| 👵 Margaret — Elder | `elder` | `123456` |
| 🤝 Alex — Caregiver | `caregiver` | `654321` |

**These passcodes are public only because the accounts and data are fictional.** They must not be reused for real accounts.

## 🎬 Suggested 90-second demo

1. **Welcome (0–15s):** Open the live app and sign in as Margaret.
2. **Daily overview (15–30s):** Show today's scheduled medicines and the upcoming appointment.
3. **Record care (30–50s):** Mark a fictional dose as taken; show the updated count. Attempting the same dose twice is rejected.
4. **Coordinate (50–70s):** Add a fictional appointment and inspect Care insights.
5. **Shared view (70–90s):** Sign out, sign in as Alex and demonstrate the same fictional care circle.

*Demo results depend on the current stored demonstration data. Reset the demo data before recording if necessary.*

## 🧠 What makes the approach different?

**A care circle, not just a reminder list.** The interface brings routines, recorded actions, appointments and caregiver context together.

**Evidence of an action, not an assumption.** The app distinguishes scheduled doses from doses explicitly recorded as taken or skipped. It does not claim an unrecorded dose was consumed.

**Human-centered safeguards.** The rule-based summary advises checking with a qualified professional rather than automatically changing treatment.

**Transparent prototype boundaries.** Missing production capabilities are documented rather than presented as completed integrations.

## 🏗️ Architecture

```text
        Elder / Caregiver demo browser
                   │
       HTML + CSS + Vanilla JavaScript
                   │
                HTTP API
                   │
          Node.js (server.js)
          ├── Demo passcode login / sessions
          ├── Medication schedules + dose events
          ├── Appointment records
          ├── In-app notification generation
          └── Rule-based summary + audit events
                   │
           Local JSON demo file
```

**Stack:** Node.js 18+, built-in `node:http`, `node:crypto`, `node:fs`; HTML, CSS and vanilla JavaScript. No third-party npm runtime dependencies or external AI keys are required.

### API overview

| Method | Endpoint | Purpose |
|:--|:--|:--|
| POST | `/api/login` | Sign in with demo persona and passcode |
| POST | `/api/logout` | Revoke current session |
| GET | `/api/state` | Retrieve shared demo state and in-app alerts |
| POST | `/api/medications` | Create a fictional medication schedule |
| DELETE | `/api/medications/:id` | Deactivate a schedule |
| POST | `/api/doses` | Record today's taken/skipped status |
| POST | `/api/appointments` | Create an appointment |
| DELETE | `/api/appointments/:id` | Remove an appointment |
| GET | `/api/summary` | Obtain rule-based daily summary |

All endpoints except login and logout require a valid demo session.

## ⚡ Run locally

**Prerequisite:** Node.js 18 or newer.

```bash
git clone https://github.com/Sraveena1992/CARECIRCLE-AI.git
cd CARECIRCLE-AI
npm start
```

Open **http://localhost:3000**. No API keys or database server are required.

To run automated tests:

```bash
npm test
```

The repository currently defines **nine Node.js API tests**, covering anonymous denial, invalid passcodes, login, medication validation, duplicate dose prevention, appointment creation/deletion, summary labeling, static-file restrictions and logout. **Run the command to verify results in your own environment**; a test file is not itself proof of a passing deployment.

### 📁 Project structure

```text
CARECIRCLE-AI/
├── public/
│   ├── index.html          # Login and dashboard markup
│   ├── app.js              # Client-side interactions
│   └── style.css           # Responsive premium styling
├── tests/
│   └── server.test.js      # Node API tests
├── server.js               # HTTP server, API and demo storage
├── package.json            # Start and test scripts
└── README.md               # Project documentation
```

The repository may also contain an earlier nested project copy; the root files above are the deployment entry point.

## ☁️ Deployment

For a Node.js service such as Render:

| Setting | Value |
|:--|:--|
| Root directory | Repository root |
| Build command | `npm install` |
| Start command | `npm start` |
| Runtime | Node.js 18+ |
| Port | Provided through `PORT` |

**Live demonstration:** https://carecircle-ai-0og5.onrender.com

The app uses a local JSON file for demonstration storage. On ephemeral hosts, updates **may disappear after restarts or redeployments**. This is not durable production storage.

## 🔒 Security, safety and known limitations

| Area | Current implementation | Required for real-world use |
|:--|:--|:--|
| Identity | Two hard-coded fictional personas; passcodes with fixed-salt hashing | Unique accounts, password hardening, recovery and MFA where appropriate |
| Sessions | In-memory cookie sessions; basic throttling | Durable session management, secure deployment configuration and comprehensive CSRF protection |
| Permissions | Both predefined roles can edit the shared demo record | Patient consent, least-privilege role controls and revocation |
| Storage | Local JSON file | Encrypted durable database, backups and concurrency handling |
| Reminders | Generated **in-app** when state is requested | Background scheduler, verified email delivery, retries and opt-in preferences |
| Intelligence | Deterministic rules | Validated AI integration if appropriate, with human oversight |
| Clinical use | Fictional sample data only | Clinical review, privacy assessment and applicable regulatory compliance |

**Not implemented:** real email/SMS sending, continuous background reminder delivery, generative AI, secure multi-family onboarding, clinical validation or production-grade patient-data protection.

Do not use this prototype to prescribe, change or double a dose. Follow the prescribing clinician's instructions.

## 🏆 Catalyst 2026 — Solo AI Hackathon

**Challenge:** Elderly Care & Medication Management Platform  
**Organizer:** Makers Need More (MnM) / PromptWars × Catalyst  
**Submission:** Public GitHub repository  
**Repository:** https://github.com/Sraveena1992/CARECIRCLE-AI

Organizer guidance specifies **a public repository, one branch, repository size below 10 MB and no more than two submission attempts**. It also lists Google Antigravity in its workflow. This README does **not** assert that Antigravity usage or any other organizer compliance requirement has been independently verified.

## 🛣️ Future roadmap

- Opt-in email reminders with scheduled delivery and failure/retry tracking
- Granular patient-controlled caregiver invitations and permissions
- Durable, encrypted multi-user storage and auditability
- Better accessibility testing with older adults and assistive technologies
- Carefully evaluated AI-assisted care coordination, without autonomous clinical decisions
- Expanded automated, browser and security testing

---

<div align="center">

### 💚 Care should feel connected, clear and human.

**[🌐 Try the demo](https://carecircle-ai-0og5.onrender.com) · [💻 View the code](https://github.com/Sraveena1992/CARECIRCLE-AI)**

*Built for Catalyst 2026 · Fictional hackathon prototype · Not medical advice*

</div>
