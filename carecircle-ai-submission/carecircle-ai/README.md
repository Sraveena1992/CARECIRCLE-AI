# ✺ CareCircle AI — Connected Elder Care

**Every dose matters. Every elder deserves a circle of care.**

Catalyst 2026 hackathon prototype addressing the *Elderly Care & Medication Management Platform* challenge.

## Run

Requires Node.js 18+.

```bash
npm start
```

Visit http://localhost:3000. Run tests with `npm test`.

## Demo accounts (fictional)

| Role | Username | Passcode |
|---|---|---|
| Elder | `elder` | `123456` |
| Caregiver | `caregiver` | `654321` |

**WARNING:** These hard-coded credentials are exclusively for local demo. Do not deploy publicly with real patient information. The app does not provide production-grade authentication, patient consent, or clinical compliance.

## Implemented

- Premium, responsive elder-friendly dashboard and role-specific sessions
- Shared fictional care circle with two predefined accounts
- Persistent JSON medication schedules and dose outcomes
- Duplicate prevention for dose logging
- Appointment creation and removal
- Deterministic adherence summary, transparent audit records
- In-app reminders for upcoming/missed doses and appointments, generated when dashboard is accessed
- Request validation, session cookies, passcode attempt throttling, restricted static files
- Automated API tests

## Explicit limitations

- **No outbound email sending.** Notifications are in-app only, not background emails.
- **No generative AI provider integration.** Care summary is explicitly rule-based.
- Passcodes use a fixed salt, not per-user salt; this is a demo, not production authentication.
- Sessions are in-memory and reset on restart; JSON storage is not suitable for multi-user concurrent production use.
- Two fixed demo roles, no real invitations, granular permissions or patient consent workflow.
- Doses are logged for today only. No recurring schedule variations or timezone-safe scheduling.
- No encryption-at-rest, production access control audit, medical certification or real health record integrations.
- Fonts use a network-loaded font with local fallback.

## Safety

All patient data is fictional. Never use this prototype for real medication management or medical decisions. It does not diagnose, prescribe, recommend dose changes or send real alerts. For missed doses, consult the prescribing clinician or pharmacist.

## Architecture

`public/index.html` + `public/style.css` + `public/app.js` → Node HTTP API (`server.js`) → local JSON persistence. No external runtime dependencies.

## Submission checklist

1. Check organizer requirements regarding mandatory Google Antigravity use.
2. Create a **public** GitHub repository with exactly **one branch**.
3. Keep the repository below **10 MB**; never commit patient data, secrets or `node_modules`.
4. Run `npm test`, manually test UI, and verify submission URL.
5. Submit repository URL through Hack2Skill before deadline.
