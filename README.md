<div align="center">

# ✺ CARECIRCLE AI

### Every dose matters. Every elder deserves a circle of care.

**An accessible, connected care workspace for older adults and the people supporting them.**

![Status](https://img.shields.io/badge/status-hackathon%20prototype-2B7469) ![Node](https://img.shields.io/badge/Node.js-18%2B-43853D) ![Tests](https://img.shields.io/badge/API%20tests-9%20passing-1D8069) ![Challenge](https://img.shields.io/badge/Catalyst-2026-9C6DCE)

**Medication routines · Dose check-ins · Appointments · Caregiver visibility · Accessible design**

</div>

---

## ✨ Why CareCircle?

CareCircle turns scattered care routines into a shared, understandable daily picture. Older adults can review their medications and appointments, record what happened, and see the people in their care circle. A caregiver can review the same fictional care record. The elder remains at the center of the experience.

> **Prototype disclaimer:** All accounts and data are fictional. This project is **not** suitable for real patient information, medication management, or medical decisions. It does not deliver real email reminders or use a generative AI service.

## 🖥️ Product experience

| Experience | What works in this prototype |
|---|---|
| 🌿 Elder-first dashboard | Clear navigation, prominent daily medication and appointment information |
| 💊 Medication tracking | Add schedules and record dose outcomes with duplicate prevention |
| 📅 Appointments | Create and remove appointments |
| 👥 Shared care view | Two predefined fictional roles share a demonstration care circle |
| 📈 Care insights | Calculated adherence summary and recorded activity |
| 🔔 In-app awareness | Upcoming/missed dose and appointment indicators when dashboard loads |
| 🔐 Demo access | Passcode login, cookie sessions, basic throttling and input validation |
| 📱 Accessible interface | Responsive layout, readable typography, visible action controls |

## 🚀 Run locally

**Requirements:** Node.js 18 or newer. No npm dependencies or API keys required.

```bash
npm start
```

Open **http://localhost:3000**.

```bash
npm test
```

The automated suite contains **9 API tests**. It covers authentication denial, invalid passcodes, medication validation and creation, duplicate dose prevention, appointments, summary labeling, static-file restrictions and logout. Run the tests on your own machine to verify your environment.

## 👤 Demo accounts

| Persona | Username | Passcode |
|---|---|---|
| Margaret · Elder | `elder` | `123456` |
| Alex · Caregiver | `caregiver` | `654321` |

These credentials are deliberately published for a **fictional demonstration**. Never enter personal medical information.

## 🧭 Explore the app

1. Sign in as **Margaret** and review the Overview.
2. Open **Medications**, add a fictional medicine and record a dose outcome.
3. Visit **Appointments** and add a fictional appointment.
4. Open **Care insights** to see recorded activity and adherence.
5. Sign out, sign in as **Alex**, and inspect the shared fictional care circle.

## 🧩 Architecture

```text
Browser (HTML + CSS + JavaScript)
           │
           ▼
Node.js HTTP server (server.js)
           │
           ▼
Local JSON persistence (demo only)
```

**Technology:** dependency-free Node.js HTTP API, vanilla JavaScript, responsive CSS, Node's built-in test runner. Designed to be quick to inspect, run and demonstrate.

## 🛡️ Safety and transparent limitations

- **No real outbound emails:** reminders are displayed in the application; there is no SMTP integration or background delivery service.
- **No generative AI:** insights are rule-based, not LLM-generated.
- **No production authentication:** fixed-salt passcode hashing, in-memory sessions and hard-coded demonstration accounts.
- **No secure invitations or granular patient consent:** two predefined roles only.
- **No production persistence:** local JSON files are unsuitable for concurrent, multi-instance or ephemeral hosting.
- **No real clinical guidance:** no diagnoses, dosage recommendations or automated treatment decisions.
- **No clinical certification or compliance claims.**

For any real-world application, implement individual user accounts, proper consent, audited role-based access, encrypted durable storage, reliable background notification processing, secure email integration, and a medical safety review.

## ☁️ Deployment notes

This repository can run on a Node.js host using:

```text
Build command: npm install
Start command: npm start
```

The server reads the `PORT` environment variable. **Deploy only with fictional data.** On hosts with ephemeral filesystems, demonstration changes may disappear after a restart. Do not present a successful deployment as proof of production readiness.

## 🏆 Catalyst 2026 submission

**Challenge:** Elderly Care & Medication Management Platform  
**Format:** Solo hackathon  
**Submission:** Public GitHub repository, one branch, repository under 10 MB.

The organizer's instructions also mention **Google Antigravity**. Its mandatory-use status has not been independently confirmed; this project was prepared without assuming an exception to that requirement.

---

<div align="center">

**Built for care, clarity and human-centered decisions.**

*CareCircle AI · Catalyst 2026 hackathon prototype*

</div>
