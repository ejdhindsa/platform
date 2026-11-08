# platform

Infrastructure and observability stack for [unwreck.dev](https://unwreck.dev).

Designed for a single self-hosted node. The goal is to catch failures early, keep resource usage bounded, and avoid manual server debugging.

## Architecture

![Observability Architecture](docs/architecture/Observability%20Architecture.png)

- **Collector:** Grafana Alloy ingests metrics, logs, and traces, routing them to Prometheus, Loki, and Tempo.
- **Querying:** Grafana dashboards query metrics (PromQL), logs (LogQL), and traces (TraceQL).
- **Alerting:** Alertmanager routes alerts and sends a heartbeat to Healthchecks.io as a dead man's switch.
- **External checks:** Uptime Robot monitors public endpoints from outside the node.

## Constraints

- **Memory limits:** Explicit memory caps on every container to prevent host-level resource exhaustion.
- **PII masking:** Stripped at the collector (Alloy) before hitting persistent storage.
- **Log lifecycle:** Bounded local retention with remote object storage backups for historical queries.
- **Automated setup:** Host provisioning and service lifecycles are handled with Ansible.

## Documentation

- [ADRs](docs/adr/): Architectural decisions ([ADR 0001](docs/adr/0001-record-architecture-decisions.md))
- [Runbooks](docs/runbooks/): Alert response procedures
- [Postmortems](docs/postmortems/): Incident writeups
