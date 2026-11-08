# YYYY-MM-DD: <Incident Title>

- **Date:** YYYY-MM-DD
- **Authors:** @ejdhindsa
- **Status:** Complete / In Review
- **Severity:** P1 / P2 / P3

---

## Summary
A high-level explanation of what happened in 2-3 sentences. What broke, how long did it last, and how was it resolved?

## Impact
- **Services affected:** e.g., Alloy, Prometheus, App
- **Downtime duration:** e.g., 25 minutes
- **User impact:** e.g., Telemetry dropped, website unreachable, data loss
- **Data exposure:** None / Specify if security-related

## Timeline
All times in UTC (or local timezone with offset).

- **HH:MM** - Incident begins (underlying condition occurs).
- **HH:MM** - Alert triggers (`<AlertName>` fired in Alertmanager).
- **HH:MM** - Operator acknowledged the alert and began investigation.
- **HH:MM** - Root cause identified.
- **HH:MM** - Mitigation deployed.
- **HH:MM** - Normal operation verified; incident resolved.

## Root cause
Detailed technical explanation of why the failure occurred. What were the trigger conditions, and why didn't safeguards prevent it?

## What went well
- Alerts fired promptly / dead man's switch triggered as expected.
- Documentation or runbooks were accurate and actionable.

## What went badly
- Telemetry/logs were missing or degraded during the incident.
- Mitigation took longer than expected due to unclear failure modes.

## Action items
Concrete preventative actions tracked as GitHub issues:

| Action Item | Type | Owner | GitHub Issue / Status |
| :--- | :--- | :--- | :--- |
| e.g., Add memory limit (`mem_limit`) to container | Prevent | @ejdhindsa | Todo |
| e.g., Create runbook for disk pressure | Mitigate | @ejdhindsa | Todo |
| e.g., Improve watchdog alerting | Detect | @ejdhindsa | Todo |
