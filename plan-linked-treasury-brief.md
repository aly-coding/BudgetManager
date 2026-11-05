# Plan-Linked Treasury: Team Brief

**Event:** NEAR Hackathon, November 1–14, 2026 (judging November 16–18)
**Team:** Uprali (Aly, Ruslana, Vadim)
**Track focus:** AI agents and autonomous payments

## One-liner

Uprali turns a company's financial plan into live spending rules. An AI agent pays only what fits the approved budget, holds everything else for approval, and logs every decision.

## Problem

- Budgets live in spreadsheets, so overspending is usually discovered weeks later.
- Approvals happen over email, and the link between plan and cash movement is manual.
- Autonomous agents are starting to make payments, and businesses need controls that match their speed.

## Solution

1. The budget becomes the policy: category limits, vendor allowlist, per-transaction limits.
2. A payment request goes to the agent, which runs a deterministic policy check and returns approve, hold, or reject with a reason.
3. Approved payments move through NEAR Intents on testnet.
4. Held requests go to a human approver.
5. An append-only audit log records each decision with the plan version used.

## Demo flow (3 minutes)

1. CFO sets a monthly software budget in Uprali.
2. Agent receives a $4,000 vendor payment request. Within budget, so it pays automatically.
3. A $9,000 request exceeds remaining budget. Agent holds it and sends an approval prompt.
4. CFO approves or rejects. Audit log shows both decisions and the plan version.
5. Runway updates on screen.

## Scope for the hackathon

**In:** Policy engine (deterministic), one testnet payment flow via NEAR Intents, Claude-powered request intake, human approval step, audit log, dashboard with plan, approvals, log, and runway chart, seeded demo data.

**Out:** Real money, production integrations with accounting systems, multi-currency treasury, real vendor onboarding.

## Build plan

| Days | Focus |
|---|---|
| 1–2 | Confirm rules and roles. NEAR testnet wallet and one test transaction. Define plan JSON format. |
| 3–5 | Policy engine and append-only audit log. Unit tests for every decision path. |
| 6–8 | Claude agent for request intake and proposed actions. One real testnet payment. Approval step. |
| 9–11 | Dashboard and seeded demo data. |
| 12–13 | Edge cases (over-budget, unknown vendor, duplicates, failed transactions). Backup demo video. |
| 14 | README, pitch, submission. |

## Roles (to confirm)

- **Policy engine and plan model:** Aly
- **NEAR integration and payments:** Vadim (CTO)
- **Agent, dashboard, and demo:** Ruslana

## Open decisions

- Use Uprali's real planning data or a standalone demo budget? Recommendation: standalone for the hackathon.
- Split between model-driven and code-driven decisions. Recommendation: all approval rules in code, with the model used only for parsing requests and explaining decisions.
- Whether to submit to the AI-judge track as well, since Claude Code and Codex are on the panel.

## Risks

- Testnet instability or NEAR Intents docs gaps. Mitigation: validate the payment path on day 2 before building anything around it.
- Scope creep into the dashboard. Mitigation: a working CLI demo comes first; the UI is polish.
- Live demo failure. Mitigation: recorded backup video by day 13.
