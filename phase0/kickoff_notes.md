# Phase 0 Kickoff — Cybersecurity Threat Intelligence Platform

## Vision (1 sentence)
SIEM-lite + UEBA that ingests auth/network/web logs, detects common threats fast, and gives analysts clear, explainable incidents with one-click triage.

## Personas & Must-have Scenarios
- Analyst: From an alert, open incident → see top signals, recent user activity, pivot to logs in one click.
- Manager: Weekly risk/alert trend with false-positive rate and MTTA/MTTR.
- Admin: RBAC (analyst/viewer/admin), API key management, index/retention config.

## MVP Use-cases (Top 5)
1. Login brute-force / credential stuffing
2. Impossible travel
3. Data exfiltration (bytes anomaly)
4. Suspicious admin actions (role/privilege changes)
5. Rare destination / beaconing

## Non-functional Targets (MVP)
- Ingest capacity: 250 EPS target (stretch 1000)
- Search P95: ≤ 2s for last 24h with basic filters
- Alert SLA: ≤ 60s from last contributing event to visible alert
- Retention: 7d hot, 30d warm, 90d cold

## Approver
<Name Surname> (<email>)

## Decisions & Dates
- Vision locked: YYYY-MM-DD
- Use-cases locked: YYYY-MM-DD
- NFR targets set: YYYY-MM-DD
- Approver confirmed: YYYY-MM-DD
### Meeting notes — $(date +"%Y-%m-%d")
- Attendees: <list names>
- Decisions: <brief bullets of decisions made>
- Action items:
  - <Owner> — <task> (due YYYY-MM-DD)
