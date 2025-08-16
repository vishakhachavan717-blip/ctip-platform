# Decision Log

- DL-001 (YYYY-MM-DD): One-line vision approved. Approver: <name>.
- DL-002 (YYYY-MM-DD): MVP use-cases (5) locked. Approver: <name>.
- DL-003 (YYYY-MM-DD): MVP non-functionals set. Approver: <name>.
- DL-004 (YYYY-MM-DD): Architecture doc approver designated. Approver: <name>.

Vision locked — "A SIEM-lite + UEBA platform … one-click triage."

Analyst scenario locked: Timeline of events and host IP.
Manager scenario locked: Weekly trend of high alerts vs low.
Admin scenario locked: User RBAC in day-one config.

Decision: MVP use-cases locked:
- Login brute-force / credential stuffing
- Impossible travel (rapid geo switch)
- Data exfil bytes anomaly
- Suspicious admin actions
- Rare destination / beaconing

Decision: NFRs locked.
EPS (ingest): 250 (dev), stretch 1000
Search P95: ≤ 2s for last 24h
Alert SLA: ≤ 60s
Retention: 7d hot, 30d warm, 90d cold
