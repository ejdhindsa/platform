# 0001. Record architecture decisions with Architecture Decision Records (ADRs)

- Status: accepted
- Date: 2026-11-07

---

## Context

We are designing an infrastructure and observability platform on a VPS for unwreck.dev. As a solo developer, there will be many decisions that will be made during the entire development due to budget and time constraints. It is evident that under those constraints we will be making many architectural trade-offs including tooling, networking, security, and repo layout.

Without a structured way to document these decisions, the idea behind why a particular choice has been made (and the alternatives that have been rejected) will be lost over time. Relying on memory and commit messages will make it hard to understand past decisions or know when to safely revisit them.

Therefore a way of recording all these important decisions must be considered.

---

## Options Considered

1. **Markdown ADRs committed to Git (`docs/adr/`)**:
   - *Pros:* Stored alongside code, version-controlled, changes reviewed via Git, zero external tooling or cost.
   - *Cons:* Requires discipline to write and keep statuses updated.
2. **External documentation (Notion, Google Docs, or Wiki)**:
   - *Pros:* Easy to edit and format.
   - *Cons:* Separated from the code repository, prone to documentation rot, requires external access and context switching.
3. **Do nothing (rely on commit messages and code comments)**:
   - *Pros:* Zero immediate overhead.
   - *Cons:* High risk of losing context; rationale and rejected alternatives are difficult to trace.

---

## Decision

We will be recording all significant architectural decisions using Architecture Decision Records (ADRs) stored as Markdown files in `docs/adr/NNNN-short-title.md` using the standard template defined in `docs/adr/0000-adr-format-template.md`.

---

## Consequences

- **What gets easier:** Rationale and rejected alternatives are preserved alongside the codebase, making future maintenance, onboarding, and reviews straightforward.
- **What gets harder:** Adds a small amount of upfront friction before implementing major architectural changes.
- **When to revisit:** If the documentation overhead becomes a bottleneck for development or if team growth requires an automated ADR management tool.
